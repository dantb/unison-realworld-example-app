# ![RealWorld Example App](logo.png)


> ### Work in progress [Unison](https://www.unison-lang.org/) implementation of the [RealWorld](https://github.com/gothinkster/realworld) backend application. This is a REST web application which should eventually adhere to the [endpoint specification](https://realworld-docs.netlify.app/docs/specs/backend-specs/endpoints).

<hr>

# Getting started

To ease any confusion upfront: Unison code is [content-addressed](https://www.unison-lang.org/learn/the-big-idea/), which is why the codebase is a database and not human-readable. Types and functions are identified by a hash of their syntax tree. To view this code we must use a tool.


1. Clone this repo
    ```
    git clone git@github.com:dantb/unison-realworld-example-app.git
    ```
2. Install Unison Codebase Manager. Instructions [here](https://www.unison-lang.org/learn/quickstart/).
3. Run `ucm` at the root of this repository. Then within UCM, `run trunk.main` will start the web application.


NOTE: Soon this application will be on [Unison share](https://share.unison-lang.org/), so the code will be readable on a public website. You will also be able to pull it locally as a namespace in your own codebase.

<hr>

# Progress report

Progress is being tracked on [this board](https://github.com/users/dantb/projects/2).

## Caveats

Unison is an alpha language, so the library ecosystem is a work in progress. Thus some of the features required by the RealWorld backend have prerequisites which do not yet exist. I plan to implement some of these.

1. Authorization logic currently uses a `JWT` ability with a dummy handler. Implementing RSA and then JWT on top of it is on the project board.
2. Database interactions are abstracted by the `KeyValueStore` ability. Currently I'm using an in-memory handler for this. There is a [redis library](https://share.unison-lang.org/latest/namespaces/ceedubs/redis) which could be used instead. For now I'm prioritising other features, since that may add some overhead by introducing an external dependency.

## Endpoints
Current implemented endpoints:

- User registration `POST /users`
- User login `POST /users/login`
- Fetch user `GET /user`

<hr>

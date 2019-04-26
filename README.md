# Example Web Application in Clojure

This is a simple web application using [Component](https://github.com/stuartsierra/component), [Ring](https://github.com/ring-clojure/ring), [Compojure](https://github.com/weavejester/compojure), and [Selmer](https://github.com/yogthos/Selmer) connected to a local SQLite database.

Clojure beginners often ask for a "complete" example that they can look at to see how these common libraries fit together and for a long time I pointed them at the User Manager example in the Framework One for Clojure repo -- but since I EOL'd that framework and I'd already rewritten the example app to no longer use the framework, it's just confusing to point them there, so this is a self-contained repo containing just that web app example.

## Requirements

This example assumes that you have the [Clojure CLI](https://clojure.org/guides/deps_and_cli) installed, and provides a `deps.edn` file.

Clojure 1.10 (or later) is required. The "model" of this example app uses namespace-qualified keys in hash maps. It uses [next.jdbc](https://cljdoc.org/d/seancorfield/next.jdbc) -- the "next generation" JDBC library for Clojure -- which produces namespace-qualified hash maps from result sets.

## Usage

Clone the repo, `cd` into it, and run it with:

```
clj -m usermanager.main
```

It should create a SQLite database (`usermanager_db`) and populate two tables (`department` and `addressbook`) and start a Jetty instance on port 8080.

If that port is in use, start it on a different port. For example, port 8100:

```
clj -m usermanager.main 8100
```

Run the tests with:

```
clj -A:test:runner
```

_There aren't any tests yet but I will create some soon!_

## Stuff I Need To Do

* There should be some real-world tests.
* I might add a `datafy`/`nav` example.

# License & Copyright

Copyright (c) 2015-2019 Sean Corfield.

Distributed under the Apache Source License 2.0.
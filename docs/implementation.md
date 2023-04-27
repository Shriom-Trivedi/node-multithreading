## What we are trying to do?

We are looking for a way to execute multithreading in JavaScript.

---

## Some knowledge

1) We have a main thread running in our node app which is running in the v8 engine.
2) v8 engine implements a library called libuv
3) libuv helps node spawning some extra little threads i.e. 7.
    - 2 are for garbage collection.
    - 4 other responds when needed i.e when we have some IO operation (db queries, file read/write, network operations)

4) none of this work for CPU bound operations.
5) parentPort.postMessage() is the way to communicate with your main thread.
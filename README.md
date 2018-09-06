# *lambdajs*

## the goal - js code static analysis and inference to *functional paradigm* if possible

Make the gap between *server side* of the *javascript* and **build artifact**
to a state constrained to **functional** programming paradigm, with respect to
concepts like:

* *First-class functions*
* *purity of unction* and *side effects awarenes*
* *Data structure immutability*
  * [Immutable.js](https://facebook.github.io/immutable-js/)

If possible, it also should *infer* an transpiled version, otherwise and exception
must be thrown at *compile/transpile* time.

## Use Cases

### Accumulation of *typed* function argument values, before dispatching.

#### Human readable description of *use-case* based on [*Contracts*](https://github.com/hemanth/functional-programming-jargon#contracts)

> A contract specifies the obligations and guarantees of the behavior from a function or expression at runtime. This acts as a set of rules that are expected from the input and output of a function or expression, and errors are generally reported whenever a contract is violated.

##### Decision tree

* Feed an function with data structures that represent an part of typed collection,
  must return an *partial function* and **dispatch** once a *handler function* is passed.
  * For example
    * feed a function with *array* typed first argument value,
      that represent *resource's taxonomy tag key->value*.
      * for example
        * by default, if none data structures are passed
          * tag environment=staging will be used
          * passed data struct overides an existing one in accamulating collection, based on key
          * once *function* with following signature is passed, it should dispatch an
            *request* while using an accamulated structure as payload.
            * ` fnk (Error error, result Array<Object>)`

# References

* [FLOW - Static type checker](https://flow.org/),

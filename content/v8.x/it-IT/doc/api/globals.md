# Object Globali

<!--introduced_in=v0.10.0-->

<!-- type=misc -->

Questi object sono disponibili in tutti i moduli. The following variables may appear to be global but are not. They exist only in the scope of modules, see the [module system documentation](modules.html):

* [`__dirname`][]
* [`__filename`][]
* [`exports`][]
* [`module`][]
* [`require()`][]

Gli object qui elencati sono specifici a Node.js. There are a number of [built-in objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects) that are part of the JavaScript language itself, which are also globally accessible.

## Class: Buffer

<!-- YAML
added: v0.1.103
-->

<!-- type=global -->

* {Function}

Utilizzato per gestire i dati binari. Visualizza la [sezione buffer](buffer.html).

## \_\_dirname

This variable may appear to be global but is not. See [`__dirname`].

## \_\_filename

This variable may appear to be global but is not. See [`__filename`].

## clearImmediate(immediateObject)

<!-- YAML
added: v0.9.1
-->

<!--type=global-->

[`clearImmediate`] è descritta nella sezione [timers](timers.html).

## clearInterval(intervalObject)

<!-- YAML
added: v0.0.1
-->

<!--type=global-->

[`clearInterval`] è descritto nella sezione [timers](timers.html).

## clearTimeout(timeoutObject)

<!-- YAML
added: v0.0.1
-->

<!--type=global-->

[`clearTimeout`] è descritto nella sezione [timers](timers.html).

## console

<!-- YAML
added: v0.1.100
-->

<!-- type=global -->

* {Object}

Utilizzato per la stampa su stdout e stderr. Visualizza la sezione [`console`][].

## export

This variable may appear to be global but is not. See [`exports`].

## globale

<!-- YAML
added: v0.1.27
-->

<!-- type=global -->

* {Object} Il namespace object globale.

Nei browser, l'ambito principale è l'ambito globale. This means that within the browser `var something` will define a new global variable. In Node.js this is different. The top-level scope is not the global scope; `var something` inside a Node.js module will be local to that module.

## module

This variable may appear to be global but is not. See [`module`].

## process

<!-- YAML
added: v0.1.7
-->

<!-- type=global -->

* {Object}

L'object del processo. Visualizza la sezione [object del `processo`][].

## require()

This variable may appear to be global but is not. See [`require()`].

## setImmediate(callback[, ...args])

<!-- YAML
added: v0.9.1
-->

<!-- type=global -->

[`setImmediate`] è descritto nella sezione [timers](timers.html).

## setInterval(callback, delay[, ...args])

<!-- YAML
added: v0.0.1
-->

<!-- type=global -->

[`setInterval`] è descritto nella sezione [timers](timers.html).

## setTimeout(callback, delay[, ...args])

<!-- YAML
added: v0.0.1
-->

<!-- type=global -->

[`setTimeout`] è descritto nella sezione [timers](timers.html).
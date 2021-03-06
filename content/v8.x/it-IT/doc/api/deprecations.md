# API obsolete

<!--introduced_in=v7.7.0-->

Node.js may deprecate APIs when either: (a) use of the API is considered to be unsafe, (b) an improved alternative API has been made available, or (c) breaking changes to the API are expected in a future major release.

Node.js utilizza tre tipi di Deprecazioni:

* Documentation-only
* Runtime
* End-of-Life

A Documentation-only deprecation is one that is expressed only within the Node.js API docs. Queste non generano effetti collaterali durante l'esecuzione di Node.js.

A Runtime deprecation will, by default, generate a process warning that will be printed to `stderr` the first time the deprecated API is used. When the `--throw-deprecation` command-line flag is used, a Runtime deprecation will cause an error to be thrown.

An End-of-Life deprecation is used to identify code that either has been removed or will soon be removed from Node.js.

## Un-deprecation

From time-to-time the deprecation of an API may be reversed. Such action may happen in either a semver-minor or semver-major release. In such situations, this document will be updated with information relevant to the decision. *However, the deprecation identifier will not be modified*.

## Elenco delle API Deprecate/Obsolete

<a id="DEP0001"></a>

### DEP0001: http.OutgoingMessage.prototype.flush

Tipo: Runtime

Il metodo `OutgoingMessage.prototype.flush()` è deprecato/obsoleto. Use `OutgoingMessage.prototype.flushHeaders()` instead.

<a id="DEP0002"></a>

### DEP0002: require('\_linklist')

Tipo: End-of-Life

Il modulo `_linklist` è deprecato/obsoleto. Si prega di utilizzare un'alternativa userland.

<a id="DEP0003"></a>

### DEP0003: \_writableState.buffer

Tipo: Runtime

La proprietà `_writableState.buffer` è deprecata/obsoleta. Use the `_writableState.getBuffer()` method instead.

<a id="DEP0004"></a>

### DEP0004: CryptoStream.prototype.readyState

Tipo: Documentation-only

The `CryptoStream.prototype.readyState` property is deprecated and should not be used.

<a id="DEP0005"></a>

### DEP0005: Buffer() constructor

Tipo: Documentation-only

The `Buffer()` function and `new Buffer()` constructor are deprecated due to API usability issues that can potentially lead to accidental security issues.

As an alternative, use of the following methods of constructing `Buffer` objects is strongly recommended:

* [`Buffer.alloc(size[, fill[, encoding]])`](buffer.html#buffer_class_method_buffer_alloc_size_fill_encoding) - Create a `Buffer` with *initialized* memory.
* [`Buffer.allocUnsafe(size)`](buffer.html#buffer_class_method_buffer_allocunsafe_size) - Create a `Buffer` with *uninitialized* memory.
* [`Buffer.allocUnsafeSlow(size)`][] - Create a `Buffer` with *uninitialized* memory.
* [`Buffer.from(array)`][] - Crea un `Buffer` con una copia di `array`
* [`Buffer.from(arrayBuffer[, byteOffset[, length]])`](buffer.html#buffer_class_method_buffer_from_arraybuffer_byteoffset_length) - Create a `Buffer` that wraps the given `arrayBuffer`.
* [`Buffer.from(buffer)`][] - Crea un `Buffer` che copia `buffer`.
* [`Buffer.from(string[, encoding])`](buffer.html#buffer_class_method_buffer_from_string_encoding) - Create a `Buffer` that copies `string`.

<a id="DEP0006"></a>

### DEP0006: child\_process options.customFds

Tipo: Runtime

Within the [`child_process`][] module's `spawn()`, `fork()`, and `exec()` methods, the `options.customFds` option is deprecated. The `options.stdio` option should be used instead.

<a id="DEP0007"></a>

### DEP0007: cluster worker.suicide

Tipo: Runtime

Within the `cluster` module, the [`worker.suicide`][] property has been deprecated. Please use [`worker.exitedAfterDisconnect`][] instead.

<a id="DEP0008"></a>

### DEP0008: require('constants')

Tipo: Documentation-only

Il modulo `constants` è deprecato/obsoleto. When requiring access to constants relevant to specific Node.js builtin modules, developers should instead refer to the `constants` property exposed by the relevant module. For instance, `require('fs').constants` and `require('os').constants`.

<a id="DEP0009"></a>

### DEP0009: crypto.pbkdf2 senza digest

Type: End-of-life

Use of the [`crypto.pbkdf2()`][] API without specifying a digest was deprecated in Node.js 6.0 because the method defaulted to using the non-recommended `'SHA1'` digest. In precedenza, veniva stampato un avviso di deprecazione. Starting in Node.js 8.0.0, calling `crypto.pbkdf2()` or `crypto.pbkdf2Sync()` with an undefined `digest` will throw a `TypeError`.

<a id="DEP0010"></a>

### DEP0010: crypto.createCredentials

Tipo: Runtime

L'API [`crypto.createCredentials()`][] è deprecata/obsoleta. Please use [`tls.createSecureContext()`][] instead.

<a id="DEP0011"></a>

### DEP0011: crypto.Credentials

Tipo: Runtime

La classe `crypto.Credentials` è deprecata/obsoleta. Please use [`tls.SecureContext`][] instead.

<a id="DEP0012"></a>

### DEP0012: Domain.dispose

Tipo: Runtime

[`Domain.dispose()`][] is deprecated. Recover from failed I/O actions explicitly via error event handlers set on the domain instead.

<a id="DEP0013"></a>

### DEP0013: fs funzione asincrona senza callback

Tipo: Runtime

Calling an asynchronous function without a callback is deprecated.

<a id="DEP0014"></a>

### DEP0014: interfaccia fs.read legacy String

Tipo: End-of-Life

The [`fs.read()`][] legacy String interface is deprecated. Use the Buffer API as mentioned in the documentation instead.

<a id="DEP0015"></a>

### DEP0015: interfaccia fs.readSync legacy String

Tipo: End-of-Life

The [`fs.readSync()`][] legacy String interface is deprecated. Use the Buffer API as mentioned in the documentation instead.

<a id="DEP0016"></a>

### DEP0016: GLOBAL/root

Tipo: Runtime

The `GLOBAL` and `root` aliases for the `global` property have been deprecated and should no longer be used.

<a id="DEP0017"></a>

### DEP0017: Intl.v8BreakIterator

Tipo: Runtime

The `Intl.v8BreakIterator` is deprecated and will be removed or replaced soon.

<a id="DEP0018"></a>

### DEP0018: Promise rejection non gestiti

Tipo: Runtime

I promise rejection non gestiti sono deprecati/obsoleti. In the future, promise rejections that are not handled will terminate the Node.js process with a non-zero exit code.

<a id="DEP0019"></a>

### DEP0019: require('.') risolto al di fuori della directory

Tipo: Runtime

In alcuni casi, `require('.')` potrebbe risolversi al di fuori della directory del pacchetto. This behavior is deprecated and will be removed in a future major Node.js release.

<a id="DEP0020"></a>

### DEP0020: Server.connections

Tipo: Runtime

La proprietà [`Server.connections`][] è deprecata/obsoleta. Please use the [`Server.getConnections()`][] method instead.

<a id="DEP0021"></a>

### DEP0021: Server.listenFD

Tipo: Runtime

Il metodo `Server.listenFD()` è deprecato/obsoleto. Please use [`Server.listen({fd: <number>})`][] instead.

<a id="DEP0022"></a>

### DEP0022: os.tmpDir()

Tipo: Runtime

L'API `os.tmpDir()` è deprecata/obsoleta. Si prega di utilizzare [`os.tmpdir()`][] al suo posto.

<a id="DEP0023"></a>

### DEP0023: os.getNetworkInterfaces()

Tipo: Runtime

Il metodo `os.getNetworkInterfaces()` è deprecato/obsoleto. Please use the [`os.networkInterfaces`][] property instead.

<a id="DEP0024"></a>

### DEP0024: REPLServer.prototype.convertToContext()

Tipo: Runtime

The `REPLServer.prototype.convertToContext()` API is deprecated and should not be used.

<a id="DEP0025"></a>

### DEP0025: require('sys')

Tipo: Runtime

Il modulo `sys` è deprecato/obsoleto. Si prega di utilizzare il modulo [`util`][] al suo posto.

<a id="DEP0026"></a>

### DEP0026: util.print()

Tipo: Runtime

L'API [`util.print()`][] è deprecata/obsoleta. Si prega di utilizzare [`console.log()`][] al suo posto.

<a id="DEP0027"></a>

### DEP0027: util.puts()

Tipo: Runtime

L'API [`util.puts()`][] è deprecata/obsoleta. Si prega di utilizzare [`console.log()`][] al suo posto.

<a id="DEP0028"></a>

### DEP0028: util.debug()

Tipo: Runtime

L'API [`util.debug()`][] è deprecata/obsoleta. Please use [`console.error()`][] instead.

<a id="DEP0029"></a>

### DEP0029: util.error()

Tipo: Runtime

L'API [`util.error()`][] è deprecata/obsoleta. Please use [`console.error()`][] instead.

<a id="DEP0030"></a>

### DEP0030: SlowBuffer

Tipo: Documentation-only

La classe [`SlowBuffer`][] è stata deprecata. Please use [`Buffer.allocUnsafeSlow(size)`][] instead.

<a id="DEP0031"></a>

### DEP0031: ecdh.setPublicKey()

Tipo: Documentation-only

The [`ecdh.setPublicKey()`][] method is now deprecated as its inclusion in the API is not useful.

<a id="DEP0032"></a>

### DEP0032: modulo domain

Tipo: Documentation-only

Il modulo [`domain`][] è deprecato/obsoleto e non dovrebbe essere utilizzato.

<a id="DEP0033"></a>

### DEP0033: EventEmitter.listenerCount()

Tipo: Documentation-only

The [`EventEmitter.listenerCount(emitter, eventName)`][] API has been deprecated. Si prega di utilizzare [`emitter.listenerCount(eventName)`][] al suo posto.

<a id="DEP0034"></a>

### DEP0034: fs.exists(path, callback)

Tipo: Documentation-only

L'API [`fs.exists(path, callback)`][] è stata deprecata. Please use [`fs.stat()`][] or [`fs.access()`][] instead.

<a id="DEP0035"></a>

### DEP0035: fs.lchmod(path, mode, callback)

Tipo: Documentation-only

L'API [`fs.lchmod(path, mode, callback)`][] è stata deprecata.

<a id="DEP0036"></a>

### DEP0036: fs.lchmodSync(path, mode)

Tipo: Documentation-only

L'API [`fs.lchmodSync(path, mode)`][] è stata deprecata.

<a id="DEP0037"></a>

### DEP0037: fs.lchown(path, uid, gid, callback)

Tipo: Documentation-only

L'API [`fs.lchown(path, uid, gid, callback)`][] è stata deprecata.

<a id="DEP0038"></a>

### DEP0038: fs.lchownSync(path, uid, gid)

Tipo: Documentation-only

L'API [`fs.lchownSync(path, uid, gid)`][] è stata deprecata.

<a id="DEP0039"></a>

### DEP0039: require.extensions

Tipo: Documentation-only

La proprietà [`require.extensions`][] è stata deprecata.

<a id="DEP0040"></a>

### DEP0040: modulo punycode

Tipo: Documentation-only

Il modulo [`punycode`][] è stato deprecato. Please use a userland alternative instead.

<a id="DEP0041"></a>

### DEP0041: variabile d'ambiente NODE\_REPL\_HISTORY\_FILE

Tipo: Documentation-only

The `NODE_REPL_HISTORY_FILE` environment variable has been deprecated.

<a id="DEP0042"></a>

### DEP0042: tls.CryptoStream

Tipo: Documentation-only

La classe [`tls.CryptoStream`][] è stata deprecata. Please use [`tls.TLSSocket`][] instead.

<a id="DEP0043"></a>

### DEP0043: tls.SecurePair

Tipo: Documentation-only

La classe [`tls.SecurePair`][] è stata deprecata. Please use [`tls.TLSSocket`][] instead.

<a id="DEP0044"></a>

### DEP0044: util.isArray()

Tipo: Documentation-only

L'API [`util.isArray()`][] è stata deprecata. Please use `Array.isArray()` instead.

<a id="DEP0045"></a>

### DEP0045: util.isBoolean()

Tipo: Documentation-only

L'API [`util.isBoolean()`][] è stata deprecata.

<a id="DEP0046"></a>

### DEP0046: util.isBuffer()

Tipo: Documentation-only

L'API [`util.isBuffer()`][] è stata deprecata. Please use [`Buffer.isBuffer()`][] instead.

<a id="DEP0047"></a>

### DEP0047: util.isDate()

Tipo: Documentation-only

L'API [`util.isDate()`][] è stata deprecata.

<a id="DEP0048"></a>

### DEP0048: util.isError()

Tipo: Documentation-only

L'API [`util.isError()`][] è stata deprecata.

<a id="DEP0049"></a>

### DEP0049: util.isFunction()

Tipo: Documentation-only

L'API [`util.isFunction()`][] è stata deprecata.

<a id="DEP0050"></a>

### DEP0050: util.isNull()

Tipo: Documentation-only

L'API [`util.isNull()`][] è stata deprecata.

<a id="DEP0051"></a>

### DEP0051: util.isNullOrUndefined()

Tipo: Documentation-only

L'API [`util.isNullOrUndefined()`][] è stata deprecata.

<a id="DEP0052"></a>

### DEP0052: util.isNumber()

Tipo: Documentation-only

L'API [`util.isNumber()`][] è stata deprecata.

<a id="DEP0053"></a>

### DEP0053 util.isObject()

Tipo: Documentation-only

L'API [`util.isObject()`][] è stata deprecata.

<a id="DEP0054"></a>

### DEP0054: util.isPrimitive()

Tipo: Documentation-only

L'API [`util.isPrimitive()`][] è stata deprecata.

<a id="DEP0055"></a>

### DEP0055: util.isRegExp()

Tipo: Documentation-only

L'API [`util.isRegExp()`][] è stata deprecata.

<a id="DEP0056"></a>

### DEP0056: util.isString()

Tipo: Documentation-only

L'API [`util.isString()`][] è stata deprecata.

<a id="DEP0057"></a>

### DEP0057: util.isSymbol()

Tipo: Documentation-only

L'API [`util.isSymbol()`][] è stata deprecata.

<a id="DEP0058"></a>

### DEP0058: util.isUndefined()

Tipo: Documentation-only

L'API [`util.isUndefined()`][] è stata deprecata.

<a id="DEP0059"></a>

### DEP0059: util.log()

Tipo: Documentation-only

L'API [`util.log()`][] è stata deprecata.

<a id="DEP0060"></a>

### DEP0060: util.\_extend()

Tipo: Documentation-only

L'API [`util._extend()`][] è stata deprecata.

<a id="DEP0061"></a>

### DEP0061: fs.SyncWriteStream

Tipo: Runtime

The `fs.SyncWriteStream` class was never intended to be a publicly accessible API. Non è disponibile alcuna API alternativa. Si prega di utilizzare un'alternativa userland.

<a id="DEP0062"></a>

### DEP0062: node --debug

Tipo: Runtime

`--debug` activates the legacy V8 debugger interface, which has been removed as of V8 5.8. It is replaced by Inspector which is activated with `--inspect` instead.

<a id="DEP0063"></a>

### DEP0063: ServerResponse.prototype.writeHeader()

Tipo: Documentation-only

The `http` module `ServerResponse.prototype.writeHeader()` API has been deprecated. Si prega di utilizzare `ServerResponse.prototype.writeHead()` al suo posto.

*Note*: The `ServerResponse.prototype.writeHeader()` method was never documented as an officially supported API.

<a id="DEP0064"></a>

### DEP0064: tls.createSecurePair()

Tipo: Runtime

The `tls.createSecurePair()` API was deprecated in documentation in Node.js 0.11.3. Users should use `tls.Socket` instead.

<a id="DEP0065"></a>

### DEP0065: repl.REPL_MODE_MAGIC e NODE_REPL_MODE=magic

Tipo: Documentation-only

The `repl` module's `REPL_MODE_MAGIC` constant, used for `replMode` option, has been deprecated. Its behavior has been functionally identical to that of `REPL_MODE_SLOPPY` since Node.js v6.0.0, when V8 5.0 was imported. Please use `REPL_MODE_SLOPPY` instead.

The `NODE_REPL_MODE` environment variable is used to set the underlying `replMode` of an interactive `node` session. Its default value, `magic`, is similarly deprecated in favor of `sloppy`.

<a id="DEP0066"></a>

### DEP0066: outgoingMessage.\_headers, outgoingMessage.\_headerNames

Tipo: Documentation-only

The `http` module `outgoingMessage._headers` and `outgoingMessage._headerNames` properties have been deprecated. Please instead use one of the public methods (e.g. `outgoingMessage.getHeader()`, `outgoingMessage.getHeaders()`, `outgoingMessage.getHeaderNames()`, `outgoingMessage.hasHeader()`, `outgoingMessage.removeHeader()`, `outgoingMessage.setHeader()`) for working with outgoing headers.

*Note*: `outgoingMessage._headers` and `outgoingMessage._headerNames` were never documented as officially supported properties.

<a id="DEP0067"></a>

### DEP0067: OutgoingMessage.prototype.\_renderHeaders

Tipo: Documentation-only

The `http` module `OutgoingMessage.prototype._renderHeaders()` API has been deprecated.

*Note*: `OutgoingMessage.prototype._renderHeaders` was never documented as an officially supported API.

<a id="DEP0068"></a>

### DEP0068: node debug

Tipo: Runtime

`node debug` corresponds to the legacy CLI debugger which has been replaced with a V8-inspector based CLI debugger available through `node inspect`.

<a id="DEP0069"></a>

### DEP0069: vm.runInDebugContext(string)

Tipo: Documentation-only

The DebugContext will be removed in V8 soon and will not be available in Node 10+.

*Note*: DebugContext was an experimental API.

<a id="DEP0070"></a>

### DEP0070: async_hooks.currentId()

Tipo: Runtime

`async_hooks.currentId()` was renamed to `async_hooks.executionAsyncId()` for clarity.

*Note*: change was made while `async_hooks` was an experimental API.

<a id="DEP0071"></a>

### DEP0071: async_hooks.triggerId()

Tipo: Runtime

`async_hooks.triggerId()` was renamed to `async_hooks.triggerAsyncId()` for clarity.

*Note*: change was made while `async_hooks` was an experimental API.

<a id="DEP0072"></a>

### DEP0072: async_hooks.AsyncResource.triggerId()

Tipo: Runtime

`async_hooks.AsyncResource.triggerId()` was renamed to `async_hooks.AsyncResource.triggerAsyncId()` for clarity.

*Note*: change was made while `async_hooks` was an experimental API.

<a id="DEP0076"></a>

### DEP0076: tls.parseCertString()

Tipo: Documentation-only

`tls.parseCertString()` is a trivial parsing helper that was made public by mistake. Questa funzione può essere generalmente sostituita con:

```js
const querystring = require('querystring');
querystring.parse(str, '\n', '=');
```

*Note*: This function is not completely equivalent to `querystring.parse()`. One difference is that `querystring.parse()` does url decoding:

```sh
> querystring.parse('%E5%A5%BD=1', '\n', '=');
{ '好': '1' }
> tls.parseCertString('%E5%A5%BD=1');
{ '%E5%A5%BD': '1' }
```

<a id="DEP0079"></a>

### DEP0079: Funzione di ispezione personalizzata sugli Object tramite .inspect()

Tipo: Documentation-only

Using a property named `inspect` on an object to specify a custom inspection function for [`util.inspect()`][] is deprecated. Use [`util.inspect.custom`][] instead. For backwards compatibility with Node.js prior to version 6.4.0, both may be specified.

<a id="DEP0085"></a>

### DEP0085: AsyncHooks Sensitive API

Tipo: Runtime

The AsyncHooks Sensitive API was never documented and had various of minor issues, see https://github.com/nodejs/node/issues/15572. Use the `AsyncResource` API instead.

<a id="DEP0086"></a>

### DEP0086: Rimuove runInAsyncIdScope

Tipo: Runtime

`runInAsyncIdScope` doesn't emit the `before` or `after` event and can thus cause a lot of issues. See https://github.com/nodejs/node/issues/14328 for more details.

<a id="DEP0089"></a>

### DEP0089: require('assert')

Tipo: Documentation-only

Importing assert directly is not recommended as the exposed functions will use loose equality checks. Utilizza `require('assert').strict` al suo posto. The API is the same as the legacy assert but it will always use strict equality checks.

<a id="DEP0098"></a>

### DEP0098: AsyncHooks Embedder AsyncResource.emit{Before,After} APIs

Tipo: Runtime

The embedded API provided by AsyncHooks exposes emit{Before,After} methods which are very easy to use incorrectly which can lead to unrecoverable errors.

Use [`asyncResource.runInAsyncScope()`][] API instead which provides a much safer, and more convenient, alternative. See https://github.com/nodejs/node/pull/18513 for more details.
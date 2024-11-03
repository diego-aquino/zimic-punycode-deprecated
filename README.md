# Zimic Punycode Deprecated Reproduction

This reproduction repository demonstrates a warning happening when using the Zimic CLI in Node.js 22.

## Running

1. Install the dependencies:

   ```bash
   pnpm install
   ```

2. Run the typegen CLI:

   ```bash
   pnpm typegen:github
   ```

Even though the command executes successfully, a warning about `punycode` being deprecated is shown:

```
$ NODE_OPTIONS=--trace-deprecation pnpm typegen:github

(node:23082) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
    at node:punycode:3:9
    at BuiltinModule.compileForInternalLoader (node:internal/bootstrap/realm:399:7)
    at BuiltinModule.compileForPublicLoader (node:internal/bootstrap/realm:338:10)
    at loadBuiltinModule (node:internal/modules/helpers:114:7)
    at Function._load (node:internal/modules/cjs/loader:1100:17)
    at TracingChannel.traceSync (node:diagnostics_channel:315:14)
    at wrapModuleLoad (node:internal/modules/cjs/loader:218:24)
    at Module.require (node:internal/modules/cjs/loader:1340:12)
    at require (node:internal/modules/helpers:141:16)
    at Object.<anonymous> (/home/diegoaquino/www/zimic-punycode-deprecated/node_modules/.pnpm/whatwg-url@5.0.0/node_modules/whatwg-url/lib/url-state-machine.js:2:18)
[zimic] ✔ Generated ./src/types/github/typegen/generated.ts (3.06s)
```

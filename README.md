TaskCluster Javascript Rules
============================

This repository contains various rules for taskcluster node components.
Intended to be used with modules such as `babel-compile` and `eslint`.

Example:
```js
{
  "name": "taskcluster-lib-...",
  "version": "...",
  "license": "MPL-2.0",
  "scripts": {
    "compile": "babel-compile -c taskcluster-lib-rules/babel src:lib test:.test",
    "prepublish": "npm run compile",
    "pretest": "npm run compile",
  },
  "dependencies": {
    "babel-runtime": "^5.8.25"
  },
  "devDependencies": {
    "babel-compile": "^0.0.3",
    "mocha": "^2.0.1",
    "taskcluster-lib-rules": "^1.0.6"
  },
  ...
}

```

By loading configuration from this module, all TaskCluster Javascript modules
can have the same linter and babel configuration. This should help us keep
the code reasonably consistent.


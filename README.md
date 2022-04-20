# 00-copy-paste

This is an example of how copy-pasting code into a repo would work. Consider this scenario: a package `dependency` we would like `dependent` to depend on exists at `~/dependency`. We copy-paste the entire contents of `~/dependency` into `~/dependent/packages/dependency`, then possibly set up a workspace to inform `npm` of the dependency tree.

```
~
├── dependency
│   ├── index.js
│   ├── package-lock.json
│   └── package.json
└── dependent
    ├── index.js
    ├── package-lock.json
    ├── package.json
    └── packages
        └── dependency # <- this directory was copied
            ├── index.js
            ├── package-lock.json
            └── package.json
```

Once this copy-paste is executed, `~/dependent/packages/dependency` will no longer receive updates made to `dependency`. To receive updates, the copy-paste must be re-executed or a patchfile must be distributed to the maintainters of `dependent`.

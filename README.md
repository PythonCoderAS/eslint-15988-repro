# eslint-15988-repro
Repro repo for eslint issue #15988.

To repro, clone and use `npm ci`.

Afterwards, run these commands:

* `npx eslint .`
* `npx eslint . --config .eslintrc`

```js
❯ npx eslint .

/private/tmp/eslint-15988-repro/index.js
  1:1  error  Empty block statement  no-empty
  1:1  error  Block is redundant     no-lone-blocks

✖ 2 problems (2 errors, 0 warnings)

❯ npx eslint . --config .eslintrc

Oops! Something went wrong! :(

ESLint: 8.17.0

Error: --config » eslint-config-pythoncoderas-combo » eslint-config-pythoncoderas » eslint-config-airbnb-base » /private/tmp/eslint-15988-repro/node_modules/eslint-config-airbnb-base/rules/best-practices.js:
	Configuration for rule "dot-notation" is invalid:
	Value {"allowKeywords":true,"allowPattern":"","allowPrivateClassPropertyAccess":false,"allowProtectedClassPropertyAccess":false,"allowIndexSignaturePropertyAccess":false} should NOT have additional properties.

    at ConfigValidator.validateRuleOptions (/private/tmp/eslint-15988-repro/node_modules/@eslint/eslintrc/dist/eslintrc.cjs:2027:23)
    at /private/tmp/eslint-15988-repro/node_modules/@eslint/eslintrc/dist/eslintrc.cjs:2082:18
    at Array.forEach (<anonymous>)
    at ConfigValidator.validateRules (/private/tmp/eslint-15988-repro/node_modules/@eslint/eslintrc/dist/eslintrc.cjs:2079:34)
    at ConfigValidator.validateConfigArray (/private/tmp/eslint-15988-repro/node_modules/@eslint/eslintrc/dist/eslintrc.cjs:2205:18)
    at CascadingConfigArrayFactory._finalizeConfigArray (/private/tmp/eslint-15988-repro/node_modules/@eslint/eslintrc/dist/eslintrc.cjs:3947:23)
    at CascadingConfigArrayFactory.getConfigArrayForFile (/private/tmp/eslint-15988-repro/node_modules/@eslint/eslintrc/dist/eslintrc.cjs:3753:21)
    at FileEnumerator._iterateFilesRecursive (/private/tmp/eslint-15988-repro/node_modules/eslint/lib/cli-engine/file-enumerator.js:446:49)
    at _iterateFilesRecursive.next (<anonymous>)
    at FileEnumerator.iterateFiles (/private/tmp/eslint-15988-repro/node_modules/eslint/lib/cli-engine/file-enumerator.js:297:49)
```

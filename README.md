# Reflection AI code guidelines
This document identifies settings necessary to ensure a consistent code style across all Reflection AI projects and to ensure engineering and design that conforms to our uncompromisingly high standards. 

## Type checking
### python
We use `pylance` for type-checking. This utility comes bundled with the `Python` extension for `VSCode`. To enable type-checking, ensure that you have downloaded the Python extension and add the following to your `settings.json` file:
```json
{
    "python.languageServer": "Pylance",
    "python.analysis.typeCheckingMode": "strict"
}
```

### typescript
First, reflectionai projects will all use typescript instead of javascript. Ensure that you install the npm `typescript`` package. Typescript can then be checked using
```bash
npx tsc
```

## Autoformatting
### python
All python code will be indented two spaces with 80 characters per line. To ensure this, projects will include a .styles.yapf file with the following contents:
```yapf
[style]
indent_width = 2
column_limit = 80
```
In addition, contributors will install the `yapf` extension for `VSCode` and add the following to their `settings.json` file:
```json
{
    "editor.defaultFormatter": "eeyore.yapf",
}
```

### typescript
All typescript and json code will be formatted using `prettier`, again using 80 characters per line. To ensure this, the following may be included in `package.json`:
```json
{
  "prettier": {
    "printWidth": 80
  }
}
```
`prettier` may be installed using npm.
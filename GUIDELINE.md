# Guidelines for Developing Thingweb Components

While developing new components in Eclipse Thingweb, we try to follow some basic rules to achieve consistency.
These are split into categories.

## Folder Names

Thingweb components use the following notation for folder names based on the programming language:

- JavaScript and TypeScript:
  - examples
  - src
  - test
  - binding-myprotocol
- Dart:
  - lib
  - binding_myprotocol

## File Names

Thingweb components use the following file name pattern based on the programming language:

- JavaScript and TypeScript: kebab case, i.e. my-file-is-here.js
- Dart: snake case, i.e. my_file_is_here.dart

## Linting

Thingweb components use the following linters based on the programming language:

- JavaScript and TypeScript: <https://www.npmjs.com/package/eslint>
- Dart: <https://pub.dev/packages/lint>

## Formatting

Thingweb components use the following formatters based on the programming language:

- JavaScript and TypeScript: <https://prettier.io/>

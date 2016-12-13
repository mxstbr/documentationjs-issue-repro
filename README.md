This is a reproduction for [issue #630](https://github.com/documentationjs/documentation/issues/630) of documentation.js. It contains a stupid module that doesn't do anything with `import/export` syntax to demonstrate the problem.

## How to reproduce

1. Run `npm run docs:notheme`, which runs the `documentation` command without specifying any theme, thusly using the standard theme. **This works perfectly fine**
2. Run `npm run docs:theme`. This runs the exact same command as above, except it also adds `--theme ./default-theme`. (`./default-theme` is a copy and paste of the `default-theme` folder in the `documentation` repo) **This fails**, because it complains "SyntaxError: Unexpected token import" in `src/index.js`

The expected behaviour for `npm run docs:theme` would be to do the exact same thing as `npm run docs:notheme`, as the only difference is that we're explicitly using the default theme instead of implicitly by not passing an argument.

As you can see, providing a custom theme for some reason breaks on the ES6 `import/export` syntax and I'm not sure why.

## License

Licensed under the MIT License, Copyright ©️ 2016 Maximilian Stoiber.

# get-package-json 

Get a package.json, from either a npm registry or github

## Installation

Download node at [nodejs.org](http://nodejs.org) and install it, if you haven't already.

```sh
npm install get-package-json --save
```

## Usage

```js
import getPackageJson from 'get-package-json';

// can be a git url
getPackageJson('git+https://github.com/kesla/get-package-json.git')
  .then(packageJson => {
    console.log('packageJson', packageJson);
  });

// can be a npm arg
getPackageJson('get-package-json@latest')
  .then(packageJson => {
    console.log('packageJson', packageJson);
  });

// can also load a cached version
const cached = getPackageJson.cached();
cached('git+https://github.com/kesla/get-package-json.git')
  .then(packageJson => {
    console.log('packageJson', packageJson);
    cached('git+https://github.com/kesla/get-package-json.git')
      .then(packageJson => {
        console.log('cached package.json', packageJson);
      });
  });

```

## Tests

```sh
npm install
npm test
```

## Dependencies

- [get-package-json-from-github](https://github.com/kesla/get-package-json-from-github): Get package.json from github
- [get-package-json-from-registry](https://github.com/kesla/get-package-json-from-registry): Get package.json from registry, cached
- [npm-package-arg](https://github.com/npm/npm-package-arg): Parse the things that can be arguments to `npm install`

## Dev Dependencies

- [babel-cli](https://github.com/babel/babel/tree/master/packages): Babel command line.
- [babel-core](https://github.com/babel/babel/tree/master/packages): Babel compiler core.
- [babel-preset-es2015](https://github.com/babel/babel/tree/master/packages): Babel preset for all es2015 plugins.
- [babel-tape-runner](https://github.com/wavded/babel-tape-runner): Babel + Tape for running your ES Next tests
- [package-json-to-readme](https://github.com/zeke/package-json-to-readme): Generate a README.md from package.json contents
- [semistandard](https://github.com/Flet/semistandard): All the goodness of `feross/standard` with semicolons sprinkled on top.
- [snazzy](https://github.com/feross/snazzy): Format JavaScript Standard Style as Stylish (i.e. snazzy) output
- [tapava](https://github.com/kesla/tapava): the syntax of ava, run through tape


## License

MIT

_Generated by [package-json-to-readme](https://github.com/zeke/package-json-to-readme)_

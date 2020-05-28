# makit-tsc
![Language](https://img.shields.io/badge/-TypeScript-blue.svg)
[![Build Status](https://travis-ci.org/searchfe/makit-tsc.svg?branch=master)](https://travis-ci.org/searchfe/makit-tsc)
[![Coveralls](https://img.shields.io/coveralls/searchfe/makit-tsc.svg)](https://coveralls.io/github/searchfe/makit-tsc)
[![npm package](https://img.shields.io/npm/v/makit-tsc.svg)](https://www.npmjs.org/package/makit-tsc)
[![npm downloads](http://img.shields.io/npm/dm/makit-tsc.svg)](https://www.npmjs.org/package/makit-tsc)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

makit-tsc

## Install

```bash
npm i makit-tsc --save-dev

```

## Get Start

In the following code, ctx is the context of [makit](https://github.com/searchfe/makit).

```
const compiler = new CustomCompiler({
    baseDir: `${__dirname}/src2`,
    outDir: `${__dirname}/src2/dist`
});

await compiler.compile(ctx);
```

Add a plugin

```

interface Plugin {
    getDepencies?: (context: PluginContext) => string[]
    beforeMakeDepencies?: (filePaths: string[], baseDir: string, outDir: string) => string[]
    onPreCompile?:  (context: PluginContext) => string
    afterCompile?:  (context: PluginContext) => string
    onDest?: (context: PluginContext) => boolean
}

const plugin: Plugin = {
    // ...
}

compiler.addPlugin(plugin);

```



## API

[API DOC](https://searchfe.github.io/makit-tsc/)

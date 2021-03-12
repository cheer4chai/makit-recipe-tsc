# makit-recipe-tsc
![Language](https://img.shields.io/badge/-TypeScript-blue.svg)
[![Build Status](https://travis-ci.org/searchfe/makit-recipe-tsc.svg?branch=master)](https://travis-ci.org/searchfe/makit-recipe-tsc)
[![Coveralls](https://img.shields.io/coveralls/searchfe/makit-recipe-tsc.svg)](https://coveralls.io/github/searchfe/makit-recipe-tsc)
[![npm package](https://img.shields.io/npm/v/makit-recipe-tsc.svg)](https://www.npmjs.org/package/makit-recipe-tsc)
[![npm downloads](http://img.shields.io/npm/dm/makit-recipe-tsc.svg)](https://www.npmjs.org/package/makit-recipe-tsc)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

makit-recipe-tsc

## Install

```bash
npm i makit-recipe-tsc --save-dev

```

## Get Started

A [makit](https://github.com/searchfe/makit) recipe for handling TypeScript compilation workflow. 

### Compile

In the following code, ctx is the context of [makit](https://github.com/searchfe/makit).

```
import {Compiler} from 'makit-recipe-tsc';

const compiler = new Compiler({
    baseDir: `${__dirname}/src2`,
    outDir: `${__dirname}/src2/dist`,
    configPath: `${__dirname}/src2/tsconfig.json`
});

await compiler.compile(ctx);
```

### Add plugins

plugins give users the opportunity to add their own code at specific stages

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

await compiler.compile(ctx);

```



## API

[API DOC](https://searchfe.github.io/makit-recipe-tsc/)

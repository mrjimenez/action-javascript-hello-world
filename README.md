# Learning to write a javascript action <!-- omit in toc -->

## Introduction

[Creating a JavaScript action](https://docs.github.com/en/actions/sharing-automations/creating-actions/creating-a-javascript-action)

## Actions Toolkit Repository

[actions/toolkit repository](https://github.com/actions/toolkit)

## Steps

```bash
$ git clone git@github.com:mrjimenez/action-javascript-hello-world.git
$ cd action-javascript-hello-world
$ nvm use stable
Now using node v20.18.1 (npm v10.8.2)
$ npm init -y

# Install the actions toolkit package
npm install @actions/core
npm install @actions/github

# Commit. Node modules must be in
git add action.yml index.js node_modules/* package.json package-lock.json README.md
git commit -m "My first action is ready"
git tag -a -m "My first action release" v1.1
git push --follow-tags

# Use vercel ncc
npm i -g @vercel/ncc
ncc build index.js --license licenses.txt

```

## Readme Template

### Hello world javascript action

This action prints "Hello World" or "Hello" + the name of a person to greet to the log.

#### Inputs

### `who-to-greet`

**Required** The name of the person to greet. Default `"World"`.

## Outputs

### `time`

The time we greeted you.

## Example usage

```yaml
uses: actions/hello-world-javascript-action@e76147da8e5c81eaf017dede5645551d4b94427b
with:
  who-to-greet: 'Mona the Octocat'
```

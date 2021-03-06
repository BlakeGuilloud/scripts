# av1-scripts


[![Build Status](https://travis-ci.org/av1-io/scripts.svg?branch=master)](https://travis-ci.org/av1-io/scripts) [![NPM version](https://img.shields.io/npm/v/av1-scripts.svg)](https://www.npmjs.com/package/av1-scripts)
[![styled with prettier](https://img.shields.io/badge/styled_with-prettier-ff69b4.svg)](#badge)

## Deployment Scripts for AV1

### React App - website
The AV1 website was bootstraped with the create-react-app cli and is hosted in an S3 Bucket.

To automate the deployment process, I have built a simple node script to push all files in the `./build` directory to the `av1.io` bucket.

The script assumes that the user's `cwd` has a `./build` directory with all of the base file structure that comes with an optimized create-react-app build.

#### Requirements
1. A profile called `av1` in your `~/.aws/credentials` that contains AWS keys with proper S3 permissions associated.

#### Installation:
```
$ npm install av1-scripts -g
```

#### Usage:
```
$ av1 deploy reactApp
```
The script also accepts optional arguments of `bucket` and AWS `profile` in the case that you want to deploy a different create-react-app project.
```
$ av1 deploy [deploymentType] [bucketName] [profile]
```

```
$ av1 deploy reactApp myAwesomebucket default
```

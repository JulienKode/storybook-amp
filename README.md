# Storybook AMP &middot; [![npm package](https://img.shields.io/npm/v/storybook-amp?color=green&label=npm&style=flat-square)](https://www.npmjs.com/package/storybook-amp) ![Libraries.io dependency status for GitHub repo](https://img.shields.io/librariesio/github/prototypearea/storybook-amp?style=flat-square)

Storybook addon that allows you to display [AMP HTML](https://amp.dev/) components generated with react in your stories

## Installation

```sh
npm install -D storybook-amp
```

## Configuration

Then create a file called `addons.js` in your storybook config.

Add following content to it:

```js
import 'storybook-amp/register';
```

## Demo

https://storybook-amp.netlify.com

## Usage

To SSR the code at runtime time use the `withAmpReactSsrDecorator` decorator inside `config.js` or specific story.  To set custom settings, use the  `amp`  parameter. 

```js
// config.js
import { configure, addDecorator, addParameters } from '@storybook/react';
import { withAmpReactSsrDecorator } from 'storybook-amp';

const customStyles = ''; // some styles

// global
addDecorator(withAmpReactSsrDecorator)
addParameters({
  amp: {
    isEnabled: true,
    styles: customStyles, // Custom styles from some string
  },
});
```

You can use the `amp` parameter to override settings on each story individually:

```js
// per story
storiesOf('AMP', module)
  .add('Default', () => <Button>Send</Button>, {
    amp: {
      isEnabled: false,
    }
  });
  ```

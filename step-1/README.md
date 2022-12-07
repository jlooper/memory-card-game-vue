# Step 1: Get to know your app
In your code editor, open the `public/index.html` file. Update the `<title>` of your game to your preference.

Note that the `body` of this file contains two HTML elements: a `div` with an `id="app"`.

Open the file `App.vue`. This is the top-level *Single File Component* (SFC, or a `.vue` file) of your new Vue app. When your project is running, `App.vue` will _mount_ to the DOM in your `index.html` file by attaching to `<div id="app"></div>`.

Notice inside of `App.vue` that there are 3 top-level HTML elements:
`<script>`, `<template>`, and `<style>`. These 3 elements will work together within the SFC as if they were your standard `script.js`, `index.html`, and `style.css` files.

In the `<script>` tag of `App.vue`, you will see two file `import`s:
```js
import HelloWorld from "./components/HelloWorld.vue";
```
This is telling the Vue compiler that within this `App.vue` SFC, you want to use a _child component_, `HelloWorld.vue`, which is found in the `components` directory in the project.

You will see this child component used inside the `<template>` tag as if they were their own HTML element tags:

```html
<HelloWorld msg="Hello Vue 3 in CodeSandbox!" />
```
```html
<TheWelcome />
```

Notice the syntax here! The SFC filenames and the HTML tags that represent them are using *Pascal Casing* - each individual word in the name starts with a captial letter, and there are no spaces. This is a standard syntax styling for JavaScript frameworks that help you visually recognize what is a _child component instance_ rather than a standard HTML tag.

Look at the _component instance_ of `HelloWorld`:
```html
<HelloWorld msg="Hello Vue 3 in CodeSandbox!" />
```
This has an _attribute_ of `msg="You did it!"`. The attribute `msg` here is not an HTML attribute, but an attribute that is specific to the `HelloWorld.vue` SFC. We call these *props*.

`msg` is a variable property that can be read inside of the `HelloWorld.vue` component. If you look at your app running in the browser in CodeSandbox, you will see the `<h1>` tag that reads *Hello Vue 3 in CodeSandbox!*.

Open up the `HelloWorld.vue` file in your code editor. At the middle of this file you will see a `script` tag:
```html
<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>
```
Note here that `msg` is a property of an object that is being passed as a property. 

> Props are passed down, events are passed up

When the `HelloWorld.vue` component is setup by the Vue compiler, this child component is called from a _parent component_ (in this case `App.vue`), with a `msg` property (which looks like an HTML attribute: `<HelloWorld msg="" />`). The value being passed as the `msg` will be a string.

In your `App.vue` file, change the value of the `msg` prop inside the `<HelloWord>` tag, like this:
```html
<HelloWorld msg="I am learning Vue!" />
```
Save this change and preview the app now in your browser.
Thanks to _Hot Module Reloading_ (HMR), the change is instant in the browser once it is saved. You don't need to reload the page!

You should now see your app's `<h1>` tag as reading *I am learning Vue!*.

Now on to [Step 2](/step-2).

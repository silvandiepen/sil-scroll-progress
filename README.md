# Scroll Progress

You know that bar on top of a screen, or sometimes in the bottom where you see how far you scrolled? So, not the regular scrollbar but just a bar to show the progress.

That is what this is. 

### Install

Install the package
`npm install @sil/scroll-progress`

Import the package

`import ScrollProgress from '~/@sil/scroll-progress`

Define the component:

```js
export default {
	components: {
		ScrollProgress
	}
}
```

Use the component:

```html
<template>
	<div>
		<scroll-progress></scroll-progress>
	</div>
</template>
```
Use the component with non-default settings:

```html
<template>
	<div>
		<scroll-progress height="10px" background-color="red" color="white"></scroll-progress>
	</div>
</template>
```

### Props

#### height
set `height` to give the element a different height.

default: `3px`

#### backgroundColor
`backgroundColor` sets the color behind the bar. This is not the color of the progress bar itself but its container.

default: `transparent`

#### color
`color` is the color of the scrollbar. 

default: `black`

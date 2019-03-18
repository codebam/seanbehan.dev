---
layout: post
title: Professional websites using Jekyll and GitHub Pages
---
<div class="message">
  This is a beginner friendly workshop that will walk you through making
  professional websites and blogs using the Jekyll static site generator.  Show
  off your results online using interactive graphs, diagrams, and LaTeX
  equations.
</div>

## What you'll need

- A laptop or tablet of some sort to type on
- A **modern** web browser

---

### Login to GitHub

1. Make a GitHub account if you don't already have one <https://github.com>
1. Fork my repository <https://github.com/codebam/layman>

### Set up your website

1. Rename your repository to `your-username.github.io`
1. Edit `_config.yml` and enter your own details
1. Continue reading this tutorial on your new website at
   <https://your-username.github.io>

### Populate your about section

1. Open `about.md` and enter your own details

### Write a new blog post

1. Create a new file in `_posts` called `2019-03-24-my-first-post.md`
1. Put this at the top of your new file (feel free to copy and paste)

```
---
layout: post
title: My First Post
---
```

### Add some content

```
$$
\text{We can do inline }\LaTeX \text{ in our blog posts} \\
\frac{1}{2}
$$
```

$$
\text{We can do inline }\LaTeX \text{ in our blog posts} \\
\frac{1}{2}
$$

### Inline JavaScript

Or we can include external javascript to make charts for us!

First we import the library we want to use.

``` html
{% raw %}
<script src="https://cdn.jsdelivr.net/npm/frappe-charts@1.1.0/dist/frappe-charts.min.iife.js"></script>
{% endraw %}
```

{% raw %}
<script src="https://cdn.jsdelivr.net/npm/frappe-charts@1.1.0/dist/frappe-charts.min.iife.js"></script>
{% endraw %}

Then we use it!

``` html
<div id="frost-chart"></div>

<script>
let chart = new frappe.Chart( "#frost-chart", { // or DOM element
	data: {
	labels: ["12am-3am", "3am-6am", "6am-9am", "9am-12pm",
		"12pm-3pm", "3pm-6pm", "6pm-9pm", "9pm-12am"],

	datasets: [
		{
			name: "Some Data", chartType: 'bar',
			values: [25, 40, 30, 35, 8, 52, 17, -4]
		},
		{
			name: "Another Set", chartType: 'bar',
			values: [25, 50, -10, 15, 18, 32, 27, 14]
		},
		{
			name: "Yet Another", chartType: 'line',
			values: [15, 20, -3, -15, 58, 12, -17, 37]
		}
	],

	yMarkers: [{ label: "Marker", value: 70,
		options: { labelPos: 'left' }}],
	yRegions: [{ label: "Region", start: -10, end: 50,
		options: { labelPos: 'right' }}]
	},

	title: "My Awesome Chart",
	type: 'axis-mixed', // or 'bar', 'line', 'pie', 'percentage'
	height: 300,
	colors: ['purple', '#ffa3ef', 'light-blue'],

	tooltipOptions: {
		formatTooltipX: d => (d + '').toUpperCase(),
		formatTooltipY: d => d + ' pts',
	}
  });
</script>
```

{% raw %}
<div id="frost-chart"></div>

<script>
let chart = new frappe.Chart( "#frost-chart", { // or DOM element
	data: {
	labels: ["12am-3am", "3am-6am", "6am-9am", "9am-12pm",
		"12pm-3pm", "3pm-6pm", "6pm-9pm", "9pm-12am"],

	datasets: [
		{
			name: "Some Data", chartType: 'bar',
			values: [25, 40, 30, 35, 8, 52, 17, -4]
		},
		{
			name: "Another Set", chartType: 'bar',
			values: [25, 50, -10, 15, 18, 32, 27, 14]
		},
		{
			name: "Yet Another", chartType: 'line',
			values: [15, 20, -3, -15, 58, 12, -17, 37]
		}
	],

	yMarkers: [{ label: "Marker", value: 70,
		options: { labelPos: 'left' }}],
	yRegions: [{ label: "Region", start: -10, end: 50,
		options: { labelPos: 'right' }}]
	},

	title: "My Awesome Chart",
	type: 'axis-mixed', // or 'bar', 'line', 'pie', 'percentage'
	height: 300,
	colors: ['purple', '#ffa3ef', 'light-blue'],

	tooltipOptions: {
		formatTooltipX: d => (d + '').toUpperCase(),
		formatTooltipY: d => d + ' pts',
	}
  });
</script>
{% endraw %}

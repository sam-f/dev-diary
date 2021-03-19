# HTML Image attributes

## Width and height

Get CLS improvements by setting width/height on your image attributes

```html
<img height="1000" width="4000" />
```

the importance is not the actual number, rather the aspect ratio. The browser uses this to reserve space, meaning less content shift on load.

## Loading

Get perf increases by setting loading to equal `lazy`

```html
<img loading="lazy">
```

this works well with height and width, reducing cls and increasing page load speed. Only supported in modern browsers.
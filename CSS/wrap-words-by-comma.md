There are many ways to achieve this:

* `span` tag with CSS rule `white-space: nowrap` is a bit verbose but also reliable way:
  
```HTML
<div class="">
  <span>God’s lioness,</span> <span>How one we grow,</span> <span>Pivot of heels and knees!—The furrow</span>
</div>
```
```CSS
span { white-space: nowrap; }
```

* `<nobr>` markup can also work:

```HTML
<div class="">
  <nobr>God’s lioness,</nobr> <nobr>How one we grow,</nobr> <nobr>Pivot of heels and knees!—The furrow</nobr>
</div>
```

* For Chinese characters, `word-break: keep-all` will treat CJK as non-CJK, which means the text will only break at spaces or punctuations. It works like a charm for Chinese poems.

source: [Where Lines Break is Complicated. Here’s all the Related CSS and HTML.](https://css-tricks.com/where-lines-break-is-complicated-heres-all-the-related-css-and-html/)
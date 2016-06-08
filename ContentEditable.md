# Notes &amp; Resources on ContentEditable

## Articles &amp; Blog Posts

* [Why ContentEditable is Terrible](https://medium.engineering/why-contenteditable-is-terrible-122d8a40e480#.9tiaal7bc) by Nick Santos; Medium.com, May 14, 2014

* [ContentEditable: The Good, the Bad and the Ugly](https://medium.com/content-uneditable/contenteditable-the-good-the-bad-and-the-ugly-261a38555e9c#.a6bmsi511) by Piotrek Koszuliński, CKEditor lead developer; Medium.com, Aug. 13, 2015

* [Fixing ContentEditable](https://medium.com/content-uneditable/fixing-contenteditable-1a9a5073c35d#.hgyzapq3w) by Piotrek Koszuliński, CKEditor lead developer; Medium.com, Aug. 21, 2015

* [The Road to HTML 5: contentEditable](https://blog.whatwg.org/the-road-to-html-5-contenteditable) by Mark Pilgrim; WHATWG Blog, Mar. 6, 2009

## W3C Resources

* [ContentEditable](https://w3c.github.io/editing/contentEditable.html) W3C Editor's Draft 26 May 2016

* [Editing Explainer](https://w3c.github.io/editing/editing-explainer.html) W3C Document 26 May 2016

## Notes

### Article: &lsquo;Why ContentEditable is Terrible&rsquo;

#### Axioms for WYSIWYG editing

1. Well-behaved content: There are many ways to mark up text content with styling and produce the same visual result. Example: Using combinations of <code>em</code> &amp; <code>strong</code>. With content, we have a _many-to-one_  DOM-to-visible mapping.

2. Well-behaved selection: One visible selection can have many DOM representations _and_ one DOM selection can have multiple visual representations. With selection, we have a _many-to-many_ DOM-to-visible mapping (even messier).

3. Closed and complete edits: Implies consistent results across browsers. Example: Pasting text created in one editor (or <code>contenteditable</code> field) into another editor or field.

#### Conclusions

1. A native <code>contenteditable</code> element violates all three axioms.

2. Embedded HTML editors employ many workarounds to compensate for inconsistencies across the range of <code>contenteditable</code> implementations within browsers.

### Other Conclusions

At some point in the future, if and when <code>contenteditable</code> is significantly modified and improved as outlined in the W3C documents listed above, the best course of action, _then_, might be to build an accessible authoring tool that would work across browsers, a prime example being an enhanced version of the OneNet editor.

For the present, it seems that the only viable choice, given the goals we have discussed, is to add the OneNet editor features to an existing HTML-embeddable editor which has already dealt with the complexities inherent in the various implementations of <code>contenteditable</code> across popular browsers.

As noted in the articles by Piotrek Koszuliński, CKEditor lead developer, even though <code>contenteditable</code> is &lsquo;broken&rsquo;, it is best to use it as a baseline, and then build in features and workarounds as needed. In other words, he advises against scrapping <code>contenteditable</code> altogether and trying to build an embeddable WYSIWYG editor from scratch.

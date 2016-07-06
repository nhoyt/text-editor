## What is the conceptual model for text editing in a WYSIWYG editor?

### Toolbar: standard operations w/ icon buttons
* Cut
* Copy
* Paste
* ------
* Undo
* Redo

### Change block formatting
Place cursor in a block of text (e.g. paragraph, possibly empty) and insert (if empty) or change it to:

* Heading
* List (operates at the item level?)
* Quotation (blockquote)
* Paragraph (normal)

### Insert formatted block
Only operates on an empty paragraph? (use case: place cursor within heading or list item?)

* Image
* Table

### Insert/Edit inline element
* Link
* Image???
* Bold/ Italic/ Strikethrough

### Add inline style (based on selection or insertion point)
* Bold
* Italic
* Monospaced

IDEA: Option (toolbar toggle button) to show block structure: Outlines each block and labels what it is, e.g.,
Heading 2, Bulleted list, Blockquote, etc.

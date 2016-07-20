## Conceptual model for creating accessible documents using an HTML-embedded WYSIWYG editor
Objective: create a conceptual model for users that:

* is simple to understand;
* improves the user experience (fewer frustrations, easier to select the appropriate task);
* provides a framework for thinking about, and working with, documents as a sequential collection of block elements;
* results in a document with "baked-in" accessibility features.

Based on concepts and functionality of the OneNet editor created for DHS, State of Illinois.

### OBJECTS
* document
* block (paragraph, heading, secondary)
* compound block (list, image/figure, table)
* text (sequence of characters within a block)
* vertical separator (automatically inserted between blocks, making them both semantically and visually distinct)

#### BLOCK TYPES
* paragraph
* heading
* list
* link
* image
* table

#### ATTRIBUTES
* block format
* inline format

### CONTAINMENT HIERARCHY
* document
    * block (simple)
        * block format
            * paragraph (after: paragraph)
            * heading (after: paragraph)
            * blockquote (after: paragraph)
            * address (after: paragraph)
            * ...
        * text
            * inline format
                * normal
                * bold
                * italic
                * link
                * ...
    * compound block
        * list (bulleted, numbered)
            * list item (after: list item)
        * figure
            * image
                * alt text
            * caption (optional)
        * table
            * table row (after: table row)
    * vertical separator

### TASKS/ACTIONS
* set/edit document properties (e.g., title)
* add/modify/delete text
* insert/change block style (insertion point determines block upon which operation acts)
* insert/change inline style (insertion point or text selection determines where text will be inserted or changed)

### GENERALIZED ACTIONS
* Cut
* Copy
* Paste
* ------
* Undo
* Redo

## NOTES FROM PREVIOUS VERSION

### Change block formatting
Place cursor in a block of text (e.g. paragraph, possibly empty) and insert (if empty) or change it to:

* Heading
* List (operates at the item level?)
* Quotation (blockquote)
* Paragraph (normal)

Can also select multiple consecutive blocks and change all of them to:

* Headings (of a specified level)
* List items
* Quotations
* Paragraphs (normal)

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

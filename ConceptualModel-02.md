# Conceptual Model v4.0

This document presents a vocabulary that relates to users' task domain when using
a text-editor. It attempts to provide terminology for the objects, attributes and
available actions that map to users' tasks when creating or editing a document.

## BLOCK OBJECTS/ATTRIBUTES

### heading
* level (2 - 6)
* content: text/inline

### paragraph
* content: text/inline

### list
* list style
* title (optional)
* content: list items

### list item
* indent level (0 - 5)
* content: text/inline

### table
* number of columns
* number of rows
* column header labels
* row header labels
* title (optional)
* long description (optional)
* content: data cells

### table data cell
* content: text/inline, blocks (excluding table, others?)

### image
* alt text
* long description (optional)
* width and height?
* content: image (from file/library)

### video
* title
* content: video (from file/library)

### audio
* title
* content: audio (from file/library)

### block quote
* content: headings, paragraphs, lists, images

## TEXT/INLINE OBJECTS/ATTRIBUTES

### text
* content: printable characters/permitted inline objects

### link
* href
* content: text/inline

### image
* alt text
* content: image (from file/library)

## ACTIONS

### block actions
* insert block (at top level of parent context -- see notes)
* select block and modify its properties (how to select table?)
* convert existing block to another type of block
* delete block (for some block types, must delete contents)

### text/inline actions
* add/modify/delete text
* add/modify/delete styling
* insert/modify/delete inline object (link, image)

### object-specific block actions

#### heading
* change level

#### list
* change list style (choices among bullets and numbers)
* add/modify/delete title
* users interact with list items; editor considers all contiguous list items
  part of the same list

#### list item
* indent/outdent

#### table
* add/delete column
* add/delete row
* modify column headers and/or row headers
* add/modify/delete title
* add/modify/delete long description
* merge data cells

### object-specific inline actions

#### link
* modify href

#### image
* modify alt text


## NOTES ON ACTIONS

### block actions vs. text/inline actions
* Need to make a clear distinction between text/inline actions and block actions.
* For example, for all of the block objects that contain text/inline, all of the
  text/inline actions are available, and thus can be factored out when
  considering the available actions on a particular block.
* Need to encourage/prioritize block actions (insert block, convert to another
  block) over text/inline styling actions.

### block insertions and splits
* A block can only be inserted at the top level of the parent context, which may
  be (1) the document, (2) a table data cell or (3) a block quote (others?).
* A paragraph can be split into two paragraphs using the enter key.
* A list can be split into two lists using the enter key twice in succession.
* These actions are necessary in order to insert a block, i.e. the user is not
  permitted to insert a block within a paragraph or list.
* Likewise, tables need a mechanism for splitting into two tables.
* In general, blocks need to maintain their integrity (you can't easily demolish
  them by inserting random blocks within them) but must also be easily divided.

### block selection, conversion and deletion
* Need to make it clear how blocks are selected, to allow modification of their
  properties, and what needs to happen in order to delete them.
* For example, a paragraph can be converted to a heading or list item by placing
  the cursor at the beginning, end or anywhere in between and choosing action.
* On the other hand, a paragraph can be deleted only by deleting all of its
  text/inline content. A list can be deleted only by deleting all of its list
  items, and list items are deleted by deleting their text/inline content.

## RELATIONSHIPS

* **simple block** (heading, paragraph, list item) contains text/inline only
* **compound block** (list, table, table column, table row) contains sub-blocks
  (list items, data cells)
* **table data cell** is a hybrid -- may contain text/inline or blocks (e.g.
  paragraphs, list/list items)
* **image** is unique -- no visible text is required (optional caption?) but
  must have alt text (short description) and may have long description

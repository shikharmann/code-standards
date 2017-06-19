# HTML Code Standards

## Table of Contents
* [Semantics](#semantics)
* [Multimedia Fallback](#multimedia-fallback)
* [General Formatting](#general-formatting)
* [HTML Quotation Marks](#html-quotation-marks)
* [Inline-Styles](#inline-styles)
* [Anchor tags & Buttons](#anchor-tags-&-buttons)
* [Further Reading (recommended)](#further-reading)

## Semantics
Use HTML according to its purpose.

Use elements (sometimes incorrectly called “tags”) for what they have been created for. For example, use heading elements for headings, p elements for paragraphs, a elements for anchors, etc.

Using HTML according to its purpose is important for accessibility, reuse, and code efficiency reasons.

```
<!-- Not recommended -->
<button href="/contact">Contact</button>

<!-- Recommended -->
<a href="/contact">Contact</a>
```

## Multimedia Fallback

Provide alternative contents for multimedia.

```
<!-- Not recommended -->
<img src="student.png">

<!-- Recommended -->
<img src="student.png" alt="Photo of smiling student">
```

## General Formatting
Independent of the styling of an element (as CSS allows elements to assume a different role per display property), put every block, list, or table element on a new line. Also, indent them if they are child elements of a block, list, or table element.

## HTML Quotation Marks
Use double `("")` rather than single quotation marks `('')` around attribute values.

## Inline-Styles
*Do not* use inline styles. 

## Anchor tags & Buttons
Use an anchor element to link to a new page. Use a button element for app behaviour.

```
  <a href="/new-page">New Page</a>
  <button type="submit">Submit</button>
  
```

## Further Reading
To further the understanding of semantic HTML please make yourself familair with the following:
* [HTML Element Index](https://developer.mozilla.org/en/docs/Web/HTML/Element)
* [HTML Doctor Outlines](http://html5doctor.com/outlines/)


# CSS Code Standards

## Table of Contents
* [Terminology](#terminology)
* [Properties](#properties)
* [Values](#values)
* [Shorthand Properties](#shorthand-properties)
* [Selectors](#selectors)
* [Nesting & Specificity](#nesting-&-specificity)
* [Inline-Styles](#inline-styles)
* [Headings](#headings)
* [Comments](#comments)
* [Variables](#variables)
* [Multiple Selectors](#multiple-selectors)
* [Naming Conventions](#naming-conventions)
* [Further Reading](#further-reading)


## Terminology
Concise terminology used in these standards:

  .selector {
      property: value;
  }

`property: value` makes a declaration. A selector with declarations makes a rule.

## Properties
Every declaration should be on its own line below the opening brace. Each property should:

* have a single soft tab with 2 spaces before the property name 
* a single space before the property value.
* end in a semi-colon.

For example:
```
  .card {
    display: block;
     margin: 20px;     
  }
```


## Values
Shorten hexidecimal color values to 3 digits when possible:

`background: #fff;`

## Shorthand Properties
Use shorthand properties where possible.

```
<!-- Not recommended -->
  card {
    padding-top: 0 
    padding-left: 7px
    padding-right: 7px
    padding-bottom: 7px
  }

<!-- Recommended -->
  card {
    padding: 0 $unit $unit
  }
```



## Selectors
Selectors should be on a single line, with a space after the selector, followed by an opening brace. A selector should end with a closing brace on the next line. Following related selectors should be on the next line with one additional line space between them.

```
  .card__heading {
    display: block;
      margin: 20px;
  }
  
  .card__image {
    width: 100%;
  }
``` 
  
## Nesting & Specificity
Avoid very complex child and descendant selectors. Just like Inception, never go more than 3 levels deep. 
  
```
  /* Wrong */  
  .c-hero div div.container ul li a span 
 ```
  
Nesting selectors the rules more specific, and specificity can make styling very complicated and often is the reason our CSS rules aren't being correctly applied. 

In order to keep specificity low, avoid using IDs in CSS. 

## Inline-Styles
*Do not* use inline styles. 

## Multiple Selectors
Multiple selectors should each be on a single line, with no space after each comma.

```
  .h1,
  .h2 {
    font-family: $open-sans;
  }
```

## Headings
Every file needs a header to describe what the file is for, and subheaders for each subsection. 

/ card.scss
```
  // Card
  // ====
  // 
  // 1. This is where comments will go 
  
  ...
```
  
Subsections are defined for both subcomponent and modifiers

/ card.scss
```
  ...
  
  // Modifiers
  // ---
  //

  .card--red {
    background-color: $red;
  }
  
  
  // Card Slide
  // ---
  // 
  
  .card__slide {
    display: block;
  }
```
  
## Comments
 
Explain code as needed, where possible. Comments go below the closest relating header and should be numbered. 
Comments should be written for anything that might be unclear, as well as anytime you’re positioning something absolute, or using a “magic number”.
```
  .card {
    position: relative;
  }
  
  
  // Card Image
  // ---
  // 
  // 1. Positioned relative to .c-card
  
  .card__image {
    position: absolute // 1.
  }
```
  
## Variables
Variables should be created for anything that is used more than once and should always be stored in `variables.scss`.
Variables should be organzied into subsections with headings. 

## Naming Conventions
Use meaningful or generic ID and class names. Always class names that reflect the purpose of the element in question, or that are otherwise generic. 

Class names are written in **lower case** and with underscores (`_`) or dashes (`-`). 

Use class names that are as short as possible but as long as necessary. Try to convey what a class is about while being as brief as possible. Using class names this way contributes to acceptable levels of understandability and code efficiency.

Avoid qualifying ID and class names with type selectors.
```
<!-- Not recommended -->
  div.card {
    display: block;
  }

```

In order to manage a large codebase with a team of developers, having a set naming convention is necessary to keep the styles and code base managable.

BEM is a naming convention that helps keep you

BEM stands for Block Element Modifier. It provides a way to arrange CSS classes into independent modules. The idea but the most common one looks like this:
```
  .block {}
  .block__element {}
  .block--modifier {}
  .block__element--modifier {}
```

If you need to add an event to an element, add a class preceded with `js-`. Avoid using the same class for both styles and js events. 

To prevent bugs due to class naming, new classes created for templates or components should be preceeded with a `t-` or `c-` respectively. 

## Styles Organization
Since our code base is going to grow and grow, we will strucutre the folders accordingly

  `/templates`
  `/components`
  `/utilities`

Templates are saved in the folder `templates` as partials. The styles for a template called`home`, for example, are in `templates/_home.scss`. Template classes are used if a page needs it's own specific styles that components cannot cover. For example `home`. Other classes within `home` that are part of this template will be sub elements, for example `home__heading`.

Components are styles that have been comportmentalized to be reusable. A button or card component, for example, are frequently used within a web app. Button styles, for example, are like below and saved in `components/_button`.
```
  .button {
    display: block;
    padding: $unit $unit*2;
  }

  .button--primary {
    background-color: $brand-green;
  }
```

Utilities are classes that belong to single CSS rules that can be applied easily to elements, and are saved in `utilities/_color`. For example:
```
  .color-white {
    color: $white;
  }

  .color-green {
    color: $green;
  }
```

It is important to note that the name of the template, component, or utility class and file should be the same. 

## Further Reading

Listed here are resources to help you find a deeper understanding of the above standars. 
* [BEM](http://getbem.com/introduction/)
* [Sitepoint on BEM](https://www.sitepoint.com/bem-smacss-advice-from-developers/)

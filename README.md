# Study Soup Code Standards
The following are the CSS and style organization coding styles that should be conformed to. Following these standards will help keep code clean and organized, will help prevent bugs, and will be more understandable to your fellow developers.


##Table of Contents
* [ HTML ] (#HTML)
* [ CSS ] (#CSS)
* [ Javascript ] (#Javascript)
* [ Ruby ] (#Ruby)
* [ Rails ] (#Rails)


# CSS Code Standards

##Table of Contents
* [Terminology] (#Terminology)
* [Properties] (#Properties)
* [Values] (#Values)
* [Selectors] (#Selectors)
* [Nesting & Specificity] (#Nesting)
* [Headings] (#Headings)
* [Comments] (#Comments)
* [Variables](#Variables)
* [Multiple Selectors] (#Multiple Selectors)
* [Naming Conventions] (#Naming Conventions)
* [Styles Organization] (#Styles Organization)
* [Further Reading] (#Further Reading)


##Terminology
Concise terminology used in these standards:

	.selector {
  		property: value;
	}

`property: value` makes a declaration. A selector with declarations makes a rule.

##Properties
Every declaration should be on its own line below the opening brace. Each property should:

* have a single soft tab with 2 spaces before the property name 
* a single space before the property value.
* end in a semi-colon.

For example:

	.c-card {
	 	display: block;
  		margin: 20px;  		
	}


##Values
Shorten hexidecimal color values to 3 digits when possible:

`background: #fff;`

##Selectors
Selectors should be on a single line, with a space after the selector, followed by an opening brace. A selector should end with a closing brace on the next line. Following related selectors should be on the next line with one additional line space between them.

	.c-card__heading {
		display: block;
  		margin: 20px;
	}
	
	.c-card__image {
		width: 100%;
	}
	
	
##Nesting & Specificity
Avoid very complex child and descendant selectors. Just like Inception, never go more than 3 levels deep. 
	
	/* Wrong */  
	.c-hero div div.container ul li a span 
	
Nesting selectors the rules more specific, and specificity can make styling very complicated and often is the reason our CSS rules aren't being correctly applied. 

In order to keep specificity low, avoid using IDs in CSS. 

##Multiple Selectors
Multiple selectors should each be on a single line, with no space after each comma.

	.h1,
	.h2 {
		font-family: $open-sans;
	}

##Headings
Every file needs a header to describe what it’s about, and subheaders for each subsection. 

/ c-card.scss

	// Card
	// ====
	// 
	// 1. This is where comments will go 
	
	...
	
	
Subsections are defined either by a new subcomponent or modifiers

/ c-card.scss
	
	...
	
	// Modifiers
	// ---
	//

	.c--red {
		background-color: $red;
	}
	
	
	// Card Slide
	// ---
	// 
	
	.c-card__slide {
		display: block;
	}
	
	
##Comments
 
Comments go below the closest relating header and should be numbered. 
Comments should be written for anything that might be unclear, as well as anytime you’re positioning something absolute, or using a “magic number”.

	.c-card {
		position: relative;
	}
	
	
	// Card Image
	// ---
	// 
	// 1. Positioned relative to .c-card
	
	.c-card__image {
		position: absolute // 1.
	}

	
##Variables
Variables should be created for anything that is used more than once and should always be stored in `variables.scss`
Variables should be organzied into subsections with headings. 

##Naming Conventions
In order to manage a large codebase with a team of developers, having a set naming convention is necessary in order to keep the styles and code base managable.

BEM is a naming convention 



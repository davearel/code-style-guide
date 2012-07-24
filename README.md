code-style-guide
================

This document defines formatting and style rules for HTML and CSS. It aims at improving collaboration, code quality, and enabling supporting infrastructure.

# HTML

### Doctype
HTML5 (HTML syntax) is preferred for all HTML documents: 
```html
<!DOCTYPE html>
```

# CSS

### Comments
Well commented code is extremely important. Take time to describe components, how they work, their limitations, and the way they are constructed. Don't leave others in the team guessing as to the purpose of uncommon or non-obvious code.

Comment style should be simple and consistent within a single code base.

- Place comments on a new line above their subject.
- Avoid end of line comments.
- Make liberal use of comments to break CSS code into discrete sections.
- Use "sentence case" comments and consistent text indentation.

```css
/* ==========================================================================
   Section comment block
   ========================================================================== */

/* Sub-section comment block
   ========================================================================== */

/**
 * Short description using Doxygen-style comment format
 *
 * Long description first sentence starts here and continues on this line for a
 * while finally concluding here at the end of this paragraph.
 *
 * The long description is ideal for more detailed explanations and
 * documentation. It can include example HTML, URLs, or any other information
 * that is deemed necessary or useful.
 *
 * @tag This is a tag named 'tag'
 *
 * @todo This is a todo statement that describes an atomic task to be completed
 *   at a later date. It wraps after 80 characters and following lines are
 *   indented by 2 spaces.
 */

/* Basic comment */
```


# Sass

- Try and Limit nesting to 1 level deep. Reassess any nesting more than 2 levels deep. This prevents overly specific CSS selectors.
- Always place @extend statements on the first lines of a declaration block.
- Where possible, group @include statements at the top of a declaration block, after any @extend statements.

```sass
.selector-1 {
    @extend .other-rule;
    @include clearfix();
    @include box-sizing(border-box);
    // other declarations
}
```

### Sass mixins, variables, and other functions
Only utilize mixins, variables, and other sass functions when necessary. Provide scope unless needed globally.

### Seperate css into partials
Split all css files into seperate partials mainly by page or module, and import into one single css file.
For exampes:

```sass
@import 'home';
@import 'contact';
@import 'about';
@import 'portfolio';
@import 'twitter_widget';
...
```
Each partial should contain one wrapper id or class to provide closure to all other selectors:

```sass
#home {

  nav {
    ...
  }

  #logo {
    ...
  }
  
}
```

### Pages
Generally, all pages should be seperated into sass partials.

### Modules
Some page components may be considered more modular than others. These containers should be extracted into their own partials.
```sass
#twitter {
  ul {
    ...
  }
  li {
    ...
  }
}
```


# General

### Whitespace
- Use tabs instead of spaces
- 1 tab = 4 spaces
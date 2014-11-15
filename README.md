##Voyager Front-end Boilerplate

###Overview
This is unapologetically opinionated. We want to keep this as flexible but as maintainable as possible. Principles are derived from [SMACSS](http://smacss.link) and [Atomic Web Design](http://atomic.link). Since one size doesn't fit all when it comes to front-end development, this will be a continuous work in progress.

###Tools
**SCSS + Compass** - CSS Preprocessor
**Foundation Grid** - Responsive Grid
**Reset** - CSS Normalization
**Grunt** - Asset Process Automation
**Autoprefixer** - CSS Prefixer based from CanIUse Database.
**Modernizr** - Feature Checking ( if applicable )

###Sample Structure
    - assets/
         ├── css/
         │   ├── style.css
         ├── favicon.ico
         ├── fonts/
         ├── img/
         ├── js/
         │   ├── bp.main.js
         │   ├── bp.modal.js
         │   ├── vendors/
         │   │   ├── jquery.min.js
         │   │   ├── jquery-cookie.min.js
         └── scss/
             ├── _svg.scss
             ├── base/
             │   ├── _colors.scss
             │   ├── _defaults.scss
             │   └── _reset.scss
             ├── components/
             │   ├── _header.scss
             │   ├── _form.scss
             │   ├── _footer.scss
             │   ├── _modal.scss
             ├── layouts/
             │   ├── _sign-in.scss
             ├── style.scss
             └── vendors/
                 └── foundation/
    - config.rb
    - index.html
    - README.md

Most parts are self-explanatory. However, some files and directories are worth noting.

 - `_colors.scss` is where all color variables are placed. Please refer to the [Colors](#colors) section for naming colors.
  - `_defaults.scss` contains individual elements' default styling.
  - `scss/components/` - contains styles for combinations of elements that can be present on different pages.
  - `layouts/` - contains page-specific styles.

###Styling

#####Colors
Structure colors as `<name>-color-<number>`. ( e.g. `$primary-color-1`, `$secondary-color-3` )
We prefer functional to actual name colors. ( e.g. `$background-color-2` to `green-color-3` ).
Numbers are used to differentiate color variations.
Maximize the use of color functions such as `lighten` and `darken`.

#####Comments
> Code tells how, comments tell why.

If something isn't obvious, don't explain how it's done, explain why.
Comments on closing brackets are required if closures are greater than 25 lines.

#####Media Queries
Media queries should be arranged from smallest to largest viewport.

#####Nesting
No nesting more than 3 levels deep.
`@media` queries and pseudoselectors are not counted as levels.

#####Properties
Property shorthands should be maximized.
`0` and `none` should be used for null values.
Selectors and properties are preferably alphabetized.

#####Selectors
Element selectors, followed by classes and then ID selectors. Preferably alphabetized.
Selectors should be separated by a comma and a line break.

#####Spacing
Two line breaks should be present before each style definition.
A space before the opening bracket is required.

    form,
    .panel {
        background: $background-color-2;
        display: block;

        input[type="text"] {
            display: block;
            font-size: 1.1em;
            width: 100%;

            &:focus {
                border-color: $primary-color-1;
            }
        }

        label {
            font-size: 0.8em;
        }
    }


#####Typography
`body` defines the base font size in `px`. `16px` is the default.
`em` is the standard unit for `font-size` across all elements.
Default `line-height` is `1.4`.

###Scripting
#####Comments
#####Event Handling
    $containingElement.on('click', '.buttons', function(e){
        /* Handle event here */
        e.preventDefault();
    });
#####onReady
Each JS file should be wrapped by the onReady function with the following shorthand.

    ;$(function(){
        /* Do stuff here */
    });
#####Namespacing
#####Variables
camelCase variable and function names.
jQuery object variables should be prefixed by a `$` sign.
An object must be cached if used more than ones.

    $button = $('.button');

###Future
**Module Injection** via Bower
**Dependency Management** via RequireJS
**Project Scaffolding** via Yeoman
**Unit Testing** via Jasmine

------------------------------------
&copy; 2014 [Voyager Innovations Inc.](http://voyagerinnovation.com)
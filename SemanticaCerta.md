## Table of Contents

  1. [HTML](#html)
  2. [CSS](#css) 
  3. [LESS](#less) 

<a name='html'></a>
## HTML
Use HTML5. And use HTML syntax, not XHTML. Hixie wrote some about it.

html
<!--- Bad -->
<br />

<!-- Good -->
<br>

<!-- Good -->
<!doctype html>

<!-- Bad -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

Use soft tabs with two spaces. You can configure your editor for this.

html
<!-- Good -->
<nav class="nav">
  <ul class="nav-menu">
    <li class="nav-item">
      <a class="nav-link">

<!-- Bad-->
<nav class="nav">
      <ul class="nav-menu">
            <li class="nav-item">
                  <a class="nav-link">


### HTML Comments

Follow this rule to add comments in HTML.
html
<!-- This is a good example -->
<!-- /Closing a good example -->



### HTML Attribute Order

HTML attributes should be in this order for facilitate the reading.

1. class
2. id, name
3. data-*
4. src, for, type, href
5. title, alt
6. aria-*, role

html
<a class="..." id="..." data-modal="toggle" href="#">

<input class="form-control" type="text">

<img class="img-rounded" src="..." alt="...">


#### Never use style inline in HTML

html
<a style="color:#CCC;" href="#">


OR

html
  <!--/* Bad */-->
  <section class="teaser">     
  
    <script>
      var teaserConfig = {
         skin: 0;
      };
    </script>
    
    <ul>
      <li>Item</li>
      <li>Item</li>
    </ul>
    
    <style>
      .teaser__title {
        font-size: 12px;
       }
    </style>
    
  </section>


<a name='css'></a>
## CSS

#### CSS Syntax
Use soft tabs with two spaces. You can configure your editor for this.

css
/* Good */
.nav-item {
  display: inline-block;
  margin: 0 5px;
}

/* Bad */
.nav-item {
    display: inline-block;
    margin: 0 5px;
}


Include a single space before the opening brace of a ruleset.

css
/* Good */
.header {
  ...
}

/* Bad */
.header{
  ...
}


Include a single space after the colon of a declaration.

css
/* Good */
.header {
  margin-bottom: 20px;
}

/* Bad */
.header{
  margin-bottom:20px;
}


Keep one declaration per line.

css
/* Good */
.selector-1,
.selector-2,
.selector-3 {
  margin-bottom: 20px;
}

/* Bad */
.selector-1, .selector-2, .selector-3 {
   margin-bottom: 20px;
}


Single declarations should remain in one line.

css 
/* Good */
.selector-1 { width: 50%; }

/* Bad */
.selector-1 {
  width: 50%;
}


Separate each ruleset by a blank line.

css 
/* Good */
.selector-1 { width: 50%; }

/* Bad */
.selector-1 {
  width: 50%;
}


Use lowercase, shorthand hex values and avoid specifying units is zero-values.

css 
/* Good */
.selector-1 {
  color: #aaa;
  margin: 0;
}

/* Bad */
.selector-1 {
  color: #AAAAAA;
  margin: 0px;
}


#### CSS Selectors
Select all 

css 
* {
 margin: 0;
 padding: 0;
}


Select all inner .container

css 
.container * {
 border: 1px solid black;
}


Select first p after ul

css 
ul + p {
 color: red;
}


Select only first child
css 
ul > li {
 color: red;
}


Select all p after ul

css 
ul ~ p {
 color: red;
}

Select attr
css 
a[title] {
 color: green;
}

Select attr with content
css 
a[href="http://www.google.com"] {
 color: #1f6053;  
}

Select has checked
css 
input[type=radio]:checked {
 border: 1px solid black;
}

Select all, but not select <p>
css 
*:not(p) {
color: green;
}


Select child
css 
li:nth-child(3) {
 color: red;
}
 
li:nth-last-child(2) {
 color: red;
}


Select element

css 
ul:nth-of-type(3) {
 border: 1px solid black;
}

ul:nth-last-of-type(3) {
 border: 1px solid black;
}



#### CSS Declaration Order

The declarations should be added in alphabetical order.

css 
/* Good */
.selector-1 {
  background: #fff;
  border: #333 solid 1px;
  color: #333;
  display: block;
  height: 200px;
  margin: 5px;
  padding: 5px;
  width: 200px;
}

/* Bad */
.selector-1 {
  padding: 5px;
  height: 200px;
  background: #fff;
  margin: 5px;
  width: 200px;
  color: #333;
  border: #333 solid 1px;
  display: block;
}


CSS Border

css 
/* Good */
.selector-1 { 
  border: 0;
}

/* Bad */
.selector-1 {
  border: none;
}


#### CSS Class Name

Keep class lowercase and use dashes.

css 
/* Good */
.nav-item { ... }

/* Bad */
.NavItem { ... }
.nav_item { ... }



Dashes serve as natural breaks in related class. Prefix class based on the closest parent or base class.

css 
/* Good */
.navbar { ... }
.nav { ... }
.nav-item { ... }
.nav-link { ... }

/* Bad */
.item-nav { ... }
.link-nav { ... }


Avoid giving too short names for class and always choose meaningful names that provide the class function.
css 
/* Good */
.btn { ... }
.page-header { ... }
.progress-bar { ... }

/* Bad */
.s { ... }
.ph { ... }
.block { ... }


#### CSS Performance


Never use IDs.

css 
/* Good */
.header { ... }
.section { ... }

/* Bad */
#header { ... }
#section { ... }



Do not use selectors standards for not generic rules, always preferably for class.

css 
/* Good */
.form-control { ... }
.header { ... }
.section { ... }

/* Bad */
input[type="text"] { ... }
header
section



Avoid nesting elements, the preference is always to use class.

css 
/* Good */
.navbar { ... }
.nav { ... }
.nav-item { ... }
.nav-link { ... }

/* Bad */
.navbar ul { ... }
.navbar ul li { ... }
.navbar ul li a { ... }


Nest only when need change the class comportament with interference for other class. Keep the nested on max of three elements.

css 
/* Good */
.modal-footer .btn { ... }
.progress.active .progress-bar { ... }

/* Bad */
.modal-btn { ... }
.progress.active .progress-bar .progress-item span { ... }


#### Mobile First and Media Queries

Start the development with generic rules with and add media queries with mobile first.

css 
/* Good */
.navbar {
  margin-bottom: 20px;
}

@media (min-width: 480px) {
  .navbar {
    padding: 10px;
  }
}

@media (min-width: 768px) {
  .navbar {
    position: absolute;
    top: 0;
    left: 0;
  }
}

@media (min-width: 992px) {
  .navbar {
    position: fixed;
  }
}

/* Bad */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
}

@media (max-width: 767px) {
  .navbar {
    position: static;
    padding: 10px;
  }
}


<a name='less'></a>
#### Pre-Processors (LESS)

Provide semantic names for variables.

less 
/* Good */
@brand-primary: #049cdb;

/* Bad */
@color-blue: #049cdb;


Do not nest selectors more than three levels deep!

less 
.page-container {
  .content {
    .profile {
      // STOP!
    }
  }
}


Media queries vars sizes.
less 
- @minmobile : 280px;
- @maxmobile : 767px;
- @mintablet : 768px;
- @maxtablet : 955px;
- @mindesktop: 956px;
- @maxdesktop: 1279px; 


Usage:

less 
height: 50px;

@media screen and (min-width:@minmobile) and (max-width:@maxmobile) {
  height: 70px;
}

@media screen and (min-width:@mintablet) and (max-width:@maxtablet) {
  height: 80px;
}

@media screen and (min-width:@mindesktop) and (max-width:@maxdesktop) {
  height: 200px;
}


Grid columns.
less 
.column(1);
...
.column(12);


#### References
- <a href="https://github.com/airbnb/css">Airbnb CSS / Sass Styleguide</a>
- <a href="http://www.felipefialho.com/coding-style/">Felipe Fialho / My Coding Style</a>
- <a href="https://github.com/diegocard/awesome-html5">Awesome HTML5</a> 
- <a href="https://github.com/sotayamashita/awesome-css">Awesome CSS</a>

# Cuddlefish
Cuddlefish is a rapid prototyping environment for designing-in-browser.

## Team Coding Philosophy

Below is a list of coding considerations when contributing to Cuddlefish.

1. **Small CSS**: Keep our CSS files small and specific with the goal of only including files that address either reusable/utility classes or specific components (or widgets). We'll use the .SCSS flavor of the preprocessor SASS.
  ```
  cuddlefish/
    +-- stylesheets
      +-- plugins
      ¦   +-- animate.css
      ¦   +-- fonts.css
      ¦   +-- grid.css
      ¦   +-- reset.css
      +-- globals
      ¦   +-- utility-classes.scss
      ¦   +-- variables.scss
      +-- components
      ¦   +-- media-object.scss
      +-- widgets
          +-- hero-slideshow-billboard.scss
          +-- super-fun-gallery.scss
          +-- tabbed-list.scss
  ```

2. **Be Specific**: We use [the BEM naming convention](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/) to target elements in our HTML documents.

  ```
  <div class="block__element">
    <div class="block__element--modifier"></div>
  </div>
  ```
  Targeting elements this way addresses most of the concerns listed in [these best practices](https://github.com/sezgi/CSS-Best-Practices) around writing scalabale and reusable CSS.
3. **Practice Object-Oriented CSS**.
4. **Always Be Iterating**: Make small strides to iterate on our CSS Styleguide, as of now, here are some coding constraints we've agreed on as team:
  + Grouping CSS properties logically, or by how they affect the DOM (Document Object Model), in this order: 
    1. **Display properties** (or things that affect the box model of an element or object)
    2. **Type** (things that affect how fonts are displayed and positioned)
    3. **Visual Styles**
    4. **Animations and/or element transitions**
    
    An example: 
    ```
    .block__element--modifier {
      display: block;
      height: $height; 
      width: $width;
      box-sizing: border-box;
      margin: 0 auto;
      
      color: $color;
      font-family: $Open-Sans;
      font-size: 16px; /* Use pixels to specify an element's font-size */
      line-height: 1.5; /* Use integers to specify an element's line-height */
      text-align: center;
      
      background: $bg-color url('images/bg.jpeg');
      background-color: $bg-color;
      background-image: url('images/bg.jpeg');
      background-position: center center;
      background-repeat: no-repeat;
      background-size: cover;
      border: 1px solid $border-color;
    }
    ```
5. **Use Modern Browser fallbacks or vendor prefixes only.**
    +  Let the dev team worry about granular cross-browser compatibility. We should be spending as much of our time as possible on designing in the browser. Keep in mind, though, that you may need to include *certain* vendor prefixes so people can properly view your design progress in the *modern browser* of their choosing. Probably the most important of these properties is `box-sizing`, which we can create an `@include` for in our CSS so that we don't have repeat ourselves too often.


      An example: 

      ```
      /* Without an @include (plain CSS) */
      
      .block__element--modifier {
        -moz-box-sizing: border-box;
        -webkit-box-sizing: border-box;
        box-sizing: border-box;
      }
      
      /* OR, with an @include (SCSS) */
      
      .block__element--modifier {
         @include box-sizing(border-box);
      }
      ```

## Getting Cuddlefish running on your machine

```
$ cd project_directory_where_you_want_Cuddlefish_to_live
$ git clone https://github.com/bux-cuddlefish/bux-cuddlefish.github.io.git cuddlefish
$ cd cuddlefish
$ git pull
```

## Contributing to Cuddlefish

The `gh-pages` branch will serve as our `master` branch and the one that we deploy to "production". To contribute to the project you'll create a branch off of `gh-pages`, make your changes, & submit a pull request comparing your branch to `gh-pages`. To switch to this branch and pull down the latest changes:

```
$ git checkout gh-pages
$ bundle install
$ bundle exec middleman server
```

`bundle install` will install all of our apps dependencies on your machine and `bundle exec middleman server` will start a local server so that you can view pages in your browser.

To start contributing to Cuddlefish create a new branch. Make sure you're branching off of `gh-pages` so we can merge your changes in later. To check which branch you're currently on by running:
```
$ git status
```
You should see the terminal return something like:
```
On branch gh-pages
Your branch is up-to-date with 'origin/gh-pages'.
```
If you need to switch to the `gh-pages` branch, run: 
```
$ git checkout gh-pages
$ git pull origin gh-pages
```
And then to create a new branch:
```
$ git checkout -b your-branch-name
```
You should try to name your branch after an issue you're addressing/fixing or after the widget you'll be designing. 

Once you make changes you want to commit to your branch push your branch up to GitHub:

```
$ git push origin your-branch-name
```

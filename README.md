# Cuddlefish
Cuddlefish is a rapid prototyping environment for designing-in-browser.

## Team Coding Philosophy

Below is a list of coding considerations when contributing to Cuddlefish.

1. **Small CSS**: Keep our CSS files small and specific with the goal of only including files that address either reusable/utility classes or specific components (or widgets).
(insert example of project directory and naming conventions)
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

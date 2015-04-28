# Cuddlefish
Cuddlefish is a rapid prototyping, or designing-in-browser environment, for the ACS Browse UX team.

## Core Coding Philosophy

Below is a list of coding considerations when contributing to Cuddlefish.

1. Small CSS: Keep our CSS files small and specific to a set of reusable/utility classes and components (or, widgets).
(insert example of project directory and naming conventions)
2. Be Specific: We use the BEM naming convention to target elements in our HTML documents.
  ```
  .block__element--modifier {
  }
  ```
3. Practice Object-Oriented CSS.
4. Always Be Iterating: Make small strides to iterate on our CSS Styleguide, as of now, some coding constraints include:
  + Grouping CSS properties logically, or by how they affect the DOM (Document Object Model), in this order; 
    1. Display properties (or things that affect the box model of an element or object)
    2. Type; (things that affect how fonts are displayed and positioned)
    3. Visual Styles
    4. Animations and/or element transitions
    
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

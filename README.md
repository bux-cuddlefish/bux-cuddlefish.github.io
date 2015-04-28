# Cuddlefish
Cuddlefish is a rapid prototyping environment for designing-in-browser.

## Team Coding Philosophy

Below is a list of coding considerations when contributing to Cuddlefish.

1. **Small CSS**: Keep our CSS files small and specific with the goal of only including files that address either reusable/utility classes or specific components (or widgets).
(insert example of project directory and naming conventions)
2. Be Specific: We use the BEM naming convention to target elements in our HTML documents.

  ```
  <div class="block__element">
    <div class="block__element--modifier"></div>
  </div>
  ```
  
3. **Practice Object-Oriented CSS**.
4. **Always Be Iterating**: Make small strides to iterate on our CSS Styleguide, as of now, here are some coding constraints we've agreed on as team:
  + Grouping CSS properties logically, or by how they affect the DOM (Document Object Model), in this order: 
    **1. Display properties (or things that affect the box model of an element or object)**
    **2. Type; (things that affect how fonts are displayed and positioned)**
    **3. Visual Styles**
    **4. Animations and/or element transitions**
    
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

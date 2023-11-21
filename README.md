# Scroll list code challenge

# Challenge Description
In this challenge, you are tasked with creating a 'ScrollList' component for displaying items in an array.
The challenge will require that you work in "ScrollList.vue".

# Requirements

## The ScrollList component should:
  1. Accept the following props
    - 'list' - array, required
    - 'index' - number, default 0
    - 'visibleItems' - number, default 5
  
  2. Display a list
    - Display an li for each element in the 'list' prop
    - Allow the parent component to determine the markup displayed within each list item
  
  3. Have a Root Element with a Set Height
    - The root element's height should be 'visibleItems' multiplied by the clientHeight of a rendered item
    - This allows the component consumer to specify the number of visible items and everything else remains scrolled out of sight
    - You can assume all items are the same height

  4. Scroll Based on the Index Prop
    - The list should be scrolled to the provided index prop.
    - This means, if index 0 is provided the first array element should be at the top of the container.
      If the index is 1 the second element should be at the top, etc
    - If list items towards the end of the list can't rest at the top of the container because
      there is no more space below them, that is ok.
    - Whenever the index prop changes, the list should scroll to the updated index

  5. Focus The List On Page Load
    - Complete the 'vFocus' custom directive to make it work

### PS. Result image see in assets

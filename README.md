# Binary Search explained in PHP

See the code example below:
```tsx
<?php
function binarySearch($Arr, $element) {
    $start = 0;
    $end = count($Arr) - 1;
    
    while($start <= $end) {
        $mid = floor(($start + $end) / 2);
        
        if ( $element == $Arr[$mid] ) {
            return $Arr[$mid];
        } elseif ( $element > $Arr[$mid] ) {
            $start = $mid + 1;
        } else {
            $end = $mid -1;
        }
    }
    return -1;
}

$number = [3,6,8,10,44,56,58,89,90,100,300];

echo binarySearch($number, 58);
```

## #step 1:
We have to define the starting point. Initially, this would be the first index of the array which is 0.
## #step 2:
We have to define the ending point. In this case, the last index of an array would be the total element of the array minus 1. Because array starts with index 0; Which is in PHP count($array) - 1;
## #step 3:
The middle point of an array would be in PHP floor( (start index + end index) / 2 ); This is a simple equation for getting the middle point of the array.
## #step 4:
Now the fun part begins. We have to define a while loop that will loop through the array if the starting point is greater than or equal to the ending point condition is meet. 

**First of all**, we will check if the given element is greater than or equal to the array mid-value is true. If this condition is true then we will return the array mid-value. Because this is the value we are looking for.

**Secondly**, if the element is greater than the value of the array mid-value, then we will reset the starting point to the midpoint with added 1. Because in this case, we know that the left part of the array is useless and the desired value would be in the right part of the array and we want to leave the left portion from the loop.

**Lastly**, if the element is smaller than the value of the array mid-value then we will reset the ending point to the midpoint by subtracting 1. Because the desired value would be the left portion of the array.

If no condition is applied that means we did not find our desire number and we will return -1. Because the number does not exist in the array list.

## Conclution:
This was a simple example to understand the binary search in PHP.

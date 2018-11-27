# javascript algos



#1. Get length of the longest substring without having duplicate letters
Solution: Using Sliding Window Algorithm



var lengthOfLongestString = function (s) {

    var ans=0, i=0, j=0, subString = "", stringLength = s.length;
    
    while(i < stringLength && j < stringLength) {
        //Check for duplicate in the sub string
        if (subString.indexOf(s[j]) < 0) {
            //If the character is not present append it to the substring
            subString = subString.concat(s[j]);
            //Keep taking the longest the answer string length
            ans = Math.max(ans, j-i);
            j++;
        } else {
            //If a duplicate is found start moving the window start index
            subString = subString.substring(1);
            i++
        }
    }
    
    return ans;
 }
 
#2. Check if a number is palindrome

Solution 1: Using Javascript built in functions

var isPalindrome = function (n) {

    var numString = n.toString(),
        reverseNumString = numString.split("").reverse().join("");
        
    return numString === reverseNumString;
 }
 
 Solution 2: Using for loop
 
 var isPalindrome = function (n) {
 
    var i, numString = n.toString(), stringLen = numString.length;
    
    for (i=0; i<stringLength/2, i++) {
        if (numString[i] !=== numString[stringLength-1-i]) {
            return false;
         }
     }
     
     return true;
 }
    

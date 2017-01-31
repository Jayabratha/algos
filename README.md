# javascript algos



#1. Get length of the longest substring without having duplicate letters
Solution: Using Sliding Window Algorithm

var lengthOfLongestString = function (s) {
    /*ans is the length of the required longest string
     *i is the start index of the sliding window
     *j is the end index of the sliding window*/
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
            

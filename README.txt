Recursive definition for the alternating characters problem:

I used a helper function so I started with char at 1 rather than char at 0, and input the first char (at pos 0) as my LastChar for the first helper call. This is only important
as it helps define the second case of my recursive definition in my explanation to work for the first call.

alternatingCharHelper(string s, char LastChar):

    if len(s) < 1:  //reached end of string, returns 0  (Base case)
        return 0
    if s[0] == lastChar:
        return 1 + alternatingCharHelper(s[1:], s[0])   //  delete the current character 
    else:
        return alternatingCharHelper(s[1:], s[0]) // don't delete the current character

Each recursive call will recursively loop through the input string and check whether the current character is the same as the last character, and if so it will add 1 to the 
total number of deletions if the characters are the same, then continue to the next, otherwise it will just continue to the next character. If it reaches the base case 
where it has reached the end of the string, it will return 0.

Time complexity is n as it has to check each character in the string to choose whether or not to delete or keep. 
Space complexity would be proportional to the current amount of recursive calls in the stack, which would be worst case O(n).




Time complexity of staircase problem is n^2 as it prints n rows with n columns. 
The space complexity would be worst case O(1)/constant time since it directly prints the data instead of storing it. 
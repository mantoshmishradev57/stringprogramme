# stringprogramme

1.Reverse a String in JavaScript
a. function reverseString(str = "") {
    return str.split("").reverse().join("")
   }
Reverse words (the sky  is blue)
const reverseWord = (str)=>{
    let strArray = str.split(" ");
    let reverse_str = "";
    
    for(let i = strArray.length - 1; i >=0; i--) {
        if (strArray[i] == "") continue;
        if (reverse_str.length > 0) reverse_str += " ";
        reverse_str += strArray[i];
        
    }
    return reverse_str;
    
}
//const reverseWord = (str)=> {
    if(str.length <= 0) return "";
    
    let reversedStr = "";
    let splittedArray = str.trim().split(" ");
    let arrayCount = splittedArray.length;
    for(let i = arrayCount - 1; i >=0; i--) {
        reversedStr += splittedArray[i] + " "
    }
    return reversedStr; 
}
//Length of Last Word
lengthOfLastWord = (str) => {
    return str.split(" ").filter(x => x.length !==0).pop().length
}
const reverseOnlyWordfromSentence = (arr)=>{
 const splitted = arr.split(" ");
 const mappedItem = splitted.map(e=> e.split("").reverse().join(""))
 return mappedItem.join(" ")
}

console.log(reverseOnlyWordfromSentence("This is Java code")) //sihT si avaJ edoc

const getMaxOccurringChar = (str) =>{
    let obj ={};
    for(let char of str){
        obj[char] = (obj[char]  || 0 ) + 1
    }
    let maxChar = '';
    let maxCount = 0;
    for(let char in obj){
          if(obj[char] > maxCount){
              maxCount = obj[char]
              maxChar = char
          }
    }
   return {"char":maxChar, totalCount: maxCount};
}
console.log(getMaxOccurringChar("Try programiz pro")) ////{ char: 'r', totalCount: 4 }
//Is Valid Paranthesis
 const isValidParanthesis = (str) => {
    let stack = [];
    for(let i = 0; i<str.length; i++ ) {
        if (str[i] === "(" || str[i] === "{"  || str[i] === "[")
        {
            stack.unshift(str[i])
        }
        else {
            ///(///
            if (str[i] === ")") {
                if (stack[0] == "("){
                    stack.shift();
                    continue
                }
                   else { return false}
            }
         
            
              ///{///
            if (str[i] === "}") {
                if (stack[0] == "{"){
                    stack.shift();
                    continue
                }
                  else { return false}
            }
          
            
                    ///[///
            if (str[i] === "]") {
                if (stack[0] == "["){
                    stack.shift();
                    continue
                }
                     else { return false}
            }
        }
            
    }
    if(stack.length >0){ return false}
    else {return true}
        
}

b.
function reverseString(str = "")  {
   let revString = ""
   for (var i = str.length - 1; i >= 0; i--) {
    revString += str[i];
   }
  return revString;
 }

2.Fizz Buzz
let s = "";
let c3 = 0; c5 =0;
for(let i = 1; i<=100; i++) {
  c3++;
  c5++;
  if(c3 === 3) {
     s += "fizz";
     c3 = 0;
  }
  if (c5 === 5) {
     s += "buzz";
     c5 = 0;
  }
 if (s.length === 0)
   console.log("length:",i);
else
 console.log(s);
s = ""
}

const pintFizzBuzz = (num) => {
    
    let arrayList = [];
    
    for (let i = 1; i <= num; i++) {
        if((i%3 == 0) && (i%5 == 0))
        {
            arrayList.push("FizzBuzz")
            continue;
        }
       if ((i%3 == 0))
       {
              arrayList.push("Fizz")
                   continue;
        }
        if ((i%5 == 0))
        {
              arrayList.push("Buzz")
                   continue;
        }
           arrayList.push(i+"")
    }
    
    return arrayList
}
3.Reverse a string without affecting special characters

1. Let input string be 'str[]' and length of string be 'n'
2. l = 0, r = n-1
3. While l is smaller than r, do following
   a) If str[l] is not an alphabetic character, do l++
   b) Else If str[r] is not an alphabetic character, do r--
   c) Else swap str[l] and str[r]

   3a. is Alphabet
   function isAlphabet(char){
      return /^[a-zA-Z]+$/.test(char)
    }
    
    3b. isInteger
    function isInteger(i){
        return /^\d+$/.test(i)
   }
   
  isAlphabet = (a) => {
    return /^[a-zA-Z]+$/.test(a)
}

swap = (str,l,r) => {
    let s = "";
    for (var i = 0 ; i< str.length; i ++){
        if (i === l) {
            s = s + str[r];
        }
        else {
            if (i === r){
                s = s + str[l]
            }
            else {
                s = s + str[i];
            }
        }
    }
    return s;
}

reverse = (str) => {
    let l = 0;
    let r = str.length - 1;
    while (l < r) {
    if (!isAlphabet(str[l])) {
        l++;
    }
    else if (!isAlphabet(str[r])){
        r--;
    }
    else {
        str = swap(str,l,r);
        l++;
        r--;
    }
    }
    return str;
}

var str= "a!!!b.c.d,e'f,ghi";
console.log(reverse(str));

4. Is An Anagram
function checkStringsAnagram(a, b) {
   let len1 = a.length;
   let len2 = b.length;
   if(len1 !== len2){
      console.log('Invalid Input');
      return
   }
   let str1 = a.split('').sort().join('');
   let str2 = b.split('').sort().join('');
   if(str1 === str2){
      console.log("True");
   } else { 
      console.log("False");
   }
   console.log("str1:",str1);
   console.log("str2:",str2);
}
checkStringsAnagram("indian","ndiani")

5. Validate Palindrom
   lastDigit = num % 10;
   rev = rev * 10 + lastDigit;
   num = Math.floor(num/10);

function reverseNumber(num) {
   let rev = 0;
   let lastDigit;

   while (num != 0) {
     lastDigit = num % 10;
     rev = rev*10 + lastDigit;
     num = Math.floor(num/10);
   }

   return rev;
}

console.log("Reverse number : "+reverseNumber(123456));

function reverseNum(num){
   let rev = 0;
   rev = Number(String(num).split('').reverse().join('')); 
   return rev;

}
console.log("Reverse number : "+reverseNum(123456));

6. Finding sum of digits of a number until sum becomes single digit

digiSum =(n) =>{
    if (n === 0){
        return 0;
    }
    
    return (n%9 == 0) ? 9 : (n%9)
}

console.log("digiSum:",digiSum(5674));

7. Dollar Sign Deletion
const str = "Hey, I'am 25 and she is 31$.";
function removeSpecialCharacter(str) {
  let s = "";
  for (let i = 0; i < str.length; i++) {
       if (str[i] !== "$"){
           s = s + str[i];
       }
    }
    return s;
}

console.log(removeSpecialCharacter(str));

8. Find first non repeating value

function firstNonRepElement(str) {
    let list = [];
    for (let i = 0; i < str.length; i++) {
        if (list.includes(str[i])) {
           list.splice(list.indexOf(str[i]),1);
        }
        else {
                 list.push(str[i]);
            }
        }
    console.log(list[0]);
}
 
// Driver Code
let str = "asdfsdafdasfjdfsafnnunl";
 
// Function Call
firstNonRepElement(str);

9. Print Pattern
* 
* * 
* * * 
* * * * 
* * * * *
    const printPattern = (n)=>{
    for(let i = 0; i<n; i++) {
        let str = "*";
        console.log(str.repeat(i))
    }
}

console.log(printPattern(5));


        * 
      * * 
    * * * 
  * * * * 
* * * * * 
const printPattern = (n)=>{
    for(let i = 1; i <= n; i++) {
         let str = "* ";
         let space  = '  ';
        console.log(space.repeat((n-i))+str.repeat(i))
    }
}


* * * * * 
* * * * 
* * * 
* * 
*

        const printPattern = (n)=>{
    for(let i = 0; i <= n; i++) {
         let str = "* ";
         let space  = '  ';
        console.log(str.repeat(n-i))
    }
}

* * * * * 
  * * * * 
    * * * 
      * * 
        * 

        const printPattern = (n)=>{
    for(let i = 0; i <= n; i++) {
         let str = "* ";
         let space  = '  ';
        console.log(space.repeat(i)+str.repeat(n-i))
    }
}

Upper pyramid
       * 
      * * 
     * * * 
    * * * * 
   * * * * * 
  * * * * * * 
 * * * * * * * 
* * * * * * * * 
const printPyramid = (n)=>{
 
for (let i = 1; i <= n; i++) { 
    let str = "* "; 
    let space = '  '; 
    console.log(space.repeat((n - i)) + str.repeat(i * 2 - 1)); 
}
}

Inverted pyramid
* * * * * * * * * 
  * * * * * * * 
    * * * * * 
      * * * 
        *
const printPyramid = (n)=>{
 
for (let i = n; i >= 1; i--) { 
    let str = "* "; 
    let space = '  '; 
    console.log(space.repeat((n - i)) + str.repeat(i * 2 - 1)); 
}
}
    10. Reverse Words in Sentence.    
let str = "Online Javascript Editor for free";

const reverseWords = (strV)=>{
    const arrStr = strV.split(" ");
    return arrStr.map(e=> e.split("").reverse().join("")).join(" ")
}
// Output: enilnO tpircsavaJ rotidE rof eerf

const areAngram = (str1, str2)=> {
    
    const firstStr = str1.replace(/\s+/g,'').toLowerCase();
    const secondStr = str2.replace(/\s+/g,'').toLowerCase()
    
    if(firstStr.length !== secondStr.length) return false;
    
    return firstStr.split('').sort().join('') == secondStr.split('').sort().join('')
}

console.log(areAngram("listen", "silent"));
console.log(areAngram("hello", "world"));

const removeDuplicateFromString = (str)=> {
    return [... new Set(str)].join('')
}

console.log(removeDuplicateFromString('aabbccddeeff'));

function removeDuplicates(str) {
    let seen = {};  // Object to track the characters we've encountered
    let result = '';

    for (let char of str) {
        if (!seen[char]) {  // Check if the character has been seen
            seen[char] = true;  // Mark this character as seen
            result += char;  // Append it to the result string
        }
    }

    return result;
}

const result = removeDuplicates('aabbccddeeff');
console.log(result); // Output: 'abcdef'

how you can count the number of palindromes in a string using JavaScript:

const isPalindrom = (str) => {
  return  str == str.split("").reverse().join("")
}

const countPalindrom = (str) => {
    let palindromCount = 0;
     const n = str.length;
    for(let i = 0; i<n; i++){
        for(let j = i+1 ; j<=n; j++){
            const subStr = str.slice(i,j);
            if(isPalindrom(subStr)){
               palindromCount ++ 
            }
        }
    }
    
    return palindromCount;
}

console.log(countPalindrom('abcba'));


Longest Palindromic Subsequence


const isPalindrom = (str) => {
  return  str == str.split("").reverse().join("")
}

const countPalindrom = (str) => {
    let palindromCount = 0;
    let obj = {};
     const n = str.length;
    for(let i = 0; i<n; i++) {
        for(let j = i+1 ; j<=n; j++){
            const subStr = str.slice(i,j);
            if(isPalindrom(subStr)){
                obj[subStr] =   subStr.length
               palindromCount ++ 
            }
        }
    }
    console.log(obj)
    let maxKey = '';
    let maxValue = -Infinity;
    for (let k in obj) {
        if(obj[k] > maxValue)
        {
            maxValue = obj[k]
            maxKey = k
        }
    }
    console.log(`Longest palindrom Value maxKey:${maxKey} maxValue:${maxValue}`)
    return palindromCount;
}

console.log(countPalindrom('abcba'));


const returnOccuranceOfString = (str) => {
    let obj = {};
    for(let char of str){
       obj[char] =  obj[char] ? obj[char] + 1 : 1
    }
    return Object.entries(obj).map(([k,v])=> v == 1 ? `${k}`: `${k}${v}`).join('');
}

console.log(returnOccuranceOfString("abaaccdeefgfhfkf"));



const findLongestWord = (str)=> {
    return str.split(' ').reduce((longest, word) => word.length > longest.length ? word : longest, '')
}

console.log(findLongestWord("Try programiz pro"));


const capatilizeFirstCharacterOfWord = (str) => {
    return str.
    split(' ').
    map(e => e.charAt(0).toUpperCase() + e.slice(1).toLowerCase()).
    join(' ')
}

console.log(capatilizeFirstCharacterOfWord("Try programiz pro"));

const isInteger = (c) => {
    return /^-?\d+$/.test(c)
}


const isAlphabet = (c) => {
    return /^[a-zA-Z\s]+$/.test(c)
}

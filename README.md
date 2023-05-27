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
//Length of Last Word
lengthOfLastWord = (str) => {
    return str.split(" ").filter(x => x.length !==0).pop().length
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

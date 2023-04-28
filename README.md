# JSpractice
Q1  Q1 How to check if an object is an array or not?
```js
let objorarray =[];

console.log(Array.isArray(objorarray));
```

Q2 How to check whether a key exist in a JavaScript object or not.
```js
let objKey = {
    name:"Rushi",
    LastName:"Kote",
}

console.log("check property",objKey.hasOwnProperty("name"));
```

Q3 Write code for merge two JavaScript Object dynamically using inbuilt and without inbuilt method.
```js
var person = {
        name : 'John',
        age  : 24
}

var location = {
        addressLine1 : 'Some Location x',
        addressLine2 : 'Some Location y',
        city : 'NewYork'
}

const con = {...person,...location};
console.log(con);

const merge = Object.assign(person,location);
console.log(merge);
```

Q4 "What is would be the output of the following :
```js
(function() {
	var objA = {
		foo: 'foo',
		bar: 'bar'
	};
	var objB = {
		foo: 'foo',
		bar: 'bar'
	};
	console.log(objA == objB); // flase
	console.log(objA === objB); // flase
}());
```

Q5 How do you print numbers with commas as thousand separators
```js
let number = 10008655476575668000;

function seperator(number){
    let num = number;
    let str = "";
    
    while(num>0){
        let rem =num%1000;
        console.log("num",num);
        console.log("rem",rem);

        if(rem>0 && num >1000){
            // str+=rem;
            if(rem<10){
                str = ",00" + rem +str; 
            }else if(rem<100){
                str = ",0" + rem +str; 
            }else{
                str = "," + rem +str;
            }
            console.log("rem>0",str);
        }else if(num>=999){
            str = "," + "000"+str;
            console.log("nem>999",str);
        }else if(num<1000){
            str = num + str;
            break;
        }
        num = Math.floor(num/1000);
    }
    console.log(str);
}

seperator(number);
```

Q6 How can we delete an element at a specific index in an array.
```js
let arrDel = [1,2,3,4,5,666,7,8,9,99];
arrDel.splice(3,1) // here 3 is index
console.log(arrDel);
```

Q7 Write a code to find the second largest value in an array.
```js
let secondLargest = [1,2,3,4,5,66,234,7,8,9,99];

let largest = secondLargest[0];
let secLargest = -999;
secondLargest.forEach((ele)=>{
    if(ele>largest){
        largest = ele;
    }else if(ele>secLargest){
        secLargest = ele;
    }
});
```
Q8 "How to check the no. of occurrence of a character in a string.
Example: PlacementsPractice"
```js
let stringOccu = "PlacementsPractice";

let chars = stringOccu.toLowerCase().split("");
console.log(chars);

for(let i=0; i<chars.length; i++){
    let count = 0;
    for (let j = 0; j < chars.length; j++) {
        if(chars[i]===chars[j]){
            count ++;
        }
    }
    console.log(chars[i]," ",count);
}
```
Q9 "Output bAsed question : 
```js
function User(name) {
  this.name = name || "JsGeeks";
}

var person = new User("xyz")["location"] = "USA";
console.log(person); // USA will be printed on screen
```
Q10 What are the ways by which we can create object in JavaScript ?
```js
let objCreat = {
    name: 'John',
    age: 20
};
let objCreat2 =new Object({
    name: 'John',
    age: 20
});
```
Q11 "Output of this code :
```js
var employeeId = '1234abe';
(function() {
	// console.log(employeeId);
	var employeeId = '122345';
	(function() {
		var employeeId = 'abc1234';
	}());
}());

//output --> Undefined
```




Q13 How to find duplicate elements in a given array?
```js
const duplicate = [1,2,3,4,5,6,4,7,3];

for(let i =0; i<duplicate.length;i++){
    for(let j=i+1; j<duplicate.length;j++){
        if(duplicate[i]== duplicate[j]){
            console.log(duplicate[j]);
        }
    }
}
```


Q14 "How to find the unique value from an array in sorted order?
let array = [23, 45, 34, 33, 87, 45, 21, 76, 25]
Output: [21, 23, 25, 33, 34, 45, 76, 87]"
```js
let array = [23, 45, 34, 33, 87, 45, 21, 76, 25]
let unique =[...new Set(array.sort())];
console.log(unique);
```

Q15 "Write a code to create a sentence from the given array?
```js
let arr = ["Hi", "I am", "Full Stack" , "Developer"]

let joined = arr.join(" ");
console.log(joined);
```

 Q16 Given a two strings find out if they are anagram of each other
 ```js
 let string1 = "listen";
let string2 = "s5ilent";

string1 = string1.replace(/[^\w]/g,"").toLowerCase().split("").sort().join("");
string2 = string2.replace(/[^\w]/g,"").toLowerCase().split("").sort().join("");

console.log(string1 === string2);
 ```
 
Q17 "How can you extract  a few fields  from the given JSON object  and form a new array? 
```js
const input = {
   students : [
                 {
                  name : "Ravi",
                  id: 10
                  }
                  , {
                  name : "Mahesh",
                  id: 6
                  } ,
                   {
                  name : "Surya",
                  id: 7
                  }
                ]
}

const output = input.students.map((ele)=>{
    return ele.name;
});
console.log(output);
```
Q18 "Tell me the output of this code :"
```js
const a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
for (let i = 0; i < 10; i++) {
  setTimeout(() => console.log(a[i]), 1000);
}
//ans-> after 1 sec of delay all 1 to 10 elements of array will be get printed on screen
for (var i = 0; i <= 9; i++) {
  setTimeout(() => console.log(a[i]), 1000);
}

//ans-> after 1 sec of delay "undefined" will be get printed on screen
```

Q19 How to convert an Object {} into an Array [] in JavaScript?
```js
const obj =  {
    name : "Ravi",
    id: 10
}

const toArray = Object.entries(obj);

console.log(toArray);
```

Q20 Write a function that takes an array of numbers and returns the median value.
```js
const arrayOfNumber = [10,20,30,40,50];

function median(arrayOfNumber){
    if(arrayOfNumber.length %2 ===0){
        let index = Math.floor((arrayOfNumber.length-1) /2);
        let medianOfArray = (arrayOfNumber[index] + arrayOfNumber[index+1])/2;
        return medianOfArray;
    }else{
        let index = Math.floor((arrayOfNumber.length-1) /2);
        return arrayOfNumber[index];
    }
}

console.log(median(arrayOfNumber));
```

Q21 "Output Based Question:
```js
var Employee = { company: "abc" };
var emp1 = Object.create(Employee);
delete emp1.company;
console.log(emp1.company);
//Output abc
```

Q24 Create a function that will convert from Celsius to Fahrenheit
```js

let Celsius =26.67 ;

let Fahrenheit = (Celsius*9)/5 +32;
console.log(Fahrenheit);

```

Q25 Create a function that will find the nth Fibonacci number using recursion
```js
let nth = 9;

console.log(Fibonacci(nth));

function Fibonacci(nth){
    if(nth>2){
        return Fibonacci(nth-1) + Fibonacci(nth-2);
    }else if(nth>1){
        return 1;
    }else{
        return 0;
    }
}
```

Q26 "Create a function that will receive two arrays of numbers as arguments and return an array composed
of all the numbers that are either in the first array or second array but not in both" ;
```js

let arr1 = [1,2,3,4,5,6,7,8];
let arr2 = [1,9,6,98,3,676,54,23,45];

function Unique(arr1,arr2){
    let CombinedArr =[];
    if(arr1.length > arr2.length){
        CombinedArr = [...arr1];
        for(let i=0;i<arr2.length;i++){
            let falg = true;
            for(let j=0;j<arr1.length;j++){
                if(arr1[j]===arr2[i]){
                    falg = false;
                    break;
                }
            }
            if(falg){
                CombinedArr.push(arr2[i]);
            }
        }
    }else{
        CombinedArr = [...arr2];
        for(let i=0;i<arr1.length;i++){
            let falg = true;
            for(let j=0;j<arr2.length;j++){
                if(arr2[j]===arr1[i]){
                    falg = false;
                    break;
                }
            }
            if(falg){
                CombinedArr.push(arr1[i]);
            }
        }
    }
    console.log(CombinedArr);
}
Unique(arr1,arr2)
```
Q27 "Create a function to return the longest word from the string
```js
let text = "Create a function to return the longest word(s) in a sentance.";

text = text.replace("/[^\w]/g","").split(" "); 

function FindMaxLengthString(text) {
    let maxLengthStr = "";
    text.forEach((ele)=>{
        if(ele.length>maxLengthStr.length){
            maxLengthStr = ele;
        }
    });
    return maxLengthStr;
}

console.log(FindMaxLengthString(text));
```
Q28 "Output of this?
```js

var Y = 1;
if (function F(){})
{
    Y += typeof (F);
}
console.log(Y);
// Output 1undefined
```
Q29
```js
(function(){
    var a = b = 3;
    })();
    console.log("a defined? " + (typeof a !== undefined));
    console.log("b defined? " + (typeof b !== undefined));

// output true for both
```

Q30 "Write a code to find the unique word from the string?

Input : "" HELLO HELLO BYE BYE HI ""
Output : HI"
```js
let inputStr = "HELLO HELLO BYE BYE HI";

inputStr = inputStr.split(" ");

for(let i=0;i<inputStr.length;i++){
    let falg = true;
    for(let j=0;j<inputStr.length;j++){
        if(inputStr[i]===inputStr[j] && i!==j){
            falg = false;
        }
    }
    if(falg){
        console.log(inputStr[i]);
    }
}
```

# JSpractice
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

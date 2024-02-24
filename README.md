# learning_javascript
### variables (var ,let ,const)
```javascript
var balance = 5000; // not used in today's
let balance = 5000; // can be overwrite later
const balance = 5000; //can't overwrite
const description = 'salary';
const newTransaction = true;
```

### data types & structures (string ,numbers ,boolean,array,object)
```javascript
const text = 'hello';
const expenses = [10, [1, 2, 3, 4, 5, 6], 30];
console.log(expenses[1][2]);

//  object
const transaction = {
    description: 'salary',
    amount: 5000
}
console.log(transaction.description);
```
### functions 
#### function declaration
```javascript
function calculateBalance(income, expenses) {
    return income - expenses;
}
const result = calculateBalance(5000, 3000);
console.log(result);
```
#### function expression
```javascript
var calculateBalance = function(income, expenses) {
    return income - expenses;
}
const result = calculateBalance(5000, 1000);
console.log(result);
```
#### arrow function
```javascript
const calculateBalance = (income, expenses) => {
    return income - expenses;
}
const result = calculateBalance(5000, 1500);
console.log(result);
```
### to GET something using api
```javascript
const btnE1 = document.querySelector('.my-button');

const clickhandler = async () => {
    try {
        const res = await fetch('https://reqres.in/api/users');
        const data = await res.json();

        if (!res.ok) {
            console.log('problem');
            return;
        }

        console.log(data.data[2].email)
    } catch (error) {
        console.log(error);
    }
}
btnE1.addEventListener('click', clickhandler);
```

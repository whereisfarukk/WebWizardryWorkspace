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
### interacting with HTML & CSS (DOM manipulation)
#### change html content
```javascript
const btnE1 = document.querySelector('.my-button');

const headingE1 = document.querySelector('.first-heading');
headingE1.textContent = 'faruk';
```
#### adding span under a class 
```js
const balanceEl = document.querySelector('.balance-number');

balanceEl.innerHTML = '<span class = "special">Unavailable</span>';
```
#### without replacing previous element ,adding new span
```js
const balanceEl = document.querySelector('.balance-number');

balanceEl.insertAdjacentHTML('afterend', '<span class = "special">Unavailable</span>');
```
#### change html content on click event
```javascript
const balanceEl = document.querySelector('.balance-number');

balanceEl.addEventListener('click', () => {
    const balance = 5000 - 1000;
    balanceEl.textContent = balance;
})
```
#### change css on click event
```javascript
const balanceEl = document.querySelector('.balance-number');

balanceEl.addEventListener('click', () => {
    balanceEl.style.color = 'red';
})
```
### adding css class 

```css
.balance-number--special {
    color: red;
    font-size: 50px;
    font-weight: 800;

}
```
```js
const balanceEl = document.querySelector('.balance-number');

balanceEl.addEventListener('click', () => {
    balanceEl.classList.add('balance-number--special');
})
```
```html
<span class="balance-number">4700</span>
// after the click
<span class="balance-number balance-number--special">4700</span>
```

### clicking an item for deleting it  
<img src="https://github.com/whereisfarukk/learning_javascript/blob/main/gifs/delet_item.gif"
alt="javascript">
```js
const transactionEl=document.querySelector('.transactions-section'); // select the parent element class
transactionEl.addEventListener('click',function(event){
    const clickedEl=event.target.parentNode;
    clickedEl.remove();
})
```
### adding something from form input
```js
formEl.addEventListener('submit',function(){
    const description = inputDescriptionEl.value;
    const amount = +inputAmountEl.value;
    const transactionItemHTML = `
        <li class="transaction transaction--${amount>0 ? "income" : "expense"}">
            <span class="transaction__text">${description}</span>
            <span class="transaction__amount">${amount>0? "+" :""}${amount}</span>
            <button class="transaction__btn">X</button>
        </li>
    `; 
    transactionEl.insertAdjacentHTML("beforeend",transactionItemHTML);
})


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

# learning_javascript
### variables (var ,let ,const)
```javascript
var balance = 5000; // not used in today's
let balance = 5000; // can be overwrite later
const balance = 5000; //can't overwrite
const description = 'salary';
const newTransaction = true;
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

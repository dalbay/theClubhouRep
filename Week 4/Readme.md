
## Exercise
1. change styles of 3 separate elements using Javascript
2. change the class name and text of a a child or sibling of each of the above elements
## Exercise
1. add an event listener to an element so that when you click it, another element's style changes.
2. create a list with at least 3 elements
3. apply event delegation to that list of elements
## Exercise
- create an auto complete feature
    - input text box
    - list of terms
    - compare
    - validate input (no special characters)
## Exercise
- create a countdown timer
    - countdown from a number to 0
    - it needs to be visible counts  
## Exercise
- hit the Fakerjs API
    - build a series of profile cards for random people
	
	
## Week 4 - Exercise/Solutions - JavaScript

* Test each function from last week's app
* update variables and functions to better names
* see if you can turn any functions into methods of objects

  - Replace *inventory[]* with Object *Products*. 
  - Replace function *addProduct* with Object method *Products.addProduct*. 


```JavaScript
// Declare Global Properties

// OMIT THIS - change inventory array to Product object
//var inventory = [];
var value;
var tr;
var td;
var li;
var input;
var td2;
var td3;
var val;

// Get the modal
var modal = document.getElementById("myModal");

// Get the button that opens the modal
var btn = document.getElementById("myBtn");

// Get the <span> element that closes the modal
var span = document.getElementsByClassName("close")[0];

// Stores the Selected item
let selectedItem = "";

// OMIT THIS - initialize the array
// // Initialize the elements
// function fillArray() {
//     inventory["water"] = 100,
//         inventory["soda"] = 100,
//         inventory["detergent"] = 50,
//         inventory["apple"] = 100,
//         inventory["banana"] = 100,
//         inventory["tomato"] = 100,
//         inventory["bread"] = 50,
//         inventory["butter"] = 50,
//         inventory["milk"] = 50,
//         inventory["chicken"] = 50;
// }

// CREATE THIS - Object Literal
var Products = { water : 100, soda : 100, detergent : 50, apple : 100, banana : 100, tomato : 100, bread : 50, butter : 50, milk : 50, chicken : 50
};

// CRAETE THIS - Object method
Products.addProduct = function(){
        // get the values
        var product = document.getElementById('inventoryName').value;
        var quantity = document.getElementById('quantity').value;
        // add to inventory if not empty
        if (product !== "" && quantity !== "") {
    
            // OMIT THIS - add new element to array
            //inventory[product] = parseInt(quantity);
            // CREATE THIS - add new property-value to object
            Products[product] = parseInt(quantity);
    
            alert("Saved " + product + " of " + quantity + " units.");
            // add to the UI
            productList();
        } else {
            alert('*Cannot add the product*');
        }
        console.log(Products);
    
        document.getElementById('inventoryName').value = "";
        document.getElementById('quantity').value = "";
}

// // OMIT THIS (function changed to object method)
// // Add a new product to the iventory array:
// function addProduct() {
//     // get the values
//     var product = document.getElementById('inventoryName').value;
//     var quantity = document.getElementById('quantity').value;
//     // add to inventory if not empty
//     if (product !== "" && quantity !== "") {

//         // OMIT THIS
//         //inventory[product] = parseInt(quantity);
//         // CREATE THIS
//         Products[product] = parseInt(quantity);

//         alert("Saved " + product + " of " + quantity + " units.");
//         // add to the UI
//         productList();
//     } else {
//         alert('*Cannot add the product*');
//     }
//     console.log(Products);

//     document.getElementById('inventoryName').value = "";
//     document.getElementById('quantity').value = "";
// }


// Event Listeners
// CHANGE THIS - No need for fillArray() anymore
window.addEventListener('load', productList());

// Add event listener to the Add Product Button
// CHANGE THIS - change addProduct to object method call
document.getElementById('addProduct').addEventListener('click', Products.addProduct);


// Clear the index page table content
function clearTable(table) {
    // Get the Product Table
    var tr = table.getElementsByTagName("tr");
    // Remove the elements
    if(tr.length !== 0){
        while (table.childNodes[1]) {
            table.removeChild(table.childNodes[1]);
        }
    }
}

// Dynamically create the first tr element for heading
function createFirstTrTag(table){
    var tr = document.createElement('tr');
    var tbody = document.createElement('tbody');  
    var th1 = document.createElement('th');
    th1.innerText = "Product";
    var th2 = document.createElement('th');
    var th3 = document.createElement('th');
    th3.innerHTML = 'Quantity in Stock';
    tr.appendChild(th1);
    tr.appendChild(th2);
    tr.appendChild(th3);
    tbody.append(tr);
    table.append(tbody);
}

// Dynamically Display the Products in index
function productList() {
    var table = document.querySelector('#productList');
    createFirstTrTag(table)
    // clear the table content before adding new rows
    clearTable(table);
    
    // OMIT THIS
    // iterate through the inventory and display each product
    // for (var key in inventory) {
    //     var tr = document.createElement('tr');
    //     var td1 = document.createElement('td');
    //     td1.innerText = key;
    //     var td2 = document.createElement('td');
    //     td2.innerText = " - ";
    //     var td3 = document.createElement('td');
    //     td3.innerText = inventory[key];
    //     tr.appendChild(td1);
    //     tr.appendChild(td2);
    //     tr.appendChild(td3);
    //     table.appendChild(tr);
    // }
    // CREATE THIS
    for(var product in Products){
        // CREATE THIS ( - call object properties only)
        if(product !== 'addProduct'){
            var tr = document.createElement('tr');
            var td1 = document.createElement('td');
            td1.innerText = product;
            var td2 = document.createElement('td');
            td2.innerText = " - ";
            var td3 = document.createElement('td');
            td3.innerText = Products[product];
            tr.appendChild(td1);
            tr.appendChild(td2);
            tr.appendChild(td3);
            table.appendChild(tr);
        }
    }
}

// Clear the table in Modal before displaying it.
function clearModelTable(table) {
    var tr = table.getElementsByTagName('tr');
    if(tr.length !== 0){
        while(table.childNodes[1]){
            table.removeChild(table.childNodes[1]);
        }
    }
}

// Dynamically create the inventory list inside the Modal Box.
function createInventoryList() {
    var table = document.querySelector('#inventoryTable');
    createFirstTrTag(table);
    // clear the modal table content before adding new rows   
    clearModelTable(table);

    // OMIT THIS
    // iterate through the inventory and display each product
    // for (var key in inventory) {
    //     var tr = document.createElement('tr');
    //     var td = document.createElement('td');
    //     var li = document.createElement('li');
    //     var input = document.createElement('input');
    //     input.type = 'radio';
    //     input.name = 'items';
    //     input.value = key;
    //     input.addEventListener('input', setItem);
    //     var td2 = document.createElement('td');
    //     td2.innerText = key;
    //     td2.classList = "items";
    //     var td3 = document.createElement('td');
    //     td3.innerText = inventory[key] + " qty";
    //     li.appendChild(input);
    //     td.appendChild(li);
    //     tr.appendChild(td)
    //     tr.appendChild(td2);
    //     tr.appendChild(td3);
    //     table.appendChild(tr);
    // }
    // CREATE THIS
    for (var product in Products) {
        // CREATE THIS ( - call object properties only)        
        if(product !== 'addProduct'){
            var tr = document.createElement('tr');
            var td = document.createElement('td');
            var li = document.createElement('li');
            var input = document.createElement('input');
            input.type = 'radio';
            input.name = 'items';
            input.value = product;
            // add event listener to each input element
            input.addEventListener('input', setItem);
            var td2 = document.createElement('td');
            td2.innerText = product;
            td2.classList = "items";
            var td3 = document.createElement('td');
            td3.innerText = Products[product] + " qty";
            li.appendChild(input);
            td.appendChild(li);
            tr.appendChild(td)
            tr.appendChild(td2);
            tr.appendChild(td3);
            table.appendChild(tr);
        }
    }
}

// Set the selected item property
function setItem(e) {
    selectedItem = e.target.value;
}

// Open the modal when clicked.
btn.onclick = function () {
    // clear the radio button selection
    selectedItem = "";
    // display the modal
    modal.style.display = "block";
    // call the function to display the inventory
    createInventoryList();
}

// Calculate the quantity left in stock; update global property and return statement
function modifyItemQuantity(item) {
    // OMIT THIS
    // if (inventory[item] !== 0) {
    // CREATE THIS
    if (Products[item] !== 0) {
        if (selectedItem === "") {
            return "Nothing was selected";
        } else {
            val = Products[item] - 1;
            return item + "- Quantity left in stock: " + val;
        }
    } else {
        return item + " is out off stock.";
    }
}

// Calculate the quantity left in stock; update global property and return statement
function modifyItemQuantity(item) {
    // CREATE THIS
    if (Products[item] !== 0) {
        if (selectedItem === "") {
            return "Nothing was selected";
        } else {
            val = Products[item] - 1;
            //change the value of the selected item in the inventory
            // OMIT THIS
            // inventory[selectedItem] = val;
            // CREATE THIS
            Products[selectedItem] = val;
            return item + "- Quantity left in stock: " + val;
        }
    } else {
        return item + " is out off stock.";
    }
}
// When the user clicks on <span> (x), close the modal 
span.onclick = function () {
    modal.style.display = "none";
    // display alert box when closing
    alert(modifyItemQuantity(selectedItem));    
    productList();
}
// When the user clicks anywhere outside of the modal, close it
window.onclick = function (event) {
    if (event.target == modal) {
        modal.style.display = "none";
        // display alert box when closing
        alert(modifyItemQuantity(selectedItem));
        productList();
    }
}
```
---

====================================================================
**_ Building an Ecommerce Website with Vanilla JavaScript _**
====================================================================

**_ Folder structure _**

my-vanilla-js-project/
├── public/
│ ├── images/
│ │ ├── logo.png
│ │ └── background.jpg
│ └── index.html
├── src/
│ ├── index.html
│ ├── main.js
│ ├── utils.js
│ └── styles.css
├── vite.config.js
└── package.json

**_ or we can also use _**

my-vanilla-js-project/
├── public/
│ ├── images/
│ │ ├── logo.png
│ │ └── background.jpg
│ └── index.html
├── index.html
├── main.js
├── styles.css
├── vite.config.js
└── package.json

## Step 1: Don't Forget To LIKE SHARE & SUBSCRIBE TO THAPA TECHNCIAL YOUTUBE CHANNEL 👉 https://www.youtube.com/thapatechnical

====================================================================
**_ Steps to Create a Function for Displaying Product Containers _**
====================================================================

## Step 1: Selecting DOM Elements

- Use `document.querySelector()` to select the product container and template container elements from the HTML document.

## Step 2: Defining the Function

- Define a function named `showProductContainer` that takes an array of products as input.

## Step 3: Checking for Valid Input

- Check if the `products` array is truthy. If not, return `false`.

## Step 4: Iterating Over Products

- Iterate over each product in the `products` array using `forEach()`.

## Step 5: Destructuring Product Properties

- Destructure the properties of each product object (brand, category, description, etc.) for easier access.

## Step 6: Cloning the Template

- Use `document.importNode()` to clone the template container for each product.

## Step 7: Updating Product Information

- Update the cloned template with the product details:
  - Set the text content of elements to display product information.
  - Set the source attribute of the product image element.
  - Calculate and display the actual price based on the product price.

## Step 8: Adding Event Listener

- Add an event listener to a specific element (`.stockElement`) within each product template.
- Use event delegation to handle click events and pass relevant data (event, product id, stock) to the `homeQuantityToggle()` function.

## Step 9: Appending to Product Container

- Append the cloned template with updated product information to the product container element.

## Step 10: Ensuring Container Availability

- Check if the product container element exists before appending the cloned template.

## Conclusion

- You've created a function that dynamically populates the product container with product information based on the provided array of products.

=============================================================
**_ # Steps to Define the homeQuantityToggle Function _**
=============================================================

# Steps to Define the homeQuantityToggle Function

## Step 1: Create a New JavaScript File

- Create `quantityToggle.js` to contain `homeQuantityToggle`.

## Step 2: Define the Function

- Define `homeQuantityToggle(event, id, stock)`.

## Step 3: Select Current Card Element

- Use `document.querySelector()` to select the card element based on `id`.

## Step 4: Retrieve Product Quantity

- Retrieve product quantity using `querySelector()`.

## Step 5: Parse Quantity Attribute

- Parse `data-quantity` attribute to an integer.

## Step 6: Handle Increment Event

- Increment quantity if event target is `"cartIncrement"` and quantity < stock.

## Step 7: Handle Decrement Event

- Decrement quantity if event target is `"cartDecrement"` and quantity > 1.

## Step 8: Update Product Quantity Display

- Update text content of product quantity element.

## Step 9: Update Quantity Attribute

- Set `data-quantity` attribute to new quantity.

## Step 10: Return Quantity

- Return updated quantity.

## Conclusion

You've created `homeQuantityToggle` in `quantityToggle.js`, enabling users to update product quantities interactively.

=====================================================
**_ Add To Cart Functionality _**
=====================================================

# Steps to Define the addToCart Function

## Step 1: Find Current Card Price and Quantity

- Select the current card element based on the provided `id`.
- Retrieve the product quantity from the current card element.
- Retrieve the product price from the current card element.

## Conclusion

You've defined the `addToCart` function, enabling users to add products to their cart with the provided quantity and price.

===================================================================
**_ Steps for Retrieving Cart Products from Local Storage _**
===================================================================

## Step 1: Incorporate `getCartProductFromLocalStorage` into `addToCart`

## Step 2: Define `getCartProductFromLocalStorage`

## Step 3: Retrieve Cart Products by using `localStorage.getItem()`

## Step 4: Check for Null or Undefined Cart Products

## Step 5: Parse Cart Products

## Step 6: Return Cart Products

======================================================================
**_ Steps to Update Product Price Before Adding to Local Storage _**
======================================================================

## Step 1: Extract Price Without Currency Symbol

- Use `replace()` to remove the currency symbol (`₹`) from the product price.

## Step 2: Calculate Total Price

- Multiply the extracted price by the product quantity to calculate the total price.

## Step 3: Prepare Product Data

- Create an object containing the product `id`, `quantity`, and updated `price`.

## Step 4: Add Product Data to Cart Array

- Push the product object to the existing cart array.

## Step 5: Convert Cart Array to JSON and Store in Local Storage

- Convert the updated cart array to JSON format using `JSON.stringify()`.
- Store the JSON string in local storage under a designated key.

======================================================================
**_ Handle Duplicate Values _**
======================================================================

## Use the find() method to search for existing products in the cart array based on their IDs.

## If an existing product is found and the local quantity is greater than 1, update the quantity and price of the existing item in the cart.

## Ensure that the quantity and price are updated only for the existing item in the cart, not for duplicate entries.

## Map through the existing cart items and update the quantity and price of the matching product.

## Update the cart array in local storage with the updated cart items.

## If an existing product is found, return false to prevent adding duplicate entries to the cart.

====================================================
**_ Update Cart Value on Page Load _**
====================================================

## Call the updateCartValue function whenever the page loads to ensure the cart value is updated.

## Call the updateCartValue function inside the function responsible for retrieving data from local storage.

====================================================
**_ Display Cart Products on Page _**
====================================================

## Retrieve cart product IDs from local storage using the getCartProductFromLocalStorage function.

## Filter the full product data from the productsArr based on the IDs of products stored in the cart.

## Iterate through the filtered cart product data and create DOM elements to display each product in the cart.

## Use document.querySelector() to select the container element where the cart products will be displayed.

## Use document.importNode() to clone the template container for each cart product.

## Update the content of the cloned template with the product details (category, name, image, etc.).

## Append the cloned template to the container element to display the cart products on the page.

====================================================
**_ Fetch Actual Quantity and Price _**
====================================================

## Implement a function named fetchQuantityFromCartLS to retrieve the actual quantity and price of a product from the cart stored in local storage.

## Import the getCartProductFromLocalStorage function to access the cart product data.

## Use the find method to search for the product with the provided ID in the cart product data.

## Set a default quantity value of 1 if the product is not found in the cart.

## If the product exists in the cart, retrieve its quantity and price from the cart product data.

## Ensure that the price is formatted as a number with two decimal places.

## Return an object containing the quantity and price of the product.

====================================================
**_ Handle Removal from Cart _**
====================================================

## Create a function named removeTheCardFromCart to remove a product from the cart.

## Import the getCartProductFromLocalStorage function to access the cart product data.

## Import the updateCartValue function to update the cart value after removing the product.

## Retrieve the cart product data from local storage.

## Use the filter method to remove the product with the provided ID from the cart product data.

## Update the cart product data in local storage after removing the product.

## Remove the corresponding HTML element of the removed product from the cart display on the page.

## Ensure that the cart value is updated after the product is removed.

================================================================
**_ Handle Increment and Decrement in Add to Cart Page _**
================================================================

## Create a function named incrementDecrement to handle the increment and decrement operations for a product in the add to cart page.

## Import the getCartProductFromLocalStorage function to access cart product data from local storage.

## Retrieve the current card element based on the provided ID.

## Retrieve the product quantity and price elements from the current card element.

## Get the cart product data from local storage and find the product with the provided ID.

## If the product does not exist in the cart, set the localStoragePrice to the provided price.

## If the product exists in the cart, retrieve its quantity and price from the cart product data.

## Increment the quantity if the increment button is clicked and the current quantity is less than the stock.

## Decrement the quantity if the decrement button is clicked and the current quantity is greater than 1.

## Calculate the updated price based on the updated quantity.

## Update the price in local storage for the product.

## Save the updated cart data back to local storage.

## Update the quantity and price elements on the screen to reflect the changes.

================================================================
**_ Update Cart Product Total _**
================================================================

## Implement a function named updateCartProductTotal to update the total cart price value and subtotal.

## Import the getCartProductFromLocalStorage function to access cart product data from local storage.

## Retrieve the elements representing the product subtotal and final total from the DOM.

## Initialize a variable initialValue with a value of 0 to use as the initial value for the reduce function.

## Use the reduce method to calculate the total order price by summing up the prices of all products in the cart.

## Ensure that the product price is converted to a number and default to 0 if it cannot be converted.

## Update the text content of the product subtotal and final total elements with the calculated values.

## Display the total order price as currency format with two decimal places.

**_ Conclusion _**

## You've implemented functionality to update the total cart price value and subtotal based on the products in the cart. This ensures that users can view the total cost of their order and make informed decisions during checkout.

==============================================
**_ Extra Information on Vite _**

# In this vite.config.js file:

# We import the defineConfig function from Vite to define our configuration.

# We also import the resolve function from the Node.js path module to resolve file paths.

# We export a default configuration object using defineConfig.

# Within the configuration object, we specify the build property to configure the build process.

# Inside build, we define rollupOptions, which allows us to configure Rollup, the underlying bundler used by Vite.

# Within rollupOptions, we specify the input property, which defines the entry points for the build process.

# Each key in the input object corresponds to an entry point. The key name is arbitrary and is used to name the resulting bundle.

# The value for each key is the resolved path to the corresponding HTML file using the resolve function. This sets each HTML file as an entry point for the bundling process.

# We use \_\_dirname to ensure that the paths are resolved relative to the directory of the vite.config.js file.

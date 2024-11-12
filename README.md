# Mast![snip 1](https://github.com/user-attachments/assets/648ab0e6-28d3-4141-bd8d-4c2b383a9c45)
![snip 2](https://github.com/user-attachments/assets/71ea759b-91cd-46b1-acd4-6155ec51da78)
![snip3](https://github.com/user-attachments/assets/dd677e29-57c6-438a-ac8f-d6453b54c70b)
![snip4](https://github.com/user-attachments/assets/5f4575c0-e633-44d7-93f2-4f1af1a797aa)
[Uplo<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Menu Item App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .container {
            max-width: 600px;
            margin: auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-shadow: 2px 2px 12px #aaa;
        }
        h1 {
            text-align: center;
        }
        input, select, button {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
        }
        #menuList {
            margin-top: 20px;
        }
        .menuItem {
            border: 1px solid #ccc;
            padding: 10px;
            margin-bottom: 10px;
            border-radius: 5px;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Menu Item App</h1>
    <input type="text" id="dishName" placeholder="Dish Name" required>
    <input type="text" id="description" placeholder="Description" required>
    
    <select id="course">
        <option value="Starter">Starter</option>
        <option value="Main">Main</option>
        <option value="Dessert">Dessert</option>
    </select>
    
    <input type="number" id="price" placeholder="Price" required min="0" step="0.01">

    <button onclick="addMenuItem()">Add Menu Item</button>

    <div id="menuList">
        <h2>Menu Items</h2>
    </div>
</div>

<script>
    function addMenuItem() {
        const dishName = document.getElementById('dishName').value;
        const description = document.getElementById('description').value;
        const course = document.getElementById('course').value;
        const price = parseFloat(document.getElementById('price').value);

        if (!dishName || !description || isNaN(price) || price < 0) {
            alert("Please fill all fields correctly.");
            return;
        }

        const menuItem = document.createElement('div');
        menuItem.classList.add('menuItem');
        menuItem.innerHTML = `
            <strong>Dish:</strong> ${dishName}<br>
            <strong>Description:</strong> ${description}<br>
            <strong>Course:</strong> ${course}<br>
            <strong>Price:</strong> $${price.toFixed(2)}
        `;

        document.getElementById('menuList').appendChild(menuItem);

        // Clear input fields
        document.getElementById('dishName').value = '';
        document.getElementById('description').value = '';
        document.getElementById('price').value = '';
        document.getElementById('course').value = 'Starter'; // Reset to default
    }
</script>

</body>
</html>ading index.html…]()

Changes made 

i have changed the css styling for my code amd i have more pages to my code i also added sliders and filters to my code the only problem was the emulator as the type script has unclearable errors for some reason but everything else works
index code 
 <header>
        <h1>Restaurant Menu App - Home</h1>
    </header>

    <div id="home-content">
        <h2>Complete Menu</h2>
        <button onclick="window.location.href = 'manage.html';">Manage Menu</button>
        <button onclick="window.location.href = 'filter.html';">Filter Menu</button>

        <div id="menu-items">
            <!-- Menu items will be displayed here -->
        </div>
        <div id="avg-prices">
            <!-- Average prices by course will be displayed here -->
        </div>
    </div>

    <script src="script.js"></script>
    <script>
        // Call displayMenuItems on page load
        displayMenuItems();
    </script>
</body>
</html>

menu code 
!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Restaurant Menu App - Manage Menu</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header>
        <h1>Restaurant Menu App - Manage Menu</h1>
    </header>

    <div id="manage-content">
        <button onclick="window.location.href = 'index.html';">Back to Home</button>
        <button onclick="showAddMenuForm()">Add Menu Item</button>

        <div id="manage-form" style="display:none;">
            <input type="text" id="item-name" placeholder="Item Name" />
            <input type="number" id="item-price" placeholder="Item Price" />
            <select id="item-course">
                <option value="Starters">Starters</option>
                <option value="Main Courses">Main Courses</option>
                <option value="Desserts">Desserts</option>
            </select>
            <button onclick="saveMenuItem()">Save Item</button>
        </div>

        <div id="remove-menu">
            <h3>Remove Menu Item</h3>
            <select id="remove-item">
                
            </select>
            <button onclick="removeMenuItem()">Remove Item</button>
        </div>
    </div>

    <script src="script.js"></script>
    <script>
       
        loadRemoveMenuOptions();
    </script>
</body>
</html>

filter code 
!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Restaurant Menu App - Filter Menu</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header>
        <h1>Restaurant Menu App - Filter Menu</h1>
    </header>

    <div id="filter-content">
        <button onclick="window.location.href = 'index.html';">Back to Home</button>
        <button onclick="filterMenu('Starters')">Starters</button>
        <button onclick="filterMenu('Main Courses')">Main Courses</button>
        <button onclick="filterMenu('Desserts')">Desserts</button>

        <div id="filtered-items">
            
        </div>
    </div>

    <script src="script.js"></script>
    <script>
        
        filterMenu('Starters');
    </script>
</body>
</html>

css styling 
 body{
    font-family: Arial, sans-serif; 
    background-color: #e0f7e9; 
    color: #333; 
    margin: 0;
    padding: 0;
}


.container {
    width: 80%;
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    background-color: #ffffff; 
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}


header {
    text-align: center;
    padding: 10px;
    font-size: 24px;
    font-weight: bold;
    color: #2e7d32; 
}


#menu-items div, #filtered-items div {
    background-color: #a5d6a7; 
    border: 1px solid #81c784; 
    padding: 10px;
    margin: 5px 0;
    border-radius: 5px;
    font-size: 18px;
}


#avg-prices div {
    font-weight: bold;
    color: #388e3c; 
    margin-top: 10px;
}


button {
    background-color: #66bb6a; 
    color: white;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #4caf50; 
}


form {
    margin-top: 20px;
}

form input, form select {
    width: 100%;
    padding: 8px;
    margin: 10px 0;
    border: 1px solid #ccc;
    border-radius: 4px;
}


#filtered-items {
    padding-top: 10px;
    font-size: 18px;
}

transcript
let menuItems = JSON.parse(localStorage.getItem('menuItems')) || [];


function displayMenuItems() {
    const menuContainer = document.getElementById('menu-items');
    const avgPriceContainer = document.getElementById('avg-prices');

    if (menuContainer) {  
        menuContainer.innerHTML = '';
        if (menuItems.length === 0) {
            menuContainer.innerHTML = 'No menu items available.';
        } else {
            menuItems.forEach(item => {
                const itemDiv = document.createElement('div');
                itemDiv.textContent = ${item.name} - $${item.price} - ${item.course};
                menuContainer.appendChild(itemDiv);
            });
        }

        
        const courses = ['Starters', 'Main Courses', 'Desserts'];
        avgPriceContainer.innerHTML = '';
        courses.forEach(course => {
            const avgPrice = calculateAveragePrice(course);
            const avgPriceDiv = document.createElement('div');
            avgPriceDiv.textContent = ${course}: $${avgPrice.toFixed(2)};
            avgPriceContainer.appendChild(avgPriceDiv);
        });
    }
}


function calculateAveragePrice(courseType) {
    const courseItems = menuItems.filter(item => item.course === courseType);
    if (courseItems.length === 0) return 0;
    const totalPrice = courseItems.reduce((sum, item) => sum + item.price, 0);
    return totalPrice / courseItems.length;
}


function showAddMenuForm() {
    const manageForm = document.getElementById('manage-form');
    if (manageForm) {
        manageForm.style.display = 'block';
    }
}


function saveMenuItem() {
    const name = document.getElementById('item-name').value;
    const price = parseFloat(document.getElementById('item-price').value);
    const course = document.getElementById('item-course').value;

    if (!name || isNaN(price) || price <= 0) {
        alert('Please fill in valid item details.');
        return;
    }

    menuItems.push({ name, price, course });
    localStorage.setItem('menuItems', JSON.stringify(menuItems));
    alert('Menu item added successfully!');
    window.location.href = 'index.html'; 


function loadRemoveMenuOptions() {
    const removeSelect = document.getElementById('remove-item');
    if (removeSelect) {
        removeSelect.innerHTML = '';
        menuItems.forEach(item => {
            const option = document.createElement('option');
            option.value = item.name;
            option.textContent = item.name;
            removeSelect.appendChild(option);
        });
    }
}


function removeMenuItem() {
    const name = document.getElementById('remove-item').value;
    if (!name) {
        alert('Please select a menu item to remove.');
        return;
    }

    menuItems = menuItems.filter(item => item.name !== name);
    localStorage.setItem('menuItems', JSON.stringify(menuItems));
    alert('Menu item removed successfully!');
    window.location.href = 'index.html'; 


function filterMenu(courseType) {
    const filteredItems = menuItems.filter(item => item.course === courseType);
    const filteredItemsContainer = document.getElementById('filtered-items');
    if (filteredItemsContainer) {
        filteredItemsContainer.innerHTML = '';

        if (filteredItems.length === 0) {
            filteredItemsContainer.innerHTML = No ${courseType} available.;
        } else {
            filteredItems.forEach(item => {
                const itemDiv = document.createElement('div');
                itemDiv.textContent = ${item.name} - $${item.price};
                filteredItemsContainer.appendChild(itemDiv);
            });
        }
    }
}


if (window.location.pathname.endsWith('index.html')) {
    displayMenuItems();
}


if (window.location.pathname.endsWith('manage.html')) {
    loadRemoveMenuOptions();
}


if (window.location.pathname.endsWith('filter.html')) {
    filterMenu('Starters');  lt course filter here
}


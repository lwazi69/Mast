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

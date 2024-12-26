<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RELLX INCOME</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }
        header {
            background-color: #2c3e50;
            color: white;
            padding: 15px;
            text-align: center;
        }
        main {
            margin: 20px;
        }
        .form-container {
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .form-container label {
            display: block;
            margin-bottom: 10px;
            font-weight: bold;
        }
        .form-container input, .form-container button {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        .form-container button {
            background-color: #27ae60;
            color: white;
            border: none;
            cursor: pointer;
        }
        .form-container button:hover {
            background-color: #219150;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        table th, table td {
            border: 1px solid #ddd;
            padding: 10px;
            text-align: left;
        }
        table th {
            background-color: #f2f2f2;
        }
        footer {
            text-align: center;
            padding: 10px;
            background-color: #2c3e50;
            color: white;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>

<header>
    <h1>RELLX INCOME</h1>
    <p>Track your time and income effectively</p>
</header>

<main>
    <div class="form-container">
        <h2>Add New Entry</h2>
        <form id="incomeForm">
            <label for="task">Task Name:</label>
            <input type="text" id="task" name="task" placeholder="Enter task name" required>

            <label for="hours">Hours Worked:</label>
            <input type="number" id="hours" name="hours" placeholder="Enter hours" required>

            <label for="rate">Hourly Rate ($):</label>
            <input type="number" id="rate" name="rate" placeholder="Enter hourly rate" required>

            <button type="submit">Add Entry</button>
        </form>
    </div>

    <table>
        <thead>
            <tr>
                <th>Task</th>
                <th>Hours</th>
                <th>Rate ($)</th>
                <th>Total Income ($)</th>
            </tr>
        </thead>
        <tbody id="incomeData">
            <!-- Entries will appear here -->
        </tbody>
    </table>
</main>

<footer>
    <p>&copy; 2024 RELLX INCOME. All rights reserved.</p>
</footer>

<script>
    const form = document.getElementById('incomeForm');
    const incomeData = document.getElementById('incomeData');

    form.addEventListener('submit', (e) => {
        e.preventDefault();

        const task = document.getElementById('task').value;
        const hours = parseFloat(document.getElementById('hours').value);
        const rate = parseFloat(document.getElementById('rate').value);
        const total = hours * rate;

        const row = document.createElement('tr');
        row.innerHTML = `
            <td>${task}</td>
            <td>${hours}</td>
            <td>${rate.toFixed(2)}</td>
            <td>${total.toFixed(2)}</td>
        `;
        incomeData.appendChild(row);

        form.reset();
    });
</script>

</body>
</html>

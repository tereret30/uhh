 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Draft</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f9f9f9;
        }

        header {
            background-color: #4a4947;
            color: white;
            padding: 10px 20px;
            text-align: center;
        }

        nav {
            display: flex;
            justify-content: center;
            background-color: #757869;
        }

        nav a {
            color: white;
            text-decoration: none;
            padding: 10px 20px;
            display: block;
        }

        nav a:hover {
            background-color: #b3ab98;
        }

        section {
            padding: 20px;
        }

        .hidden {
            display: none;
        }

        table {
            margin-top: 10px;
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            border: 1px solid black;
            padding: 8px;
            text-align: center;
        }

        th {
            background-color: #3C3D37;
            color: white;
        }

        tr:nth-child(even) {
            background-color: #7c806a;
        }

        tr:nth-child(odd) {
            background-color: #ECDFCC;
        }

        tr:hover {
            background-color: #757869;
        }
    </style>
</head>
<body>
    <header>
        <h1>Draft</h1>
    </header>
    <nav>
        <a href="#unitConverter" onclick="showSection('unitConverter')">Unit Converter</a>
        <a href="#incomeTaxCalculator" onclick="showSection('incomeTaxCalculator')">Income Tax Calculator</a>
        <a href="#naturalNumbers" onclick="showSection('naturalNumbers')">Natural Numbers</a>
        <a href="#payrollSystem" onclick="showSection('payrollSystem')">Payroll System</a>
    </nav>

    <section id="unitConverter">
    <h1>Unit Converter</h1>
    <html>
    <body>

    <div class="converter">
        <h2>Fahrenheit to Celsius</h2>
        <label for="fahrenheit">Fahrenheit:</label>
        <input type="number" id="fahrenheit" placeholder="Enter value">
        <button id="convertFahrenheitToCelsius">Convert</button>
        <button id="ftcclearvalues">Clear Values</button> 
        <br>
        <label for="FtoCresult">Result:</label>
        <input id="FtoCresult" readonly>
    </div>

    <div class="converter">
        <h2>Celsius to Fahrenheit</h2>
        <label for="celsius">Celsius:</label>
        <input type="number" id="celsius" placeholder="Enter value">
        <button id="convertCelsiusToFahrenheit">Convert</button>
        <button id="ctfclearvalues">Clear Values</button> 
        <br>
        <label for="CtoFresult">Result:</label>
        <input id="CtoFresult" readonly>
    </div>

    <div class="converter">
        <h2>Meters to Feet</h2>
        <label for="meters">Meters:</label>
        <input type="number" id="meters" placeholder="Enter value">
        <button id="convertMetersToFeet">Convert</button>
        <button id="mtfclearvalues">Clear Values</button> 
        <br>
        <label for="MtoFTresult">Result:</label>
        <input id="MtoFTresult" readonly>
    </div>

    <div class="converter">
        <h2>Feet to Meters</h2>
        <label for="feet">Feet:</label>
        <input type="number" id="feet" placeholder="Enter value">
        <button id="convertFeetToMeters">Convert</button>
        <button id="ftmclearvalues">Clear Values</button> 
        <br>
        <label for="FTtoMresult">Result:</label>
        <input id="FTtoMresult" readonly>
    </div>

    <script>
        document.getElementById("convertFahrenheitToCelsius").addEventListener("click", ()=>
        {
            var F, C;

            F = parseFloat(document.getElementById("fahrenheit").value);
            C = (F - 32) * 5 / 9;

            document.getElementById("FtoCresult").value = `${C.toFixed(2)}\u00B0C`;
        });

        document.getElementById("ftcclearvalues").addEventListener("click", ()=>
        {
            document.getElementById("fahrenheit").value='';
            document.getElementById("FtoCresult").value='';
        });

        document.getElementById("convertCelsiusToFahrenheit").addEventListener("click", ()=>
        {
            var C, F;

            C = parseFloat(document.getElementById("celsius").value);
            F = (C * 9 / 5) + 32;

            document.getElementById("CtoFresult").value = `${F.toFixed(2)}\u00B0C`;
        });

        document.getElementById("ctfclearvalues").addEventListener("click", ()=>
        {
            document.getElementById("celsius").value='';
            document.getElementById("CtoFresult").value='';
        });

        document.getElementById("convertMetersToFeet").addEventListener("click", ()=>
        {
            var m, ft;

            m = parseFloat(document.getElementById("meters").value);
            ft = m * 3.28084;

            document.getElementById("MtoFTresult").value = `${ft.toFixed(2)} feet`;
        });

        document.getElementById("mtfclearvalues").addEventListener("click", ()=>
        {
            document.getElementById("meters").value='';
            document.getElementById("MtoFTresult").value='';
        });

        document.getElementById("convertFeetToMeters").addEventListener("click", ()=>
        {
            var ft, m;

            ft = parseFloat(document.getElementById("feet").value);
            m = ft / 3.28084;

            document.getElementById("FTtoMresult").value = `${m.toFixed(2)} meters`;
        });

        document.getElementById("ftmclearvalues").addEventListener("click", ()=>
        {
            document.getElementById("feet").value='';
            document.getElementById("FTtoMresult").value='';
        });
    </script>
</body>
</html>
    </section>

    <section id="incomeTaxCalculator" class="hidden">
        <h2>Income Tax Calculator</h2>
        <html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Income Tax Calculator</title>
</head>
<body>
    <label for="taxableIncome">Enter your taxable income: </label>
    <input type="number" id="taxableIncome" step="0.01" placeholder="Enter amount">
    <button id="calculateTax">Compute Tax</button>
    <button id="ITclearvalues">Clear Values</button> 
    <br>

    <p id="result">Income Tax: </p>

    <script>
        document.getElementById("calculateTax").addEventListener("click", ()=>
        {
            
            const taxableIncome = parseFloat(document.getElementById("taxableIncome").value);
            let tax = 0;

            if (taxableIncome <= 250000) {
                tax = 0;
            } else if (taxableIncome <= 400000) {
                tax = (taxableIncome - 250000) * 0.20;
            } else if (taxableIncome <= 800000) {
                tax = 30000 + (taxableIncome - 400000) * 0.25;
            } else if (taxableIncome <= 2000000) {
                tax = 130000 + (taxableIncome - 800000) * 0.30;
            } else if (taxableIncome <= 8000000) {
                tax = 490000 + (taxableIncome - 2000000) * 0.32;
            } else {
                tax = 2410000 + (taxableIncome - 8000000) * 0.35;
            }

            document.getElementById("result").textContent = 
                `Income Tax: ₱${tax.toFixed(2)}`;
        });

        document.getElementById("ITclearvalues").addEventListener("click", ()=>
        {
            document.getElementById("taxableIncome").value='';
            document.getElementById("result").textContent='Income Tax: ';
        });
    </script>
</body>
</html>
    </section>

    <section id="naturalNumbers" class="hidden">
        <h2>Natural Number Calculations</h2>
        <html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Natural Number Calculations</title>
</head>
<body>
    <label for="numberInput">Integer (n):</label>
    <input type="number" id="numberInput" min="1" placeholder="Enter a valid integer">
    <button id="calculate">Calculate</button>
    <button id="nnclearvalues">Clear Values</button>

    <h3>Results:</h3>
    <p id="factorialResult">The factorial is: </p>
    <p id="sumResult">The sum is: </p>
    <p id="averageResult">The average is: </p>

    <script>
        document.getElementById("calculate").addEventListener("click", ()=>
        {
            // Get the input value
            const n = parseInt(document.getElementById("numberInput").value);

            if (isNaN(n) || n < 1) {
                alert("Please enter a valid integer greater than or equal to 1.");
                return;
            }

            // Calculate factorial using a while loop
            let factorial = 1;
            let i = n;
            while (i > 0) {
                factorial *= i;
                i--;
            }

            // Calculate sum using a do-while loop
            let sum = 0;
            let j = 1;
            do {
                sum += j;
                j++;
            } while (j <= n);

            // Calculate average using a for loop
            let average = 0;
            for (let k = 1; k <= n; k++) {
                average += k;
            }
            average = average / n;

            // Display results3
            document.getElementById("factorialResult").textContent = `The factorial of ${n} is: ${factorial}`;
            document.getElementById("sumResult").textContent = `The sum of the first ${n} numbers is: ${sum}`;
            document.getElementById("averageResult").textContent = `The average of the first ${n} numbers is: ${average.toFixed(2)}`;
        });

        document.getElementById("nnclearvalues").addEventListener("click", ()=>
        {
            document.getElementById("factorialResult").textContent = 'The factorial is: ';
            document.getElementById("sumResult").textContent = 'The sum is: ';
            document.getElementById("averageResult").textContent = 'The average is: ';
            document.getElementById("numberInput").value = '';
        });

    </script>
</body>
</html>
    </section>

    <section id="payrollSystem" class="hidden">
        <h2>Payroll System</h2>
        <html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Payroll System</title>
    <style>
        /* Table styles */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }

        th, td {
            border: 1px solid black;
            padding: 8px;
            text-align: center;
        }

        th {
            background-color: #3C3D37;
            color: white;
        }

        tr:nth-child(even) {
            background-color: #7c806a;
        }

        tr:nth-child(odd) {
            background-color: #ECDFCC;
        }

        tr:hover {
            background-color: #757869;
        }

        td {
            color: #333;
        }

        button {
            padding: 5px 10px;
            margin: 5px 0;
            background-color: #D8D2C2;
            color: #4A4947;
            border: none;
            cursor: pointer;
        }

        button:hover {
            background-color: #b3ab98;
        }

        input {
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <h3>Add Employee</h3>
    <label for="employeeName">Employee Name:</label>
    <input type="text" id="employeeName" placeholder="Enter name"><br>
    <label for="daysWorked">Days Worked:</label>
    <input type="number" id="daysWorked" min="0" placeholder="Enter days worked"><br>
    <label for="dailyRate">Daily Rate:</label>
    <input type="number" id="dailyRate" min="0" placeholder="Enter daily rate"><br>
    <label for="deduction">Deduction Amount:</label>
    <input type="number" id="deduction" min="0" placeholder="Enter deduction"><br>
    <button id="addEmployee">Add Employee</button>

    <h3>Delete Employee</h3>
    <label for="lineNumber">Line Number to Delete:</label>
    <input type="number" id="lineNumber" min="1" placeholder="Enter line number"><br>
    <button id="deleteEmployee">Delete Employee</button>

    <h3>Payroll Table</h3>
    <table id="payrollTable">
        <thead>
            <tr>
                <th>No.</th>
                <th>Employee Name</th>
                <th>Days Worked</th>
                <th>Daily Rate</th>
                <th>Gross Pay</th>
                <th>Deduction Amount</th>
                <th>Net Pay</th>
            </tr>
        </thead>
        <tbody>
        </tbody>
    </table>

    <button id="clearList">Clear List</button>

    <script>
        let payrollList = [];

        function updateTable() {
            const tableBody = document.querySelector("#payrollTable tbody");
            tableBody.innerHTML = ""; // Clear table

            payrollList.forEach((employee, index) => 
            {
                const grossPay = employee.daysWorked * employee.dailyRate;
                const netPay = grossPay - employee.deduction;

                const row = document.createElement("tr");
                row.innerHTML = 
                      "<td>" + (index + 1) + "</td>" 
                    + "<td>" + employee.name + "</td>" 
                    + "<td>" + employee.daysWorked + "</td>" 
                    + "<td>" + employee.dailyRate.toFixed(2) + "</td>" 
                    + "<td>" + grossPay.toFixed(2) + "</td>" 
                    + "<td>" + employee.deduction.toFixed(2) + "</td>" 
                    + "<td>" + netPay.toFixed(2) + "</td>";
                tableBody.appendChild(row);
            });
        }

        document.getElementById("addEmployee").addEventListener("click", () => 
        {
            const name = document.getElementById("employeeName").value.trim();
            const daysWorked = parseInt(document.getElementById("daysWorked").value);
            const dailyRate = parseFloat(document.getElementById("dailyRate").value);
            const deduction = parseFloat(document.getElementById("deduction").value);

            if (!name || isNaN(daysWorked) || isNaN(dailyRate) || isNaN(deduction)) {
                alert("Please fill out all fields with valid values.");
                return;
            }

            payrollList.push({ name, daysWorked, dailyRate, deduction });
            updateTable();

            document.getElementById("employeeName").value = "";
            document.getElementById("daysWorked").value = "";
            document.getElementById("dailyRate").value = "";
            document.getElementById("deduction").value = "";
        });

        document.getElementById("deleteEmployee").addEventListener("click", () => 
        {
            const lineNumber = parseInt(document.getElementById("lineNumber").value);

            if (isNaN(lineNumber) || lineNumber < 1 || lineNumber > payrollList.length) {
                alert("Please enter a valid line number.");
                return;
            }

            const confirmation = confirm("Are you sure you want to delete line number " + lineNumber + "?");
            if (!confirmation) {
                return;
            }

            payrollList.splice(lineNumber - 1, 1);
            updateTable();

            document.getElementById("lineNumber").value = "";
        });

        document.getElementById("clearList").addEventListener("click", () => 
        {
            const confirmation = confirm("Are you sure you want to clear the entire payroll list?");
            if (confirmation) {
                payrollList = []; 
                updateTable(); 
            }
        });

        updateTable();
    </script>
</body>
</html>
    </section>

    <script>
        function showSection(sectionId) {
            // Hide all sections
            document.querySelectorAll("section").forEach((section) => {
                section.classList.add("hidden");
            });
            // Show the selected section
            document.getElementById(sectionId).classList.remove("hidden");
        }
    </script>
</body>
</html>

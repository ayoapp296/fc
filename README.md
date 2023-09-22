<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KYC Form</title>
    <style>
        /* Add your CSS styling here */
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #fff;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-shadow: 0 2px 5px #aaa;
        }

        h2 {
            text-align: center;
        }

        label {
            font-weight: bold;
        }

        input[type="text"],
        input[type="email"],
        input[type="date"],
        input[type="tel"],
        select,
        textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 3px;
        }

        button[type="submit"] {
            background-color: #007BFF;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }

        .beneficiary-section {
            border: 1px solid #ccc;
            padding: 10px;
            margin-top: 20px;
        }

        .beneficiary-section h3 {
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>KYC Form</h2>
        <form id="kycForm">
            <label for="fullName">Full Name:</label>
            <input type="text" id="fullName" name="fullName" required>

            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>

            <label for="phoneNumber">Phone Number:</label>
            <input type="tel" id="phoneNumber" name="phoneNumber" required>

            <label for="idNumber">ID Number:</label>
            <input type="text" id="idNumber" name="idNumber" required>

            <label for="companyName">Company Name:</label>
            <input type="text" id="companyName" name="companyName" required>

            <label for="coverType">Select Cover:</label>
            <select id="coverType" name="coverType" required>
                <option value="ayocare">aYo Care</option>
                <option value="family">Family Cover</option>
            </select>

            <label for="premiumAmount">Select Premium Amount:</label>
            <select id="premiumAmount" name="premiumAmount" required>
                <option value="5.00">K5.00 (Life Cover = K5,000)</option>
                <option value="10.00">K10.00 (Life Cover = K10,000)</option>
                <option value="15.00">K15.00 (Illness = K1,000, Accidental = K2,000, Life = K5,000)</option>
                <option value="20.00">K20.00 (Illness = K2,000, Accidental = K4,000)</option>
                <option value="30.00">K30.00 (Illness = K2,000, Accidental = K4,000, Life = K10,000)</option>
            </select>

            <label for="address">Address:</label>
            <textarea id="address" name="address" rows="4" required></textarea>

            <label for="jobTitle">Job Title:</label>
            <input type="text" id="jobTitle" name="jobTitle" required>

            <label for="caretakerName">Caretaker or Loved One Name:</label>
            <input type="text" id="caretakerName" name="caretakerName" required>

            <!-- Beneficiaries Section -->
            <div class="beneficiary-section">
                <h3>Beneficiary 1</h3>
                <label for="beneficiary1Name">Name:</label>
                <input type="text" id="beneficiary1Name" name="beneficiary1Name" required>

                <label for="beneficiary1Dob">Date of Birth:</label>
                <input type="date" id="beneficiary1Dob" name="beneficiary1Dob" required>

                <label for="beneficiary1Id">ID Number:</label>
                <input type="text" id="beneficiary1Id" name="beneficiary1Id" required>

                <label for="beneficiary1Relationship">Relationship:</label>
                <input type="text" id="beneficiary1Relationship" name="beneficiary1Relationship" required>
            </div>

            <!-- Repeat the beneficiary section for beneficiaries 2 to 6, changing the headings and IDs accordingly -->

            <!-- Display the total amount to pay -->
            <p>Total Amount to Pay: <span id="totalAmount"></span></p>

            <button type="submit">Submit</button>
        </form>
    </div>

    <script>
        // JavaScript code for form submission and total amount calculation
        const kycForm = document.getElementById('kycForm');
        const premiumAmountSelect = document.getElementById('premiumAmount');
        const totalAmount = document.getElementById('totalAmount');

        kycForm.addEventListener('submit', function (e) {
            e.preventDefault();

            // You can add code here to handle form submission,
            // such as sending the data to a server or performing validations.

            alert('KYC form submitted successfully!');
        });

        premiumAmountSelect.addEventListener('change', function () {
            const selectedPremium = parseFloat(premiumAmountSelect.value);
            totalAmount.textContent = `K${selectedPremium.toFixed(2)}`;
        });

        // Initialize the total amount when the page loads
        totalAmount.textContent = `K${parseFloat(premiumAmountSelect.value).toFixed(2)}`;
    </script>
</body>
</html>


<html>
<head>
    <title>Multiple Shade Selection for Zirconia Only</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
        }
        img {
            width: 500px; /* Increased logo size */
            margin-bottom: 10px;
        }
        h1 {
            font-size: 24px;
        }
        h3 {
            font-size: 16px;
            color: gray;
        }
        input {
            margin: 5px;
            padding: 5px;
        }
        button {
            padding: 8px 12px;
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        p {
            font-weight: bold;
            margin-top: 15px;
        }
    </style>
</head>
<body>

    <!-- Company Logo -->
    <img src="OIP.jpeg" alt="Company Logo">

    <!-- Main Title and Subtitle -->
    <h1>Multiple Shade Selection for Zirconia Only</h1>
    <h3>Please input all shades provided on the prescription.</h3>

    <!-- Shade Input Form -->
    <label>Incisal Shade: <input type="text" id="incisal"></label><br>
    <label>Body/Mid Shade: <input type="text" id="body"></label><br>
    <label>Gingival Shade: <input type="text" id="gingival"></label><br>
    <button onclick="displayShade()">Submit</button>

    <!-- Output Section -->
    <p>Selected Shade: <span id="output"></span></p>

    <script>
        function displayShade() {
            // Get input values
            let incisalShade = document.getElementById("incisal").value.trim();
            let bodyShade = document.getElementById("body").value.trim();

            // If incisal shade is empty, use body shade; if both are empty, display default message
            let finalShade = incisalShade || bodyShade || "No shade entered";

            // Display the selected shade
            document.getElementById("output").innerText = finalShade;
        }
    </script>

</body>
</html>

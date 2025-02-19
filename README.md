<title> Multipl Shade Selection for Zirconia Only</title>
<html>
<head>
    <title> Input all shades provided on Rx</title>
</head>
</head>
<body>
       <!-- Company Logo -->
    <img src="OIP.jpeg alt="Company Logo" width="400">
    <h2>Shade Selection</h2>
    <label>Incisal Shade: <input type="text" id="incisal"></label><br>
    <label>Body/Mid Shade: <input type="text" id="body"></label><br>
    <label>Gingival Shade: <input type="text" id="gingival"></label><br>
    <button onclick="getIncisalShade()">Submit</button>
    <p>Selected Incisal Shade: <span id="output"></span></p>

    <script>
        function getIncisalShade() {
            let incisalShade = document.getElementById("incisal").value;
            
            // Output only the incisal shade
            document.getElementById("output").innerText = incisalShade || "No incisal shade entered";
        }
    </script>
</body>
</html>

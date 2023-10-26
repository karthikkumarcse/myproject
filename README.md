//html
<!DOCTYPE html>
<html>
<head>
    <title>Smart Water Management System</title>
   
</head>
<body>
 <a href="C:\Users\admin\Desktop\dev tech\NM WEBSITE\img_files"<img src="front.jpg"></a>
    <h1>Water Consumption Platform</h1>
    <div id="dataContainer">
        <div class="sensorCard">
            <h2>Sensor 1</h2>
            <div class="sensorValue" id="sensor1Value">0</div>
            <div class="lastUpdated" id="sensor1LastUpdated"></div>
            <button class="promoteButton" onclick="promoteWaterConservation(1)">Promote</button>
        </div>
        <div class="sensorCard">
            <h2>Sensor 2</h2>
            <div class="sensorValue" id="sensor2Value">0</div>
            <div class="lastUpdated" id="sensor2LastUpdated"></div>
            <button class="promoteButton" onclick="promoteWaterConservation(2)">Promote</button>
        </div>
        <div class="sensorCard">
            <h2>Sensor 3</h2>
            <div class="sensorValue" id="sensor3Value">0</div>
            <div class="lastUpdated" id="sensor3LastUpdated"></div>
            <button class="promoteButton" onclick="promoteWaterConservation(3)">Promote</button>
        </div>
    </div>
	<br>
	<br>
	</body>
</html>


//css code
 body {
            font-family: Arial, sans-serif;
        }

        h1 {
            text-align: center;
            margin-top: 40px;
			color: blue;
        }

        #dataContainer {
            display: flex;
            justify-content: space-between;
        }

        .sensorCard {
            width: 300px;
            border: 1px solid #ccc;
            padding: 20px;
            margin-bottom: 20px;
        }

        h2 {
            margin-top: 0;
        }

        .sensorValue {
            font-size: 24px;
            font-weight: bold;
            color: #4CAF50;
            margin-bottom: 10px;
        }

        .lastUpdated {
            font-size: 12px;
            color: #888;
        }

        .promoteButton {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 8px 16px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin-top: 10px;
            cursor: pointer;
        }
     body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }

        .header {
            background-color: #f5f5f5;
            padding: 20px;
            text-align: center;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }

        .form-group input {
            width: 100%;
            padding: 10px;
            font-size: 16px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }

        .form-group button {
            padding: 10px 20px;
            font-size: 16px;
            border-radius: 5px;
            background-color: #4CAF50;
            color: #fff;
            border: none;
        }

        .result {
            margin-top: 20px;
            padding: 10px;
            background-color: #f5f5f5;
            border-radius: 5px;
        }
   

//jscode
 // JS
        function updateSensorValue(sensorId) {
            var sensorValue = Math.floor(Math.random() * 100); // Replace with actual sensor data

            var valueElement = document.getElementById("sensor" + sensorId + "Value");
            var lastUpdatedElement = document.getElementById("sensor" + sensorId + "LastUpdated");

            valueElement.textContent = sensorValue;
            lastUpdatedElement.textContent = "Last updated: " + new Date().toLocaleString();
        }

        function promoteWaterConservation(sensorId) {
            // Code to promote water conservation efforts
            alert("Promote water conservation for sensor " + sensorId);
        }

        setInterval(function() {
            // Update sensor values every 5 seconds
            updateSensorValue(1);
            updateSensorValue(2);
            updateSensorValue(3);
        }, 5000);

function calculateWaterUsage() {
            var showerDuration = parseFloat(document.getElementById("showerDuration").value);
            var flushesPerDay = parseInt(document.getElementById("flushesPerDay").value);
            var dishwasherFrequency = parseInt(document.getElementById("dishwasherFrequency").value);
            var dishwasherCycle = parseFloat(document.getElementById("dishwasherCycle").value);
            var washingMachineFrequency = parseInt(document.getElementById("washingMachineFrequency").value);
            var washingMachineCycle = parseFloat(document.getElementById("washingMachineCycle").value);
           
            var showerWaterUsage = showerDuration * 12; // Assuming average shower uses 12 liters of water per minute
            var toiletWaterUsage = flushesPerDay * 6; // Assuming average toilet flush uses 6 liters of water
            var dishwasherWaterUsage = dishwasherFrequency * dishwasherCycle * 15; // Assuming dishwasher uses 15 liters of water per cycle
            var washingMachineWaterUsage = washingMachineFrequency * washingMachineCycle * 40; // Assuming washing machine uses 40 liters of water per cycle
           
            var totalWaterUsage = showerWaterUsage + toiletWaterUsage + dishwasherWaterUsage + washingMachineWaterUsage;
           
            document.getElementById("result").innerHTML = "Total Water Usage: " + totalWaterUsage + " liters per day";
        }

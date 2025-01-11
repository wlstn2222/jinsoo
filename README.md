<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Color Language Exploration</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            text-align: center;
        }
        header {
            background: linear-gradient(to right, #32a852, #000080);
            color: white;
            padding: 20px;
        }
        .color-spectrum {
            display: flex;
            justify-content: center;
            margin: 20px;
        }
        .color-box {
            width: 40px;
            height: 40px;
            margin-right: 10px;
            cursor: grab;
        }
        .question-section {
            margin: 30px auto;
            text-align: center;
        }
        .language-container {
            display: flex;
            justify-content: space-around;
            width: 100%;
            margin: 20px auto;
        }
        .language-box {
            width: 30%;
            border: 2px solid #ccc;
            padding: 20px;
            text-align: center;
        }
        .input-box {
            margin: 10px 0;
        }
        .dropzone {
            border: 2px dashed #ccc;
            border-radius: 10px;
            padding: 20px;
            min-height: 100px;
            display: flex;
            flex-wrap: wrap;
            justify-content: flex-start;
        }
        .dropzone:hover {
            border-color: #32a852;
        }
        .result-section {
            margin-top: 30px;
        }
        input, button, select {
            padding: 10px;
            margin: 10px;
            font-size: 16px;
        }
        .multiselect {
            width: 60%;
            height: auto;
            padding: 10px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Color Language Exploration</h1>
        <p>Explore the connection between colors and languages</p>
    </header>

    <main>
        <section class="color-spectrum" id="colorSpectrum">
            <!-- Color boxes will be dynamically generated here -->
        </section>

        <section class="question-section">
            <h2>1. Where is your country?</h2>
            <input type="text" id="countryInput" placeholder="Enter your country">
    
                <div class="container">
                    <div class="question">
                        <label for="languageQuestion">
                        
                            <h2>2. Are you multilingual?
                              
                                (Multilingual individuals, please feel free to answer the question multiple times. )
                                
                        </label>
                    </div>
            
                    <div class="answer-input">
                        <textarea id="languageAnswer" placeholder="Answer here..."></textarea>
                <script>
                    function submitAnswer() {
                        const answer = document.getElementById('languageAnswer').value;
                        if (answer) {
                            alert('Your answer: ' + answer);
                        } else {
                            alert('Please provide an answer.');
                        }
                    }
                </script>
            
            </body>
            </html>
            
            <h2>3. Which language can you speak? (Select one)</h2>
            <select id="languageSelect" class="multiselect">
                <option value="English">English</option>
                <option value="Korean">Korean (한국어)</option>
                <option value="Japanese">Japanese (日本語)</option>
                <option value="Vietnamese">Vietnamese (Tiếng Việt)</option>
                <option value="Thai">Thai (ภาษาไทย)</option>
                <option value="Swedish">Swedish (Svenska)</option>
                <option value="Mongolian">Mongolian (Монгол хэл)</option>
                <option value="French">French (Français)</option>
                <option value="Spanish">Spanish (Castellano)</option>
                <option value="German">German (Deutsch)</option>
                <option value="Chinese">Chinese (中文)</option>
                <option value="Arabic">Arabic (العربية)</option>
                <option value="Hindi">Hindi (हिन्दी)</option>
                <option value="Portuguese">Portuguese (Português)</option>
                <option value="Russian">Russian (Русский)</option>
                <option value="Italian">Italian (Italiano)</option>
                <option value="Turkish">Turkish (Türkçe)</option>
                <option value="Dutch">Dutch (Nederlands)</option>
                <option value="Indonesian">Indonesian (Bahasa Indonesia)</option>
            </select>

            <h2>4. Write the name of the color and drag and drop colors to classify in your language:</h2>

            <div class="language-container">
                <!-- Left, Center, Right text input boxes -->
                <div class="language-box">
                    <input type="text" class="input-box" placeholder="Write color name (e.g., Green)">
                    <div class="dropzone" id="dropzone-left" ondrop="handleDrop(event)" ondragover="allowDrop(event)">Drop colors here</div>
                </div>

                <div class="language-box">
                    <input type="text" class="input-box" placeholder="Write color name (e.g., Blue)">
                    <div class="dropzone" id="dropzone-center" ondrop="handleDrop(event)" ondragover="allowDrop(event)">Drop colors here</div>
                </div>

                <div class="language-box">
                    <input type="text" class="input-box" placeholder="Write color name (e.g., Yellow)">
                    <div class="dropzone" id="dropzone-right" ondrop="handleDrop(event)" ondragover="allowDrop(event)">Drop colors here</div>
                </div>
            </div>

            <button onclick="submitData()">Submit</button>
        </section>

     

        <section class="result-section">
            <h2>5. World Map Visualization</h2>
            <div id="mapContainer">
                
                <body>

                
                    <meta charset="UTF-8">
                    <meta name="viewport" content="width=device-width, initial-scale=1.0">
                    <title>Color Language Exploration - Results</title>
                    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" />
                    <style>
                        body {
                            font-family: Arial, sans-serif;
                            margin: 0;
                            padding: 0;
                            text-align: center;
                        }
                        #map {
                            height: 500px;
                            width: 100%;
                        }
                        .dropdown-container {
                            margin: 20px;
                        }
                    </style>
                <body>
                    <p>Please drop down the coordinates of the country.</p>


    <div id="map"></div>

    <script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js"></script>
    <script>
        // Retrieve data from localStorage
        const userCountry = localStorage.getItem('userCountry');
        const userLanguage = localStorage.getItem('userLanguage');
        
        alert(`You selected: Country = ${userCountry}, Language = ${userLanguage}`);

        // Initialize the map
        var map = L.map('map').setView([20, 0], 2); // Set the map center (lat, lon) and zoom level

        // Add OpenStreetMap tiles
        L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
            attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
        }).addTo(map);

        // Extended Country Data with languages and locations
        const countryData = {

    "USA": { lat: 37.0902, lon: -95.7129, languages: { "English": "Green, Blue" } },
    "Germany": { lat: 51.1657, lon: 10.4515, languages: { "German": "Grün, Blau" } },
    "India": { lat: 20.5937, lon: 78.9629, languages: { "Hindi": "हरा, नीला" } },
    "Japan": { lat: 36.2048, lon: 138.2529, languages: { "Japanese": "緑, 青" } },
    "Spain": { lat: 40.4637, lon: -3.7492, languages: { "Spanish": "Verde, Azul" } },
    "China": { lat: 35.8617, lon: 104.1954, languages: { "Chinese": "绿色, 蓝色, 青" } },
    "France": { lat: 46.6034, lon: 1.8883, languages: { "French": "Vert, Bleu" } },
    "Italy": { lat: 41.8719, lon: 12.5674, languages: { "Italian": "Verde, Blu" } },
    "South Korea": { lat: 35.9078, lon: 127.7669, languages: { "Korean": "초록, 파랑, 청색" } },
    "Brazil": { lat: -14.2350, lon: -51.9253, languages: { "Portuguese": "Verde, Azul" } },
    "Mexico": { lat: 23.6345, lon: -102.5528, languages: { "Spanish": "Verde, Azul" } },
    "Russia": { lat: 55.7558, lon: 37.6173, languages: { "Russian": "Зеленый, Синий" } },
    "Turkey": { lat: 38.9637, lon: 35.2433, languages: { "Turkish": "Yeşil, Mavi" } },
    "Sweden": { lat: 60.1282, lon: 18.6435, languages: { "Swedish": "Grön, Blå" } },
    "Hong Kong": { lat: 22.3193, lon: 114.1694, languages: { "Cantonese": "綠色, 藍色" } },
    "Indonesia": { lat: -0.7893, lon: 113.9213, languages: { "Indonesian": "Hijau, Biru" } },
    "Australia": { lat: -25.2744, lon: 133.7751, languages: { "English": "Green, Blue" } },
    "Egypt": { lat: 26.8206, lon: 30.8025, languages: { "Arabic": "أخضر, أزرق" } },
    "Thailand": { lat: 15.8700, lon: 100.9925, languages: { "Thai": "เขียว, น้ำเงิน, สี" } },
    "Mongolia": { lat: 46.8625, lon: 103.8467, languages: { "Mongolian": "Ногоон, Цэнхэр" } },
    "Netherlands": { lat: 52.3676, lon: 4.9041, languages: { "Dutch": "Groen, Blauw" } },
    "Philippines": { lat: 12.8797, lon: 121.7740, languages: { "Filipino": "Berde, Asul" } },
    "Vietnam": { lat: 14.0583, lon: 108.2772, languages: { "Vietnamese": "Xanh, Xanh dương, Xanh lá" } },
    "Haiti": { lat: 18.9712, lon: -72.2852, languages: { "Haitian Creole": "Vè, Ble" } },
    "Canada": { lat: 56.1304, lon: -106.3468, languages: { "English": "Green, Blue", "French": "Vert, Bleu" } },
    "Ethiopia": { lat: 9.145, lon: 40.4897, languages: { "Amharic": "አረንጋጋት, ሰማያዊ" } },
    "Kenya": { lat: -1.2921, lon: 36.8219, languages: { "Swahili": "Kijani, Buluu", "English": "Green, Blue" } },
    "Tanzania": { lat: -6.369028, lon: 34.888822, languages: { "Swahili": "Kijani, Buluu", "English": "Green, Blue" } },
    "Uganda": { lat: 1.3733, lon: 32.2903, languages: { "Swahili": "Kijani, Buluu", "English": "Green, Blue" } },
    "Democratic Republic of the Congo": { lat: -4.0383, lon: 21.7587, languages: { "French": "Vert, Bleu", "Lingala": "Mokolo, Ebale" } },
    "Burundi": { lat: -3.3731, lon: 29.9189, languages: { "Kirundi": "Ikirundi, Ubushengero", "French": "Vert, Bleu" } },
    "Croatia": { lat: 45.1, lon: 15.2, languages: { "Croatian": "Zelena, Plava" } },
    "Finland": { lat: 61.9241, lon: 25.7482, languages: { "Finnish": "Vihreä, Sininen" } },
    "Kyrgyzstan": { lat: 41.2044, lon: 74.7661, languages: { "Kyrgyz": "Жашыл, Көк" } },
    "Uzbekistan": { lat: 41.3775, lon: 64.5853, languages: { "Uzbek": "Yashil, Ko'k" } },
    "Kazakhstan": { lat: 48.0196, lon: 66.9237, languages: { "Kazakh": "Жасыл, Көк" } }


};



        

        // Add markers for each country and display their language color info in a popup
        for (const [country, data] of Object.entries(countryData)) {
            const marker = L.marker([data.lat, data.lon]).addTo(map);

            // Prepare the language information as a dropdown
            let languageDropdown = '<select>';
            for (const [language, colors] of Object.entries(data.languages)) {
                languageDropdown += `<option value="${language}">${language}: ${colors}</option>`;
            }
            languageDropdown += '</select>';
            
            // Bind the popup with the country's language and color info
            marker.bindPopup(`
                <h3>${country}</h3>
                <p>Select the language and see the color names:</p>
                ${languageDropdown}
            `);
        }
    </script>
</body>


    <footer>
        &copy; 2025 Color Language Exploration. All rights reserved.
    </footer>

    <script>
        const languages = [
            "English", "Korean (한국어)", "Japanese (日本語)", "Vietnamese (Tiếng Việt)",
            "Thai (ภาษาไทย)", "Swedish (Svenska)", "Mongolian (Монгол хэл)", 
            "French (Français)", "Spanish (Castellano)", "German (Deutsch)", 
            "Chinese (中文)", "Arabic (العربية)", "Hindi (हिन्दी)", 
            "Portuguese (Português)", "Russian (Русский)", "Italian (Italiano)", 
            "Turkish (Türkçe)", "Dutch (Nederlands)", "Indonesian (Bahasa Indonesia)"
        ];

        function generateSpectrum() {
            const spectrum = document.getElementById('colorSpectrum');
            const shades = 50; // Number of shades
            for (let i = 0; i < shades; i++) {
                const ratio = i / (shades - 1);
                const red = Math.round(50 + ratio * (0 - 50));
                const green = Math.round(168 + ratio * (0 - 168));
                const blue = Math.round(82 + ratio * (128 - 82));

                const color = `rgb(${red}, ${green}, ${blue})`;

                const colorBox = document.createElement('div');
                colorBox.className = 'color-box';
                colorBox.style.backgroundColor = color;
                colorBox.setAttribute('draggable', 'true');
                colorBox.setAttribute('data-color', color);
                colorBox.addEventListener('dragstart', handleDragStart);
                spectrum.appendChild(colorBox);
            }
        }

        function handleDragStart(event) {
            event.dataTransfer.setData('text/plain', event.target.style.backgroundColor);
        }

        function allowDrop(event) {
            event.preventDefault();
        }

        function handleDrop(event) {
            event.preventDefault();
            const color = event.dataTransfer.getData('text/plain');
            const dropZone = event.target;

            // Prevent dropping into the text input area
            if (dropZone.classList.contains("input-box")) {
                return;
            }

            const colorBox = document.createElement('div');
            colorBox.className = 'color-box';
            colorBox.style.backgroundColor = color;
            dropZone.appendChild(colorBox);
        }

        function submitData() {
            alert("Thank you for your submission!");

            
        }

        window.onload = () => {
            generateSpectrum();
        };
    </script>
</body>
</html>


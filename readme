index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>CHROMA · ORIGIN</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: radial-gradient(circle at 10% 20%, #0A0F1A, #03060C);
            font-family: system-ui, -apple-system, 'Segoe UI', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }
        .chroma-app {
            max-width: 550px;
            width: 100%;
            background: rgba(12, 20, 28, 0.75);
            backdrop-filter: blur(25px);
            border-radius: 3rem;
            border: 1px solid rgba(255,255,245,0.12);
            box-shadow: 0 35px 68px rgba(0,0,0,0.5);
            overflow: hidden;
        }
        .chroma-header {
            background: linear-gradient(125deg, #1A2F3A, #0D1C24);
            padding: 1.8rem 1.8rem 1.2rem;
            text-align: center;
            border-bottom: 1px solid rgba(255,255,200,0.1);
        }
        .chroma-header h1 {
            font-size: 2rem;
            font-weight: 800;
            background: linear-gradient(135deg, #F5E7D9, #C7E0D4, #AAC7C0);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .chroma-header p {
            font-size: 0.7rem;
            color: #94A9B5;
            margin-top: 4px;
        }
        .content {
            padding: 1.8rem;
        }
        .color-canvas {
            background: #0d141c;
            border-radius: 2rem;
            padding: 1rem;
            margin-bottom: 1.8rem;
        }
        .color-display {
            height: 180px;
            border-radius: 1.5rem;
            background: #4A6A5E;
            transition: background 0.1s ease;
            cursor: pointer;
            box-shadow: 0 6px 14px rgba(0,0,0,0.3);
        }
        .hex-row {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            margin-top: 12px;
            flex-wrap: wrap;
            gap: 8px;
        }
        .hex-code {
            font-family: monospace;
            font-size: 1.3rem;
            font-weight: 600;
            background: #10161F;
            padding: 6px 16px;
            border-radius: 40px;
            color: #D9EFE5;
        }
        .dna-section {
            background: #0F1722;
            border-radius: 1.2rem;
            padding: 0.8rem 1rem;
            margin-bottom: 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            border: 1px solid #293542;
        }
        .dna-label {
            font-size: 0.7rem;
            font-weight: 600;
            color: #A9C2CF;
        }
        .dna-value {
            font-family: monospace;
            font-size: 0.85rem;
            background: #00000040;
            padding: 4px 12px;
            border-radius: 3rem;
            color: #D9D2B0;
        }
        .copy-dna {
            background: #2B404B;
            border: none;
            padding: 5px 12px;
            border-radius: 3rem;
            color: white;
            font-size: 0.65rem;
            cursor: pointer;
        }
        .time-travel {
            background: #0F1722;
            border-radius: 1.2rem;
            padding: 1rem;
            margin-bottom: 1.5rem;
        }
        .slider-label {
            display: flex;
            justify-content: space-between;
            font-size: 0.7rem;
            color: #AAC2CE;
            margin-bottom: 8px;
        }
        input.time-slider {
            width: 100%;
            accent-color: #6F9E8F;
        }
        .time-value {
            font-family: monospace;
            font-size: 0.7rem;
            background: #00000040;
            display: inline-block;
            padding: 2px 8px;
            border-radius: 3rem;
            margin-top: 8px;
        }
        .mood-mirror {
            background: linear-gradient(145deg, #10222B, #071118);
            border-radius: 1.2rem;
            padding: 1rem;
            margin-bottom: 1.5rem;
            border-left: 4px solid #C5B89A;
        }
        .mood-emotion {
            font-size: 1rem;
            font-weight: 700;
            color: #F2E5C6;
        }
        .mood-intensity {
            font-size: 0.7rem;
            color: #B4D0CF;
            margin: 6px 0;
        }
        .mood-message {
            font-size: 0.7rem;
            color: #C0D6D0;
            font-style: italic;
        }
        .action-buttons {
            display: flex;
            gap: 10px;
            margin: 5px 0;
        }
        .btn-primary {
            flex: 1;
            background: #2F5F66;
            border: none;
            padding: 12px;
            border-radius: 3rem;
            font-weight: 600;
            color: white;
            cursor: pointer;
        }
        .btn-primary:active {
            transform: scale(0.97);
        }
        .btn-secondary {
            flex: 1;
            background: #211E1A;
            border: 1px solid #4C5B62;
            padding: 12px;
            border-radius: 3rem;
            font-weight: 500;
            color: #DDD2BF;
            cursor: pointer;
        }
        .toast-msg {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: #1E2F30;
            backdrop-filter: blur(16px);
            padding: 8px 24px;
            border-radius: 60px;
            color: #E6EACE;
            font-size: 0.7rem;
            opacity: 0;
            transition: 0.2s;
            pointer-events: none;
            z-index: 200;
        }
        .credit {
            text-align: center;
            font-size: 0.55rem;
            color: #4D626B;
            margin-top: 1rem;
            border-top: 1px solid #1C2A30;
            padding-top: 1rem;
        }
    </style>
</head>
<body>
<div class="chroma-app">
    <div class="chroma-header">
        <h1>⚛️ CHROMA · ORIGIN</h1>
        <p>DNA Fingerprint · Time Travel · Mood Mirror</p>
    </div>
    <div class="content">
        <div class="color-canvas">
            <div class="color-display" id="colorDisplay" style="background: #4A6A5E;"></div>
            <div class="hex-row">
                <span class="hex-code" id="hexMain">#4A6A5E</span>
            </div>
        </div>
        <div class="dna-section">
            <span class="dna-label">🧬 CHROMA DNA FINGERPRINT</span>
            <span class="dna-value" id="dnaFull">C8H3N5O2_4A6A5E</span>
            <button class="copy-dna" id="copyDnaBtn">📋 Copy</button>
        </div>
        <div class="time-travel">
            <div class="slider-label">
                <span>🕰️ TIME TRAVEL</span>
                <span>Past ← → Future</span>
            </div>
            <input type="range" class="time-slider" id="timeSlider" min="0" max="100" value="50">
            <div class="time-value" id="timeValueDesc">⚡ Present</div>
        </div>
        <div class="mood-mirror">
            <div class="mood-emotion" id="moodEmotion">🌿 Serene · Tranquil</div>
            <div class="mood-intensity" id="moodIntensity">Intensity: 42%</div>
            <div class="mood-message" id="moodMessage">A breath between two waves</div>
        </div>
        <div class="action-buttons">
            <button class="btn-primary" id="randomColorBtn">🎲 Random Color</button>
            <button class="btn-secondary" id="resetColorBtn">🌀 Reset</button>
        </div>
        <div class="credit">🔬 CHROMA · ORIGIN — 3 Unique Features</div>
    </div>
</div>
<div id="toastMessage" class="toast-msg">✨ Copied!</div>
<script>
    let currentRealHex = "#4A6A5E";
    let currentDisplayHex = "#4A6A5E";
    let timeTravelProgress = 50;
    function hexToRgb(hex) {
        let h = hex.slice(1);
        if (h.length === 3) h = h.split('').map(c => c + c).join('');
        let intV = parseInt(h, 16);
        return { r: (intV >> 16) & 255, g: (intV >> 8) & 255, b: intV & 255 };
    }
    function rgbToHex(r, g, b) {
        return "#" + ((1 << 24) + (Math.round(r) << 16) + (Math.round(g) << 8) + Math.round(b)).toString(16).slice(1).toUpperCase();
    }
    function generateDnaFromHex(hex) {
        const rgb = hexToRgb(hex);
        let r = rgb.r, g = rgb.g, b = rgb.b;
        let prime1 = (r * 9301 + g * 49297 + b * 2339) % 100000;
        let prime2 = ((r * g) ^ (b + r) * 2333) % 8888;
        let chemPart = ['C','H','N','O','S','Fe','Mg'][(r+g+b)%7];
        let code = `${chemPart}${(r+prime1)%99}H${(g+prime2)%77}N${(b+prime1)%55}`;
        let shortId = hex.slice(1,5).toUpperCase();
        return `${code}_${shortId}`;
    }
    function getTimeTravelColor(hex, t) {
        let rgb = hexToRgb(hex);
        let r = rgb.r, g = rgb.g, b = rgb.b;
        let pastR = Math.max(0, r*0.75+30);
        let pastG = Math.max(0, g*0.7+20);
        let pastB = Math.max(0, b*0.8+25);
        let futureR = Math.min(255, r*1.2+30);
        let futureG = Math.min(255, g*0.9+25);
        let futureB = Math.min(255, b*0.7+40);
        let factor = t/100;
        return rgbToHex(pastR*(1-factor)+futureR*factor, pastG*(1-factor)+futureG*factor, pastB*(1-factor)+futureB*factor);
    }
    function analyzeMood(hex) {
        let {r,g,b} = hexToRgb(hex);
        let total = r+g+b;
        let rRatio = r/total, gRatio = g/total, bRatio = b/total;
        let intensity = Math.floor(((Math.abs(r-128)+Math.abs(g-128)+Math.abs(b-128))/(3*128))*100);
        let emotion = "", msg = "";
        if(rRatio>0.45 && gRatio<0.35) { emotion="🔥 Passionate · Bold"; msg="Energy sparks, action calls."; }
        else if(gRatio>0.45 && rRatio<0.4) { emotion="🌿 Growth · Balanced"; msg="Harmony with nature."; }
        else if(bRatio>0.45 && gRatio<0.4) { emotion="🌊 Introspective · Wise"; msg="Deep waters, quiet strength."; }
        else if(rRatio>0.35 && gRatio>0.35 && bRatio<0.3) { emotion="☀️ Optimistic · Warm"; msg="Sunlit meadows."; }
        else if(rRatio>0.3 && gRatio>0.3 && bRatio>0.3) { emotion="🤍 Serene · Tranquil"; msg="A breath between two waves."; }
        else { emotion="🎭 Curious · Experimental"; msg="Unique emotional signature."; }
        let intensityWord = intensity>65?"High":(intensity>35?"Medium":"Soft");
        return { emotion, intensity: `${intensity}% · ${intensityWord}`, message: msg };
    }
    function updateEverythingFromBaseHex(baseHex, timeValue) {
        let displayColor = getTimeTravelColor(baseHex, timeValue);
        currentDisplayHex = displayColor;
        document.getElementById('colorDisplay').style.backgroundColor = displayColor;
        document.getElementById('hexMain').innerText = displayColor;
        document.getElementById('dnaFull').innerText = generateDnaFromHex(baseHex);
        let mood = analyzeMood(displayColor);
        document.getElementById('moodEmotion').innerHTML = mood.emotion;
        document.getElementById('moodIntensity').innerHTML = `Intensity: ${mood.intensity}`;
        document.getElementById('moodMessage').innerHTML = mood.message;
    }
    let timeSlider = document.getElementById('timeSlider');
    let timeValueDesc = document.getElementById('timeValueDesc');
    function setTimeTravel(value) {
        timeTravelProgress = parseInt(value);
        if(timeTravelProgress===50) timeValueDesc.innerText="⚡ Present";
        else if(timeTravelProgress<48) timeValueDesc.innerText="🕰️ Past";
        else timeValueDesc.innerText="🚀 Future";
        updateEverythingFromBaseHex(currentRealHex, timeTravelProgress);
    }
    timeSlider.addEventListener('input', (e) => setTimeTravel(e.target.value));
    function setRandomColor() {
        let newHex = rgbToHex(50+Math.random()*180, 40+Math.random()*180, 40+Math.random()*180);
        currentRealHex = newHex;
        if(timeTravelProgress!==50) { timeSlider.value=50; timeTravelProgress=50; timeValueDesc.innerText="⚡ Present"; }
        updateEverythingFromBaseHex(currentRealHex, 50);
    }
    function resetToPresent() { timeSlider.value=50; setTimeTravel(50); }
    document.getElementById('randomColorBtn').addEventListener('click', setRandomColor);
    document.getElementById('resetColorBtn').addEventListener('click', resetToPresent);
    document.getElementById('copyDnaBtn').addEventListener('click', () => {
        navigator.clipboard.writeText(document.getElementById('dnaFull').innerText);
        let toast = document.getElementById('toastMessage');
        toast.style.opacity='1'; toast.innerText='🧬 DNA copied!';
        setTimeout(()=>toast.style.opacity='0',1500);
    });
    document.getElementById('colorDisplay').addEventListener('click', () => {
        navigator.clipboard.writeText(currentDisplayHex);
        let toast = document.getElementById('toastMessage');
        toast.style.opacity='1'; toast.innerText=`🎨 ${currentDisplayHex} copied!`;
        setTimeout(()=>toast.style.opacity='0',1500);
    });
    updateEverythingFromBaseHex("#4A6A5E", 50);
</script>
</body>
</html>

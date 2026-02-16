<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yeah Bypasser</title>
    <style>
        :root {
            --bg: #050505;
            --card: #0d0d0d;
            --accent: #00ffcc;
            --text: #ffffff;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            margin: 0;
            padding: 20px;
        }

        /* Appearing Text Animation */
        .title-wrapper {
            display: inline-block;
            overflow: hidden;
            border-right: 3px solid var(--accent);
            white-space: nowrap;
            margin: 0 auto;
            animation: typing 2s steps(20, end) forwards, blink .75s step-end infinite;
        }

        @keyframes typing { from { width: 0 } to { width: 100% } }
        @keyframes blink { from, to { border-color: transparent } 50% { border-color: var(--accent); } }

        h1 { font-size: 3rem; margin: 0; text-transform: uppercase; letter-spacing: 2px; }

        .container {
            background: var(--card);
            padding: 3rem;
            border-radius: 12px;
            border: 1px solid #1a1a1a;
            text-align: center;
            width: 100%;
            max-width: 850px;
            box-shadow: 0 20px 80px rgba(0,0,0,0.6);
        }

        .subtitle { color: #666; font-size: 0.8rem; letter-spacing: 2px; margin-top: 10px; text-transform: uppercase; }
        .discord-link {
            display: inline-block;
            margin: 10px 0 30px 0;
            color: #5865F2;
            text-decoration: none;
            font-weight: bold;
            font-size: 0.85rem;
        }
        .discord-link:hover { text-shadow: 0 0 10px rgba(88, 101, 242, 0.5); }

        .section-label { font-size: 0.65rem; color: var(--accent); text-transform: uppercase; margin-bottom: 12px; display: block; letter-spacing: 2px; font-weight: bold; }

        .controls, .sub-controls, .bait-section { display: flex; flex-wrap: wrap; gap: 10px; justify-content: center; margin-bottom: 20px; }

        .btn {
            background: #111;
            border: 1px solid #222;
            color: #555;
            padding: 10px 20px;
            cursor: pointer;
            font-size: 0.7rem;
            text-transform: uppercase;
            font-weight: bold;
            transition: 0.2s;
        }
        .btn:hover { color: #ccc; border-color: #444; }
        .btn.active { border-color: var(--accent); color: var(--accent); background: rgba(0, 255, 204, 0.05); }

        .bait-section { border-top: 1px solid #1a1a1a; padding-top: 25px; display: none; }

        .upload-label {
            display: inline-block;
            background: #fff;
            color: #000;
            padding: 16px 50px;
            font-weight: 900;
            cursor: pointer;
            margin: 20px 0;
            text-transform: uppercase;
            transition: transform 0.2s;
        }
        .upload-label:hover { transform: scale(1.02); }

        #preview-area {
            background: #000;
            padding: 30px;
            border: 1px solid #222;
            margin-top: 20px;
            display: none;
            overflow: auto;
            max-height: 450px;
        }

        #exportBtn {
            background: var(--accent);
            color: #000;
            border: none;
            padding: 20px;
            font-weight: 900;
            margin-top: 25px;
            cursor: pointer;
            width: 100%;
            text-transform: uppercase;
            letter-spacing: 1px;
            display: none;
        }

        footer { margin-top: 50px; color: #222; font-size: 0.8rem; font-weight: 800; letter-spacing: 1px; }
    </style>
</head>
<body>

<div class="container">
    <div class="title-wrapper">
        <h1>Yeah Bypasser</h1>
    </div>
    <div class="subtitle">Greatly Inspired by Top Bypassing</div>
    <a href="https://discord.gg/3cF8kra8PN" target="_blank" class="discord-link">JOIN DISCORD SERVER</a>

    <span class="section-label">Methods</span>
    <div class="controls">
        <button class="btn active" onclick="setMode('stretchWide', this)">2000x50 Wide</button>
        <button class="btn" onclick="setMode('stretchTall', this)">200x2100 Tall</button>
        <button class="btn" onclick="setMode('blackOnly', this)">512x512 Black Only</button>
        <button class="btn" onclick="setMode('whiteOnly', this)">512x512 White Only</button>
    </div>

    <div id="stretch-options" class="sub-controls">
        <button class="btn" id="convBlack" onclick="toggleConversion('black')">Convert to Only Black</button>
        <button class="btn" id="convWhite" onclick="toggleConversion('white')">Convert to Only White</button>
    </div>

    <div id="bait-area" class="bait-section">
        <span class="section-label" style="width: 100%;">Baits</span>
        <button class="btn" id="baitBtn" onclick="toggleBait()">Duck Bait</button>
    </div>

    <label for="upload" class="upload-label">Initialize Upload</label>
    <input type="file" id="upload" accept="image/*" style="display:none">
    
    <div id="preview-area">
        <canvas id="canvas"></canvas>
    </div>

    <button id="exportBtn">Export ( No bait selected )</button>
</div>

<footer>Note: Real life images wont work as well.</footer>

<script>
    const upload = document.getElementById('upload');
    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    const exportBtn = document.getElementById('exportBtn');
    const previewArea = document.getElementById('preview-area');
    const stretchOptions = document.getElementById('stretch-options');
    const baitArea = document.getElementById('bait-area');
    
    // NEW CATBOX BAIT LINK
    const baitImg = new Image();
    baitImg.crossOrigin = "anonymous";
    baitImg.src = "https://files.catbox.moe/x0zpmq.png";

    let currentMode = 'stretchWide';
    let conversionMode = 'none';
    let baitEnabled = false;
    let lastImg = null;

    function setMode(mode, btn) {
        currentMode = mode;
        document.querySelectorAll('.controls .btn').forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
        
        const isStretch = mode.includes('stretch');
        stretchOptions.style.display = isStretch ? 'flex' : 'none';
        baitArea.style.display = (mode.includes('Only') || conversionMode !== 'none') ? 'flex' : 'none';
        
        if (!isStretch) {
            conversionMode = 'none';
            document.getElementById('convBlack').classList.remove('active');
            document.getElementById('convWhite').classList.remove('active');
        }
        updateUI();
        if(lastImg) processImage(lastImg);
    }

    function toggleConversion(type) {
        if (conversionMode === type) conversionMode = 'none';
        else conversionMode = type;
        
        document.getElementById('convBlack').classList.toggle('active', conversionMode === 'black');
        document.getElementById('convWhite').classList.toggle('active', conversionMode === 'white');
        
        baitArea.style.display = (conversionMode !== 'none') ? 'flex' : 'none';
        updateUI();
        if(lastImg) processImage(lastImg);
    }

    function toggleBait() {
        baitEnabled = !baitEnabled;
        document.getElementById('baitBtn').classList.toggle('active', baitEnabled);
        updateUI();
        if(lastImg) processImage(lastImg);
    }

    function updateUI() {
        exportBtn.innerText = baitEnabled ? "Export" : "Export ( No bait selected )";
    }

    upload.addEventListener('change', (e) => {
        const file = e.target.files[0];
        if (!file) return;
        const reader = new FileReader();
        reader.onload = (event) => {
            const img = new Image();
            img.onload = () => { lastImg = img; processImage(img); };
            img.src = event.target.result;
        };
        reader.readAsDataURL(file);
    });

    function processImage(img) {
        let w = 2000, h = 50;
        if(currentMode === 'stretchTall') { w = 200; h = 2100; }
        if(currentMode === 'blackOnly' || currentMode === 'whiteOnly') { w = 512; h = 512; }

        canvas.width = w;
        canvas.height = h;
        ctx.clearRect(0, 0, w, h);

        // 1. BAIT LAYER (20% Opacity)
        if (baitEnabled) {
            ctx.globalAlpha = 0.2;
            ctx.drawImage(baitImg, 0, 0, w, h);
            ctx.globalAlpha = 1.0;
        }

        // 2. SECRET IMAGE LAYER
        const activeMethod = (currentMode.includes('Only')) ? currentMode : conversionMode;
        
        const tempCanvas = document.createElement('canvas');
        tempCanvas.width = w;
        tempCanvas.height = h;
        const tempCtx = tempCanvas.getContext('2d');
        tempCtx.drawImage(img, 0, 0, w, h);

        const imageData = tempCtx.getImageData(0, 0, w, h);
        const data = imageData.data;

        for (let i = 0; i < data.length; i += 4) {
            let r = data[i], g = data[i+1], b = data[i+2];
            const noise = (Math.random() - 0.5) * 50; // 20% Jitter

            if (activeMethod === 'blackOnly' || activeMethod === 'black') {
                // Visible on Black: Force Pixels to White
                const avg = (r + g + b) / 3;
                data[i] = 255; data[i+1] = 255; data[i+2] = 255; 
                data[i+3] = Math.max(0, Math.min(255, (avg * 0.7) + noise)); 
            } 
            else if (activeMethod === 'whiteOnly' || activeMethod === 'white') {
                // Visible on White: Force Pixels to Black
                const avg = (r + g + b) / 3;
                data[i] = 0; data[i+1] = 0; data[i+2] = 0; 
                data[i+3] = Math.max(0, Math.min(255, ((255 - avg) * 0.7) + noise));
            } 
            else {
                // Standard Stretch
                data[i] += noise; data[i+1] += noise; data[i+2] += noise;
                data[i+3] = 130;
            }
        }

        tempCtx.putImageData(imageData, 0, 0);
        ctx.drawImage(tempCanvas, 0, 0);

        previewArea.style.display = 'block';
        exportBtn.style.display = 'block';
        
        // Dynamic Preview Background
        previewArea.style.background = (activeMethod.includes('white')) ? '#ffffff' : '#000000';
    }

    exportBtn.addEventListener('click', () => {
        const link = document.createElement('a');
        link.download = 'YeahByp.png';
        link.href = canvas.toDataURL('image/png');
        link.click();
    });
</script>

</body>
</html>

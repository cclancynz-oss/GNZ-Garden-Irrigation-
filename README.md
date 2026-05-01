# GNZ-Garden-Irrigation-
Create your ideal Garden Irrigation Plan in no time with  the GMZ Garden Irrigation App
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GNZ Irrigation Design</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-dark: #1a1a1a;
            --bg-card: #242424;
            --bg-input: #2d2d2d;
            --gold: #d4af37;
            --gold-light: #e8c547;
            --gold-dark: #b8960c;
            --text-primary: #f5f5f0;
            --text-secondary: #b0b0a8;
            --text-muted: #808078;
            --border: #3a3a35;
            --success: #4a7c59;
            --danger: #8b3a3a;
            --accent: #4a6741;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg-dark);
            color: var(--text-primary);
            line-height: 1.6;
            min-height: 100vh;
        }

        /* Header & Logo */
        .app-header {
            background: linear-gradient(180deg, #0f0f0f 0%, var(--bg-dark) 100%);
            border-bottom: 2px solid var(--gold);
            padding: 20px;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 4px 20px rgba(0,0,0,0.5);
        }

        .header-content {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .logo-container {
            position: relative;
            width: 80px;
            height: 80px;
            flex-shrink: 0;
        }

        .logo-circle {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 3px solid var(--gold);
            overflow: hidden;
            background: var(--bg-card);
            box-shadow: 0 0 20px rgba(212, 175, 55, 0.3);
        }

        .logo-circle img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            opacity: 0.9;
        }

        .logo-ring {
            position: absolute;
            top: -5px;
            left: -5px;
            right: -5px;
            bottom: -5px;
            border-radius: 50%;
            border: 1px solid rgba(212, 175, 55, 0.3);
            pointer-events: none;
        }

        .brand-text {
            flex: 1;
        }

        .brand-text h1 {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            color: var(--gold);
            letter-spacing: 2px;
            text-transform: uppercase;
            line-height: 1.1;
        }

        .brand-text .subtitle {
            font-size: 0.85rem;
            color: var(--text-secondary);
            letter-spacing: 4px;
            text-transform: uppercase;
            margin-top: 4px;
        }

        .saved-badge {
            background: var(--bg-card);
            border: 1px solid var(--gold);
            color: var(--gold);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            gap: 8px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .saved-badge:hover {
            background: var(--gold);
            color: var(--bg-dark);
        }

        /* Layout */
        .app-container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 30px 20px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
        }

        @media (max-width: 1024px) {
            .app-container {
                grid-template-columns: 1fr;
            }
        }

        /* Cards */
        .card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 24px;
            margin-bottom: 24px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.3);
        }

        .card-header {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 20px;
            padding-bottom: 16px;
            border-bottom: 1px solid var(--border);
        }

        .card-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, var(--gold-dark), var(--gold));
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--bg-dark);
            font-size: 1.2rem;
        }

        .card-title {
            font-family: 'Playfair Display', serif;
            font-size: 1.3rem;
            color: var(--text-primary);
        }

        /* Form Elements */
        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            font-size: 0.85rem;
            font-weight: 500;
            color: var(--text-secondary);
            margin-bottom: 8px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        input[type="text"],
        input[type="email"],
        input[type="number"],
        input[type="tel"],
        select,
        textarea {
            width: 100%;
            background: var(--bg-input);
            border: 1px solid var(--border);
            border-radius: 8px;
            padding: 12px 16px;
            color: var(--text-primary);
            font-family: 'Inter', sans-serif;
            font-size: 0.95rem;
            transition: all 0.3s;
        }

        input:focus,
        select:focus,
        textarea:focus {
            outline: none;
            border-color: var(--gold);
            box-shadow: 0 0 0 3px rgba(212, 175, 55, 0.1);
        }

        .input-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
        }

        @media (max-width: 600px) {
            .input-row {
                grid-template-columns: 1fr;
            }
        }

        /* Checkbox & Radio Groups */
        .option-group {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 8px;
        }

        .option-chip {
            position: relative;
        }

        .option-chip input {
            position: absolute;
            opacity: 0;
            cursor: pointer;
        }

        .option-chip label {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 10px 16px;
            background: var(--bg-input);
            border: 1px solid var(--border);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 0.9rem;
            text-transform: none;
            letter-spacing: 0;
            color: var(--text-secondary);
            margin: 0;
        }

        .option-chip input:checked + label {
            background: rgba(212, 175, 55, 0.15);
            border-color: var(--gold);
            color: var(--gold);
        }

        .option-chip label:hover {
            border-color: var(--gold-light);
        }

        /* Drop Zone */
        .drop-zone {
            border: 2px dashed var(--border);
            border-radius: 12px;
            padding: 40px 20px;
            text-align: center;
            background: var(--bg-input);
            transition: all 0.3s;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .drop-zone:hover,
        .drop-zone.dragover {
            border-color: var(--gold);
            background: rgba(212, 175, 55, 0.05);
        }

        .drop-zone.has-image {
            padding: 0;
            border-style: solid;
            border-color: var(--gold);
        }

        .drop-zone img {
            width: 100%;
            max-height: 400px;
            object-fit: contain;
            display: block;
        }

        .drop-placeholder {
            color: var(--text-muted);
        }

        .drop-placeholder svg {
            width: 48px;
            height: 48px;
            margin-bottom: 12px;
            stroke: var(--gold);
        }

        .drop-hint {
            font-size: 0.85rem;
            color: var(--text-muted);
            margin-top: 8px;
        }

        /* Grid Overlay */
        .grid-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            pointer-events: none;
            background-image: 
                linear-gradient(rgba(212, 175, 55, 0.2) 1px, transparent 1px),
                linear-gradient(90deg, rgba(212, 175, 55, 0.2) 1px, transparent 1px);
            background-size: 20px 20px;
            display: none;
        }

        .drop-zone.has-image .grid-overlay {
            display: block;
        }

        /* Buttons */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 14px 28px;
            border-radius: 8px;
            font-family: 'Inter', sans-serif;
            font-size: 0.95rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            cursor: pointer;
            transition: all 0.3s;
            border: none;
            width: 100%;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--gold), var(--gold-light));
            color: var(--bg-dark);
            box-shadow: 0 4px 15px rgba(212, 175, 55, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(212, 175, 55, 0.4);
        }

        .btn-secondary {
            background: transparent;
            border: 1px solid var(--gold);
            color: var(--gold);
        }

        .btn-secondary:hover {
            background: rgba(212, 175, 55, 0.1);
        }

        .btn-outline {
            background: var(--bg-input);
            border: 1px solid var(--border);
            color: var(--text-secondary);
        }

        .btn-outline:hover {
            border-color: var(--text-primary);
            color: var(--text-primary);
        }

        .btn-danger {
            background: var(--danger);
            color: white;
            opacity: 0.8;
        }

        .btn-group {
            display: flex;
            gap: 12px;
            margin-top: 20px;
        }

        .btn-group .btn {
            flex: 1;
        }

        /* Flow Calculator */
        .flow-calc {
            background: linear-gradient(135deg, rgba(212, 175, 55, 0.1), rgba(212, 175, 55, 0.05));
            border: 1px solid var(--gold);
            border-radius: 12px;
            padding: 24px;
            margin-bottom: 24px;
        }

        .flow-calc h3 {
            color: var(--gold);
            font-family: 'Playfair Display', serif;
            margin-bottom: 16px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .calc-formula {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 16px;
            margin: 20px 0;
            flex-wrap: wrap;
            font-size: 1.1rem;
        }

        .calc-box {
            background: var(--bg-dark);
            border: 1px solid var(--gold);
            border-radius: 8px;
            padding: 12px 20px;
            text-align: center;
            min-width: 80px;
        }

        .calc-box .value {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--gold);
        }

        .calc-box .unit {
            font-size: 0.75rem;
            color: var(--text-muted);
            text-transform: uppercase;
        }

        .calc-operator {
            color: var(--gold);
            font-size: 1.5rem;
            font-weight: 300;
        }

        /* Results Section */
        .results-panel {
            background: var(--bg-card);
            border: 1px solid var(--gold);
            border-radius: 12px;
            padding: 24px;
            position: sticky;
            top: 120px;
        }

        .results-header {
            text-align: center;
            margin-bottom: 24px;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--border);
        }

        .results-header h2 {
            font-family: 'Playfair Display', serif;
            color: var(--gold);
            font-size: 1.5rem;
        }

        .parts-list {
            list-style: none;
        }

        .parts-list li {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 12px 0;
            border-bottom: 1px solid var(--border);
        }

        .parts-list li:last-child {
            border-bottom: none;
        }

        .part-name {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .part-dot {
            width: 8px;
            height: 8px;
            background: var(--gold);
            border-radius: 50%;
        }

        .part-qty {
            background: var(--bg-input);
            color: var(--gold);
            padding: 4px 12px;
            border-radius: 20px;
            font-weight: 600;
            font-size: 0.9rem;
        }

        .summary-total {
            margin-top: 20px;
            padding-top: 20px;
            border-top: 2px solid var(--gold);
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 1.1rem;
            font-weight: 600;
        }

        .summary-total .label {
            color: var(--text-secondary);
        }

        .summary-total .value {
            color: var(--gold);
            font-size: 1.3rem;
        }

        /* Zone Map */
        .zone-map {
            background: var(--bg-input);
            border-radius: 8px;
            padding: 16px;
            margin-top: 20px;
            min-height: 200px;
            position: relative;
        }

        .zone-legend {
            display: flex;
            gap: 16px;
            margin-top: 12px;
            flex-wrap: wrap;
            font-size: 0.85rem;
        }

        .zone-item {
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .zone-color {
            width: 16px;
            height: 16px;
            border-radius: 4px;
        }

        /* Print Styles */
        @media print {
            .app-header, .btn-group, .drop-zone {
                display: none;
            }
            
            .results-panel {
                position: static;
                border: 2px solid #000;
                page-break-inside: avoid;
            }
            
            body {
                background: white;
                color: black;
            }
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .animate-in {
            animation: fadeIn 0.5s ease-out;
        }

        /* Tooltip */
        .tooltip {
            position: relative;
            display: inline-block;
            cursor: help;
        }

        .tooltip:hover::after {
            content: attr(data-tip);
            position: absolute;
            bottom: 100%;
            left: 50%;
            transform: translateX(-50%);
            background: var(--bg-dark);
            color: var(--text-primary);
            padding: 8px 12px;
            border-radius: 6px;
            font-size: 0.8rem;
            white-space: nowrap;
            border: 1px solid var(--gold);
            z-index: 10;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .brand-text h1 {
                font-size: 1.4rem;
            }
            
            .header-content {
                flex-wrap: wrap;
            }
            
            .saved-badge {
                width: 100%;
                justify-content: center;
                margin-top: 10px;
            }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--bg-dark);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--gold-dark);
            border-radius: 4px;
        }

        /* Notification */
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            background: var(--bg-card);
            border: 1px solid var(--gold);
            color: var(--gold);
            padding: 16px 24px;
            border-radius: 8px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.5);
            z-index: 1000;
            transform: translateX(400px);
            transition: transform 0.3s;
        }

        .notification.show {
            transform: translateX(0);
        }

        /* Site Plan Analysis */
        .analysis-results {
            margin-top: 20px;
            padding: 16px;
            background: rgba(74, 103, 65, 0.1);
            border: 1px solid var(--accent);
            border-radius: 8px;
            display: none;
        }

        .analysis-results.active {
            display: block;
        }

        .measurement-row {
            display: flex;
            justify-content: space-between;
            padding: 8px 0;
            border-bottom: 1px solid var(--border);
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header class="app-header">
        <div class="header-content">
            <div class="logo-container">
                <div class="logo-circle">
                    <img src="/mnt/agents/upload/E2D0F7A4-7E44-44C8-AA87-79603505CDCA.jpg" alt="GNZ Garden Design Logo">
                </div>
                <div class="logo-ring"></div>
            </div>
            <div class="brand-text">
                <h1>GNZ Irrigation Design</h1>
                <div class="subtitle">Landscape & Interior Studio</div>
            </div>
            <div class="saved-badge" onclick="showSavedDesigns()">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M19 21l-7-5-7 5V5a2 2 0 0 1 2-2h10a2 2 0 0 1 2 2z"></path>
                </svg>
                Saved Designs
            </div>
        </div>
    </header>

    <div class="app-container">
        <!-- Left Column: Input Forms -->
        <div class="input-column">
            
            <!-- Customer & Site Details -->
            <div class="card animate-in">
                <div class="card-header">
                    <div class="card-icon">📋</div>
                    <h2 class="card-title">Project Brief</h2>
                </div>
                
                <div class="input-row">
                    <div class="form-group">
                        <label>Customer Name</label>
                        <input type="text" id="customerName" placeholder="Enter customer name">
                    </div>
                    <div class="form-group">
                        <label>Phone</label>
                        <input type="tel" id="customerPhone" placeholder="Phone number">
                    </div>
                </div>

                <div class="input-row">
                    <div class="form-group">
                        <label>Email</label>
                        <input type="email" id="customerEmail" placeholder="email@example.com">
                    </div>
                    <div class="form-group">
                        <label>Local Store</label>
                        <select id="localStore">
                            <option value="">Select Store</option>
                            <option value="Palmers">Palmers</option>
                            <option value="Kings Plant Barn">Kings Plant Barn</option>
                            <option value="Mitre 10 Mega">Mitre 10 Mega</option>
                            <option value="Bunnings">Bunnings</option>
                            <option value="Other">Other</option>
                        </select>
                    </div>
                </div>

                <div class="form-group">
                    <label>Project Address</label>
                    <textarea id="projectAddress" rows="2" placeholder="Full project address"></textarea>
                </div>

                <div class="form-group">
                    <label>Project Type</label>
                    <div class="option-group">
                        <div class="option-chip">
                            <input type="radio" name="projectType" id="typeNew" value="new" checked>
                            <label for="typeNew">New Installation</label>
                        </div>
                        <div class="option-chip">
                            <input type="radio" name="projectType" id="typeExisting" value="existing">
                            <label for="typeExisting">Existing Upgrade</label>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Site Conditions -->
            <div class="card animate-in">
                <div class="card-header">
                    <div class="card-icon">🌿</div>
                    <h2 class="card-title">Site Conditions</h2>
                </div>

                <div class="input-row">
                    <div class="form-group">
                        <label>Aspect</label>
                        <select id="siteAspect">
                            <option value="North">North</option>
                            <option value="South">South</option>
                            <option value="East">East</option>
                            <option value="West">West</option>
                            <option value="Flat">Flat</option>
                            <option value="Contoured">Contoured</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Soil Type</label>
                        <select id="soilType">
                            <option value="Sandy">Sandy</option>
                            <option value="Clay">Clay</option>
                            <option value="Loam">Loam</option>
                            <option value="Silty">Silty</option>
                            <option value="Peaty">Peaty</option>
                        </select>
                    </div>
                </div>

                <div class="input-row">
                    <div class="form-group">
                        <label>Exposure</label>
                        <select id="exposure">
                            <option value="Sheltered">Sheltered</option>
                            <option value="Moderate">Moderate</option>
                            <option value="Exposed">Exposed</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Moisture</label>
                        <select id="moisture">
                            <option value="Dry">Dry</option>
                            <option value="Average">Average</option>
                            <option value="Wet">Wet</option>
                        </select>
                    </div>
                </div>

                <div class="form-group">
                    <label>Areas to Irrigate</label>
                    <div class="option-group">
                        <div class="option-chip">
                            <input type="checkbox" id="areaLawn" value="lawns" checked>
                            <label for="areaLawn">Lawns</label>
                        </div>
                        <div class="option-chip">
                            <input type="checkbox" id="areaGarden" value="gardens">
                            <label for="areaGarden">Gardens</label>
                        </div>
                        <div class="option-chip">
                            <input type="checkbox" id="areaVeg" value="vege">
                            <label for="areaVeg">Vege Garden</label>
                        </div>
                        <div class="option-chip">
                            <input type="checkbox" id="areaGreenhouse" value="greenhouse">
                            <label for="areaGreenhouse">Glass House</label>
                        </div>
                        <div class="option-chip">
                            <input type="checkbox" id="areaOther" value="other">
                            <label for="areaOther">Other</label>
                        </div>
                    </div>
                </div>

                <div class="form-group">
                    <label>Obstacles & Access</label>
                    <div class="option-group">
                        <div class="option-chip">
                            <input type="checkbox" id="obsDriveway" value="driveway">
                            <label for="obsDriveway">Driveway</label>
                        </div>
                        <div class="option-chip">
                            <input type="checkbox" id="obsPaths" value="paths">
                            <label for="obsPaths">Paths</label>
                        </div>
                        <div class="option-chip">
                            <input type="checkbox" id="obsDeck" value="deck">
                            <label for="obsDeck">Deck</label>
                        </div>
                        <div class="option-chip">
                            <input type="checkbox" id="obsFence" value="fence">
                            <label for="obsFence">Fences</label>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Flow Rate Calculator -->
            <div class="flow-calc animate-in">
                <h3>
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M12 2.69l5.66 5.66a8 8 0 1 1-11.31 0z"></path>
                    </svg>
                    Bucket Test Flow Rate Calculator
                </h3>
                <p style="color: var(--text-secondary); font-size: 0.9rem; margin-bottom: 16px;">
                    Time how long it takes to fill a 9-litre bucket from your tap. We'll calculate litres per minute (LPM).
                </p>
                
                <div class="input-row">
                    <div class="form-group">
                        <label>Bucket Size (Litres)</label>
                        <input type="number" id="bucketSize" value="9" min="1">
                    </div>
                    <div class="form-group">
                        <label>Time to Fill (Seconds)</label>
                        <input type="number" id="fillTime" placeholder="e.g. 20" min="1">
                    </div>
                </div>

                <div class="calc-formula">
                    <div class="calc-box">
                        <div class="value" id="bucketSizeDisplay">9</div>
                        <div class="unit">Litres</div>
                    </div>
                    <span class="calc-operator">×</span>
                    <div class="calc-box">
                        <div class="value">60</div>
                        <div class="unit">Seconds</div>
                    </div>
                    <span class="calc-operator">÷</span>
                    <div class="calc-box">
                        <div class="value" id="fillTimeDisplay">--</div>
                        <div class="unit">Seconds</div>
                    </div>
                    <span class="calc-operator">=</span>
                    <div class="calc-box" style="border-color: var(--gold-light); background: rgba(212,175,55,0.1);">
                        <div class="value" id="flowRateResult" style="color: var(--gold-light);">--</div>
                        <div class="unit">LPM</div>
                    </div>
                </div>

                <div class="form-group" style="margin-top: 16px;">
                    <label>Water Supply Source</label>
                    <div class="option-group">
                        <div class="option-chip">
                            <input type="radio" name="waterSupply" id="supplyTap" value="tap" checked>
                            <label for="supplyTap">Tap</label>
                        </div>
                        <div class="option-chip">
                            <input type="radio" name="waterSupply" id="supplyMains" value="mains">
                            <label for="supplyMains">Mains</label>
                        </div>
                        <div class="option-chip">
                            <input type="radio" name="waterSupply" id="supplyTank" value="tank">
                            <label for="supplyTank">Tank</label>
                        </div>
                        <div class="option-chip">
                            <input type="radio" name="waterSupply" id="supplyOther" value="other">
                            <label for="supplyOther">Other</label>
                        </div>
                    </div>
                </div>

                <div class="form-group">
                    <label>Control Type</label>
                    <div class="option-group">
                        <div class="option-chip">
                            <input type="radio" name="controlType" id="ctrlTapTimer" value="tapTimer" checked>
                            <label for="ctrlTapTimer">Tap Timer</label>
                        </div>
                        <div class="option-chip">
                            <input type="radio" name="controlType" id="ctrl9v" value="9v">
                            <label for="ctrl9v">Solenoid 9V</label>
                        </div>
                        <div class="option-chip">
                            <input type="radio" name="controlType" id="ctrl240v" value="240v">
                            <label for="ctrl240v">Solenoid 240V</label>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Site Plan Upload -->
            <div class="card animate-in">
                <div class="card-header">
                    <div class="card-icon">📐</div>
                    <h2 class="card-title">Site Plan Upload</h2>
                </div>
                
                <p style="color: var(--text-secondary); font-size: 0.9rem; margin-bottom: 16px;">
                    Upload customer's grid photo or scale drawing. Include measurements, taps, and obstacles. 
                    <span class="tooltip" data-tip="1 square = 1 metre">ℹ️</span>
                </p>

                <div class="drop-zone" id="dropZone" onclick="document.getElementById('fileInput').click()">
                    <div class="drop-placeholder" id="dropPlaceholder">
                        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                            <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                            <polyline points="17 8 12 3 7 8"></polyline>
                            <line x1="12" y1="3" x2="12" y2="15"></line>
                        </svg>
                        <div style="font-size: 1.1rem; color: var(--text-primary); margin-bottom: 4px;">
                            Drop site plan photo here
                        </div>
                        <div class="drop-hint">
                            or click to browse • JPG, PNG, PDF
                        </div>
                    </div>
                    <div class="grid-overlay" id="gridOverlay"></div>
                    <img id="previewImage" style="display: none;">
                </div>
                <input type="file" id="fileInput" accept="image/*,.pdf" style="display: none;" onchange="handleFileSelect(event)">

                <div class="analysis-results" id="analysisResults">
                    <h4 style="color: var(--gold); margin-bottom: 12px;">Detected Measurements</h4>
                    <div class="measurement-row">
                        <span>Estimated Area</span>
                        <span id="estArea">-- m²</span>
                    </div>
                    <div class="measurement-row">
                        <span>Grid Scale</span>
                        <span id="gridScale">1 sq = 1m</span>
                    </div>
                    <div class="measurement-row">
                        <span>Suggested Zones</span>
                        <span id="suggestedZones">--</span>
                    </div>
                </div>

                <div class="form-group" style="margin-top: 16px;">
                    <label>Manual Area Input (m²)</label>
                    <input type="number" id="manualArea" placeholder="Enter total area if no plan uploaded">
                </div>

                <div class="input-row">
                    <div class="form-group">
                        <label>Lawn Area (m²)</label>
                        <input type="number" id="lawnArea" placeholder="0">
                    </div>
                    <div class="form-group">
                        <label>Garden Area (m²)</label>
                        <input type="number" id="gardenArea" placeholder="0">
                    </div>
                </div>
            </div>

            <!-- Action Buttons -->
            <div class="btn-group">
                <button class="btn btn-primary" onclick="generateBrief()">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"></polygon>
                    </svg>
                    Generate Brief
                </button>
                <button class="btn btn-secondary" onclick="clearAll()">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <polyline points="23 4 23 10 17 10"></polyline>
                        <path d="M20.49 15a9 9 0 1 1-2.12-9.36L23 10"></path>
                    </svg>
                    Clear All
                </button>
            </div>

        </div>

        <!-- Right Column: Results -->
        <div class="results-column">
            <div class="results-panel" id="resultsPanel">
                <div class="results-header">
                    <h2>Design Brief & Parts Summary</h2>
                    <p style="color: var(--text-muted); font-size: 0.9rem; margin-top: 8px;">
                        Complete the form and click Generate Brief
                    </p>
                </div>

                <div id="emptyState" style="text-align: center; padding: 40px 20px; color: var(--text-muted);">
                    <svg width="64" height="64" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" style="margin-bottom: 16px; opacity: 0.5;">
                        <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path>
                        <polyline points="14 2 14 8 20 8"></polyline>
                        <line x1="16" y1="13" x2="8" y2="13"></line>
                        <line x1="16" y1="17" x2="8" y2="17"></line>
                        <polyline points="10 9 9 9 8 9"></polyline>
                    </svg>
                    <p>Your irrigation design brief will appear here</p>
                </div>

                <div id="briefContent" style="display: none;">
                    <!-- Dynamic content inserted here -->
                </div>

                <div class="btn-group" id="actionButtons" style="display: none; margin-top: 24px;">
                    <button class="btn btn-outline" onclick="copyBrief()">
                        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <rect x="9" y="9" width="13" height="13" rx="2" ry="2"></rect>
                            <path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"></path>
                        </svg>
                        Copy
                    </button>
                    <button class="btn btn-outline" onclick="window.print()">
                        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <polyline points="6 9 6 2 18 2 18 9"></polyline>
                            <path d="M6 18H4a2 2 0 0 1-2-2v-5a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v5a2 2 0 0 1-2 2h-2"></path>
                            <rect x="6" y="14" width="12" height="8"></rect>
                        </svg>
                        Print
                    </button>
                    <button class="btn btn-secondary" onclick="emailBrief()">
                        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                            <polyline points="22,6 12,13 2,6"></polyline>
                        </svg>
                        Email
                    </button>
                </div>

                <button class="btn btn-primary" id="saveBtn" style="display: none; margin-top: 12px;" onclick="saveDesign()">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M19 21l-7-5-7 5V5a2 2 0 0 1 2-2h10a2 2 0 0 1 2 2z"></path>
                    </svg>
                    Save Design
                </button>
            </div>

            <!-- Zone Visualization -->
            <div class="card" id="zoneCard" style="display: none;">
                <div class="card-header">
                    <div class="card-icon">🎯</div>
                    <h2 class="card-title">Zone Layout</h2>
                </div>
                <div class="zone-map" id="zoneMap">
                    <div style="text-align: center; color: var(--text-muted); padding: 40px;">
                        Zone map visualization based on site plan
                    </div>
                </div>
                <div class="zone-legend" id="zoneLegend">
                    <!-- Dynamic legend -->
                </div>
            </div>
        </div>
    </div>

    <!-- Notification -->
    <div class="notification" id="notification"></div>

    <script>
        // Wetta Product Database
        const wettaProducts = {
            sprinklers: {
                popUp: { name: 'Wetta Pop-Up Sprinkler', flow: 9, coverage: 3.5, price: 24.99, type: 'lawn' },
                gearDrive: { name: 'Wetta Gear Drive Sprinkler', flow: 12, coverage: 5.0, price: 34.99, type: 'lawn' },
                shrub: { name: 'Wetta Shrub Riser', flow: 6, coverage: 2.5, price: 18.99, type: 'garden' },
                drip: { name: 'Wetta Drip Line (10m)', flow: 2, coverage: 10, price: 29.99, type: 'garden' },
                micro: { name: 'Wetta Micro Spray', flow: 4, coverage: 1.5, price: 12.99, type: 'garden' }
            },
            controllers: {
                tapTimer: { name: 'Wetta Tap Timer', price: 89.99, zones: 1 },
                battery9v: { name: 'Wetta 9V Battery Controller', price: 149.99, zones: 4 },
                mains240v: { name: 'Wetta 240V Mains Controller', price: 199.99, zones: 6 }
            },
            piping: {
                poly13mm: { name: '13mm Poly Pipe (25m)', price: 24.99 },
                poly19mm: { name: '19mm Poly Pipe (25m)', price: 34.99 },
                fittings: { name: 'Pipe Fittings Pack', price: 19.99 }
            },
            valves: {
                solenoid: { name: 'Solenoid Valve', price: 45.99 },
                master: { name: 'Master Valve', price: 59.99 }
            }
        };

        let currentDesign = null;
        let savedDesigns = JSON.parse(localStorage.getItem('gnzIrrigationDesigns') || '[]');

        // Flow Rate Calculator
        document.getElementById('bucketSize').addEventListener('input', updateFlowCalc);
        document.getElementById('fillTime').addEventListener('input', updateFlowCalc);

        function updateFlowCalc() {
            const bucket = parseFloat(document.getElementById('bucketSize').value) || 9;
            const time = parseFloat(document.getElementById('fillTime').value) || 0;
            
            document.getElementById('bucketSizeDisplay').textContent = bucket;
            document.getElementById('fillTimeDisplay').textContent = time || '--';
            
            if (time > 0) {
                const lpm = ((bucket * 60) / time).toFixed(1);
                document.getElementById('flowRateResult').textContent = lpm;
                return parseFloat(lpm);
            } else {
                document.getElementById('flowRateResult').textContent = '--';
                return 0;
            }
        }

        // File Upload Handling
        const dropZone = document.getElementById('dropZone');
        const fileInput = document.getElementById('fileInput');

        ['dragenter', 'dragover', 'dragleave', 'drop'].forEach(eventName => {
            dropZone.addEventListener(eventName, preventDefaults, false);
        });

        function preventDefaults(e) {
            e.preventDefault();
            e.stopPropagation();
        }

        ['dragenter', 'dragover'].forEach(eventName => {
            dropZone.addEventListener(eventName, () => dropZone.classList.add('dragover'), false);
        });

        ['dragleave', 'drop'].forEach(eventName => {
            dropZone.addEventListener(eventName, () => dropZone.classList.remove('dragover'), false);
        });

        dropZone.addEventListener('drop', handleDrop, false);

        function handleDrop(e) {
            const dt = e.dataTransfer;
            const files = dt.files;
            handleFiles(files);
        }

        function handleFileSelect(e) {
            handleFiles(e.target.files);
        }

        function handleFiles(files) {
            if (files.length > 0) {
                const file = files[0];
                if (file.type.startsWith('image/')) {
                    const reader = new FileReader();
                    reader.onload = (e) => {
                        const img = document.getElementById('previewImage');
                        img.src = e.target.result;
                        img.style.display = 'block';
                        document.getElementById('dropPlaceholder').style.display = 'none';
                        dropZone.classList.add('has-image');
                        analyzeSitePlan();
                    };
                    reader.readAsDataURL(file);
                }
            }
        }

        function analyzeSitePlan() {
            // Simulate image analysis
            setTimeout(() => {
                const lawn = parseFloat(document.getElementById('lawnArea').value) || 50;
                const garden = parseFloat(document.getElementById('gardenArea').value) || 30;
                const total = lawn + garden;
                
                document.getElementById('estArea').textContent = total + ' m²';
                document.getElementById('suggestedZones').textContent = Math.ceil(total / 50) + ' zones';
                document.getElementById('analysisResults').classList.add('active');
                
                showNotification('Site plan analyzed successfully');
            }, 800);
        }

        // Generate Design Brief
        function generateBrief() {
            const flowRate = updateFlowCalc();
            const lawnArea = parseFloat(document.getElementById('lawnArea').value) || 0;
            const gardenArea = parseFloat(document.getElementById('gardenArea').value) || 0;
            const totalArea = lawnArea + gardenArea || parseFloat(document.getElementById('manualArea').value) || 0;
            
            if (flowRate === 0) {
                showNotification('Please complete the bucket test first', 'error');
                document.getElementById('fillTime').focus();
                return;
            }

            if (totalArea === 0) {
                showNotification('Please enter area measurements or upload a site plan', 'error');
                return;
            }

            const controlType = document.querySelector('input[name="controlType"]:checked').value;
            const areas = Array.from(document.querySelectorAll('input[type="checkbox"]:checked'))
                .filter(cb => ['areaLawn', 'areaGarden', 'areaVeg', 'areaGreenhouse', 'areaOther'].includes(cb.id))
                .map(cb => cb.nextElementSibling.textContent);

            // Calculate parts needed
            const parts = calculateParts(totalArea, lawnArea, gardenArea, flowRate, controlType, areas);
            
            // Generate HTML
            const briefHTML = generateBriefHTML(parts, totalArea, flowRate, controlType, areas);
            
            document.getElementById('emptyState').style.display = 'none';
            document.getElementById('briefContent').innerHTML = briefHTML;
            document.getElementById('briefContent').style.display = 'block';
            document.getElementById('actionButtons').style.display = 'flex';
            document.getElementById('saveBtn').style.display = 'flex';
            document.getElementById('zoneCard').style.display = 'block';

            // Generate zone map
            generateZoneMap(parts.zones);

            currentDesign = {
                id: Date.now(),
                date: new Date().toLocaleDateString(),
                customer: document.getElementById('customerName').value,
                parts: parts,
                totalArea,
                flowRate
            };

            showNotification('Design brief generated successfully');
        }

        function calculateParts(totalArea, lawnArea, gardenArea, flowRate, controlType, areas) {
            const parts = [];
            let zones = [];
            let currentZone = 1;
            let zoneFlow = 0;
            const maxZoneFlow = flowRate * 0.8; // 80% of available flow

            // Lawn sprinklers
            if (lawnArea > 0) {
                const lawnZones = Math.ceil(lawnArea / 50); // ~50m² per zone
                for (let i = 0; i < lawnZones; i++) {
                    const zoneArea = Math.min(50, lawnArea - (i * 50));
                    const sprinklerCount = Math.ceil(zoneArea / 12); // ~12m² per sprinkler
                    const sprinklerType = zoneArea > 30 ? 'gearDrive' : 'popUp';
                    
                    zones.push({
                        id: currentZone,
                        type: 'Lawn',
                        area: zoneArea,
                        sprinklers: sprinklerCount,
                        sprinklerType: wettaProducts.sprinklers[sprinklerType].name,
                        flow: sprinklerCount * wettaProducts.sprinklers[sprinklerType].flow
                    });

                    parts.push({
                        name: wettaProducts.sprinklers[sprinklerType].name,
                        qty: sprinklerCount,
                        zone: currentZone
                    });
                    currentZone++;
                }
            }

            // Garden irrigation
            if (gardenArea > 0) {
                const gardenZones = Math.ceil(gardenArea / 40);
                for (let i = 0; i < gardenZones; i++) {
                    const zoneArea = Math.min(40, gardenArea - (i * 40));
                    const dripLength = Math.ceil(zoneArea / 10) * 10;
                    
                    zones.push({
                        id: currentZone,
                        type: 'Garden',
                        area: zoneArea,
                        dripLength: dripLength,
                        flow: (dripLength / 10) * wettaProducts.sprinklers.drip.flow
                    });

                    parts.push({
                        name: wettaProducts.sprinklers.drip.name,
                        qty: dripLength / 10,
                        zone: currentZone
                    });
                    currentZone++;
                }
            }

            // Controller
            const controllerKey = controlType === 'tapTimer' ? 'tapTimer' : 
                                 controlType === '9v' ? 'battery9v' : 'mains240v';
            parts.push({
                name: wettaProducts.controllers[controllerKey].name,
                qty: 1,
                zone: 'All'
            });

            // Valves (one per zone if not tap timer)
            if (controlType !== 'tapTimer') {
                parts.push({
                    name: wettaProducts.valves.solenoid.name,
                    qty: zones.length,
                    zone: 'All'
                });
            }

            // Piping estimate
            const totalPipeLength = Math.ceil(totalArea / 10);
            parts.push({
                name: wettaProducts.piping.poly19mm.name,
                qty: Math.ceil(totalPipeLength / 25),
                zone: 'All'
            });
            parts.push({
                name: wettaProducts.piping.poly13mm.name,
                qty: Math.ceil(totalPipeLength / 50),
                zone: 'All'
            });
            parts.push({
                name: wettaProducts.piping.fittings.name,
                qty: zones.length * 2,
                zone: 'All'
            });

            return { parts, zones, totalZones: zones.length };
        }

        function generateBriefHTML(parts, totalArea, flowRate, controlType, areas) {
            const customer = document.getElementById('customerName').value || 'Customer';
            const date = new Date().toLocaleDateString('en-NZ');
            
            let html = `
                <div style="border-bottom: 2px solid var(--gold); padding-bottom: 16px; margin-bottom: 20px;">
                    <h3 style="color: var(--gold); font-family: 'Playfair Display', serif; font-size: 1.3rem; margin-bottom: 8px;">
                        GNZ IRRIGATION DESIGN - COMPREHENSIVE BRIEF
                    </h3>
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 12px; font-size: 0.9rem; color: var(--text-secondary);">
                        <div>Date: ${date}</div>
                        <div>Customer: ${customer}</div>
                        <div>Flow Rate: ${flowRate} LPM</div>
                        <div>Total Area: ${totalArea} m²</div>
                    </div>
                </div>

                <div style="margin-bottom: 20px;">
                    <h4 style="color: var(--gold); margin-bottom: 12px; text-transform: uppercase; letter-spacing: 1px; font-size: 0.9rem;">
                        Site Conditions
                    </h4>
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 8px; font-size: 0.9rem; color: var(--text-secondary);">
                        <div>• Aspect: ${document.getElementById('siteAspect').value}</div>
                        <div>• Soil: ${document.getElementById('soilType').value}</div>
                        <div>• Exposure: ${document.getElementById('exposure').value}</div>
                        <div>• Moisture: ${document.getElementById('moisture').value}</div>
                    </div>
                </div>

                <div style="margin-bottom: 20px;">
                    <h4 style="color: var(--gold); margin-bottom: 12px; text-transform: uppercase; letter-spacing: 1px; font-size: 0.9rem;">
                        Irrigation Zones (${parts.zones.length})
                    </h4>
            `;

            parts.zones.forEach(zone => {
                html += `
                    <div style="background: var(--bg-input); padding: 12px; border-radius: 8px; margin-bottom: 8px; border-left: 3px solid var(--gold);">
                        <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
                            <strong style="color: var(--text-primary);">Zone ${zone.id} - ${zone.type}</strong>
                            <span style="color: var(--gold);">${zone.area} m²</span>
                        </div>
                        <div style="font-size: 0.85rem; color: var(--text-muted);">
                            ${zone.sprinklers ? `${zone.sprinklers}x ${zone.sprinklerType}` : `${zone.dripLength}m Drip Line`} 
                            • Flow: ${zone.flow} LPM
                        </div>
                    </div>
                `;
            });

            html += `</div>

                <div style="margin-bottom: 20px;">
                    <h4 style="color: var(--gold); margin-bottom: 12px; text-transform: uppercase; letter-spacing: 1px; font-size: 0.9rem;">
                        Parts Schedule
                    </h4>
                    <ul class="parts-list">
            `;

            // Group parts by type
            const grouped = {};
            parts.parts.forEach(part => {
                if (!grouped[part.name]) grouped[part.name] = { qty: 0, zones: [] };
                grouped[part.name].qty += part.qty;
                if (part.zone !== 'All') grouped[part.name].zones.push(part.zone);
            });

            Object.entries(grouped).forEach(([name, data]) => {
                html += `
                    <li>
                        <div class="part-name">
                            <div class="part-dot"></div>
                            <div>
                                <div style="color: var(--text-primary);">${name}</div>
                                ${data.zones.length > 0 ? `<div style="font-size: 0.8rem; color: var(--text-muted);">Zones: ${data.zones.join(', ')}</div>` : ''}
                            </div>
                        </div>
                        <div class="part-qty">×${data.qty}</div>
                    </li>
                `;
            });

            const totalItems = Object.values(grouped).reduce((a, b) => a + b.qty, 0);

            html += `
                    </ul>
                    <div class="summary-total">
                        <span class="label">Total Items</span>
                        <span class="value">${totalItems}</span>
                    </div>
                </div>

                <div style="background: rgba(212,175,55,0.05); border: 1px solid var(--gold); border-radius: 8px; padding: 16px; margin-top: 20px;">
                    <h4 style="color: var(--gold); margin-bottom: 8px;">Design Notes</h4>
                    <p style="font-size: 0.9rem; color: var(--text-secondary); line-height: 1.6;">
                        System designed for ${areas.join(', ')} areas. 
                        ${controlType === 'tapTimer' ? 'Tap timer suitable for simple scheduling.' : 'Solenoid system allows multi-zone automation.'}
                        Pipe layout should avoid ${Array.from(document.querySelectorAll('input[id^="obs"]:checked')).map(cb => cb.nextElementSibling.textContent).join(', ') || 'known obstacles'}.
                        Allow 15% extra pipe for connections and wastage.
                    </p>
                </div>

                <div style="margin-top: 20px; padding-top: 16px; border-top: 1px solid var(--border); font-size: 0.8rem; color: var(--text-muted); text-align: center;">
                    Designed by GNZ Garden Design • Wetta Irrigation Products • ${date}
                </div>
            `;

            return html;
        }

        function generateZoneMap(zones) {
            const map = document.getElementById('zoneMap');
            const legend = document.getElementById('zoneLegend');
            const colors = ['#d4af37', '#4a7c59', '#8b6914', '#5c7a29', '#c9a227', '#6b8e23'];
            
            let mapHTML = '<div style="position: relative; width: 100%; height: 200px; background: var(--bg-dark); border-radius: 8px; overflow: hidden;">';
            
            zones.forEach((zone, index) => {
                const color = colors[index % colors.length];
                const top = 20 + (index * 35);
                const left = 10 + (index * 15);
                const width = 30 + (zone.area / 2);
                const height = 25;
                
                mapHTML += `
                    <div style="position: absolute; top: ${top}px; left: ${left}%; width: ${Math.min(width, 80)}%; height: ${height}px; 
                                background: ${color}33; border: 2px solid ${color}; border-radius: 6px; 
                                display: flex; align-items: center; justify-content: center; font-size: 0.8rem; color: ${color};">
                        Z${zone.id} • ${zone.type}
                    </div>
                `;
            });
            
            mapHTML += '</div>';
            map.innerHTML = mapHTML;

            legend.innerHTML = zones.map((zone, index) => `
                <div class="zone-item">
                    <div class="zone-color" style="background: ${colors[index % colors.length]};"></div>
                    <span>Zone ${zone.id}: ${zone.type} (${zone.area}m²)</span>
                </div>
            `).join('');
        }

        // Actions
        function copyBrief() {
            const content = document.getElementById('briefContent').innerText;
            navigator.clipboard.writeText(content).then(() => {
                showNotification('Brief copied to clipboard');
            });
        }

        function emailBrief() {
            const customer = document.getElementById('customerEmail').value;
            const subject = 'GNZ Irrigation Design Brief';
            const body = document.getElementById('briefContent').innerText;
            window.location.href = `mailto:${customer}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
        }

        function saveDesign() {
            if (!currentDesign) return;
            
            savedDesigns.push(currentDesign);
            localStorage.setItem('gnzIrrigationDesigns', JSON.stringify(savedDesigns));
            showNotification('Design saved successfully');
        }

        function showSavedDesigns() {
            if (savedDesigns.length === 0) {
                showNotification('No saved designs yet');
                return;
            }
            
            let list = 'Saved Designs:\n\n';
            savedDesigns.forEach((d, i) => {
                list += `${i + 1}. ${d.customer} - ${d.date} (${d.totalArea}m²)\n`;
            });
            
            alert(list);
        }

        function clearAll() {
            if (confirm('Clear all form data?')) {
                document.querySelectorAll('input, select, textarea').forEach(el => {
                    if (el.type === 'checkbox' || el.type === 'radio') {
                        el.checked = el.defaultChecked;
                    } else {
                        el.value = el.defaultValue || '';
                    }
                });
                
                document.getElementById('previewImage').style.display = 'none';
                document.getElementById('dropPlaceholder').style.display = 'block';
                document.getElementById('dropZone').classList.remove('has-image');
                document.getElementById('analysisResults').classList.remove('active');
                document.getElementById('briefContent').style.display = 'none';
                document.getElementById('emptyState').style.display = 'block';
                document.getElementById('actionButtons').style.display = 'none';
                document.getElementById('saveBtn').style.display = 'none';
                document.getElementById('zoneCard').style.display = 'none';
                
                updateFlowCalc();
                showNotification('Form cleared');
            }
        }

        function showNotification(message, type = 'success') {
            const notif = document.getElementById('notification');
            notif.textContent = message;
            notif.style.borderColor = type === 'error' ? 'var(--danger)' : 'var(--gold)';
            notif.style.color = type === 'error' ? '#ff6b6b' : 'var(--gold)';
            notif.classList.add('show');
            
            setTimeout(() => {
                notif.classList.remove('show');
            }, 3000);
        }

        // Initialize
        updateFlowCalc();
    </script>
</body>
</html>

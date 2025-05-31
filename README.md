<html lang="ar">
<head>
    <meta charset="UTF-8">
    <title>رقم واحد لتأجير المعدات</title>
    <style>
        body { font-family: Tahoma, Arial; margin: 0; background: #f7f7f7; direction: rtl; }
        .header { background: #0d47a1; color: #fff; text-align: center; padding: 30px 0; font-size: 2rem; letter-spacing: 2px;}
        .container { max-width: 480px; margin: 30px auto; padding: 0 10px;}
        .card {
            background: #fff; margin: 15px 0; padding: 20px 0; text-align: center;
            border-radius: 10px; font-size: 1.3rem; box-shadow: 0 2px 10px #ddd;
            cursor: pointer; transition: box-shadow 0.2s;
        }
        .card:hover { box-shadow: 0 4px 20px #bbb;}
        .equip-card {
            background: #fff; margin: 15px 0; padding: 15px 10px 13px 10px; border-radius: 10px;
            box-shadow: 0 2px 10px #eee; font-size: 1.1rem;
            display: flex; flex-direction: column; gap: 10px;
            transition: background 0.2s;
        }
        .equip-name {
            font-size: 3.2rem;
            font-weight: bold;
            color: #00ff00;
            background: #181818;
            border-radius: 8px;
            padding: 18px 0 14px 0;
            text-shadow:
              0 0 7px #00ff00,
              0 0 20px #00ff00,
              0 0 40px #00ff00;
            text-align: center;
            margin-bottom: 5px;
            letter-spacing: 1.5px;
            border: 1px solid #222;
            margin-top: 0;
        }
        .store-banner-red {
            background: #b30a0a;
            border: 2.5px solid #b40000;
            box-shadow: 0 0 7px #b40000, 0 0 20px #b40000;
            border-radius: 8px;
            margin: 10px 0 5px 0;
            padding: 18px 0 10px 0;
            text-align: center;
        }
        .store-banner-red .store-hacker {
            font-size: 3.2rem;
            font-weight: bold;
            color: #00ff00;
            text-shadow:
              0 0 7px #00ff00,
              0 0 20px #00ff00,
              0 0 40px #00ff00;
            letter-spacing: 1.5px;
            display: block;
            margin-bottom: 8px;
            font-family: inherit;
        }
        .store-banner-red .banner-info {
            font-size: 1.1rem;
            margin: 0 0 3px 0;
            color: #fff;
            text-shadow: 0 0 7px #fff, 0 0 2px #ffcccc;
        }
        .input-row { display: flex; gap: 8px; margin: 0 0 3px 0;}
        .input-row label { min-width: 80px; font-size: 0.96rem;}
        .input-row input, .input-row textarea {
            flex: 1; font-size: 1rem; padding: 4px 7px; border-radius: 4px; border: 1px solid #ccc;
        }
        .input-row textarea { resize: vertical;}
        .oil-alert {
            display: inline-block; padding: 6px 14px; border-radius: 7px;
            font-size: 1rem; margin: 4px 0 0 0;
        }
        .oil-normal { background: #e3f7e3; color: #205720; border: 1px solid #b6eab6;}
        .oil-late { background: #ffe1e1; color: #b40000; border: 1px solid #ff6a6a;}
        .btn-group { display: flex; gap: 4px; flex-wrap: wrap; justify-content: flex-start; margin-top: 7px;}
        .my-btn, .store-btn {
            background: #1976d2; color: #fff; border: none; border-radius: 5px;
            padding: 5px 12px; font-size: 0.97rem; cursor: pointer; margin:1px 0;
            transition: background 0.15s;
        }
        .my-btn:hover, .store-btn:hover { background: #0d47a1;}
        .back-btn {
            background: #1565c0; color: #fff; border: none; border-radius: 7px;
            padding: 10px 25px; margin: 20px auto; display: block; font-size: 1.1rem; cursor: pointer;
        }
        .centered-btns { display: flex; justify-content: center; gap: 12px; margin-top: 14px;}
        .hidden-section { display: none !important; }

        /* Styles for the new log page */
        .log-page-container {
            max-width: 600px;
            margin: 30px auto;
            padding: 20px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 2px 10px #ddd;
            direction: rtl;
            font-family: Tahoma, Arial;
        }
        .log-page-container h2 {
            text-align: center;
            color: #0d47a1;
            margin-bottom: 20px;
        }
        /* Removed log-entry specific styles as they are now handled by table */
        .print-button-container {
            text-align: center;
            margin-top: 20px;
        }
        /* New styles for the log table */
        .log-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            font-size: 0.95rem;
        }

        .log-table th,
        .log-table td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: right;
            vertical-align: top;
        }

        .log-table th {
            background-color: #f2f2f2;
            font-weight: bold;
        }

        /* Styles for Oil Due Page */
        .oil-due-container {
            max-width: 700px;
            margin: 30px auto;
            padding: 20px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 2px 10px #ddd;
            direction: rtl;
            font-family: Tahoma, Arial;
        }
        .oil-due-container h2 {
            text-align: center;
            color: #0d47a1;
            margin-bottom: 20px;
        }
        .oil-due-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            font-size: 0.95rem;
        }
        .oil-due-table th, .oil-due-table td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: right;
        }
        .oil-due-table th {
            background-color: #f2f2f2;
            font-weight: bold;
        }
        .oil-due-table tr.late-oil {
            background-color: #ffe0e0; /* Light red for late oil */
        }
        .oil-due-table tr.due-soon {
            background-color: #fffacd; /* Light yellow for due soon */
        }
        .search-container {
            display: flex;
            gap: 10px;
            margin-bottom: 15px;
            justify-content: center;
        }
        .search-container input {
            flex: 1;
            padding: 8px 12px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 1rem;
            max-width: 300px;
        }
        .search-container button {
            padding: 8px 15px;
            background: #1976d2;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.15s;
        }
        .search-container button:hover {
            background: #0d47a1;
        }

        /* Styles for Print */
        @media print {
            body { visibility: hidden; } /* Hide the whole body by default */
            .oil-due-container, .log-page-container { /* Show relevant containers specifically */
                visibility: visible;
                position: absolute;
                left: 0;
                top: 0;
                width: 100%;
                box-shadow: none;
                margin: 0;
                padding: 0;
                background-color: #fff; /* Ensure white background for print */
            }
            /* Hide specific elements within the printable containers */
            .oil-due-container .search-container,
            .oil-due-container .back-btn,
            .oil-due-container .print-button-container,
            .oil-due-table th:first-child, /* Hide the checkbox header */
            .oil-due-table td:first-child, /* Hide the checkbox column cells */
            .log-page-container .back-btn, /* Hide back button in log print */
            .log-page-container .print-button-container { /* Hide print button in log print */
                display: none !important;
            }
            /* Styles for oil due table when printing specific rows */
            .oil-due-table tbody tr {
                display: none;
            }
            .oil-due-table tbody tr.print-selected {
                display: table-row;
            }
            .oil-due-table thead {
                display: table-header-group;
            }
            .oil-due-table {
                width: 100%;
                border-collapse: collapse;
            }
            .oil-due-table th, .oil-due-table td {
                border: 1px solid #ccc;
                padding: 5px;
            }
            /* Ensure log table appears correctly */
            .log-page-container .log-table {
                width: 100%;
                border-collapse: collapse;
                margin-top: 0; /* No margin needed for print */
                font-size: 0.85rem;
            }
            .log-page-container .log-table th,
            .log-page-container .log-table td {
                border: 1px solid #ccc;
                padding: 5px;
            }
        }
        /* New styles for image export */
        /* These styles will be applied temporarily before capturing the image */
        body.export-mode {
            visibility: hidden; /* Hide everything by default when exporting */
        }
        body.export-mode .oil-due-container {
            visibility: visible;
            position: absolute;
            left: 0;
            top: 0;
            width: 100%;
            margin: 0;
            padding: 0;
            box-shadow: none; /* Remove shadow for a cleaner image */
            background-color: #fff; /* Ensure white background for image */
        }
        body.export-mode .oil-due-container .search-container,
        body.export-mode .oil-due-container .back-btn,
        body.export-mode .oil-due-container .print-button-container,
        body.export-mode .oil-due-table th:first-child, /* Hide the checkbox header */
        body.export-mode .oil-due-table td:first-child { /* Hide the checkbox column cells */
            display: none !important;
        }
        body.export-mode .oil-due-table tbody tr {
            display: none;
        }
        body.export-mode .oil-due-table tbody tr.print-selected {
            display: table-row;
        }
        body.export-mode .oil-due-table thead {
            display: table-header-group;
        }
        body.export-mode .oil-due-table {
            border: 1px solid #ddd; /* Add a border to the table itself for image clarity */
        }

        /* New styles for Log Print Mode */
        body.print-mode-log {
            visibility: hidden; /* Hide everything by default when in log print mode */
        }
        body.print-mode-log .log-page-container {
            visibility: visible;
            position: absolute;
            left: 0;
            top: 0;
            width: 100%;
            margin: 0;
            padding: 0;
            box-shadow: none; /* Remove shadow for a cleaner print */
            background-color: #fff; /* Ensure white background for print */
        }
        body.print-mode-log .log-page-container .back-btn,
        body.print-mode-log .log-page-container .print-button-container {
            display: none !important; /* Hide buttons in print mode */
        }
        /* Ensure log table appears correctly in image export/print mode */
        body.print-mode-log .log-page-container .log-table {
            border: 1px solid #ddd; /* Add a border to the table itself for image clarity */
        }


        @media (max-width: 600px) {
            .container { max-width: 100vw;}
            .input-row { flex-direction: column; }
            .btn-group, .centered-btns { justify-content: flex-start; }
            .equip-name {font-size: 2rem;}
            .store-banner-red .store-hacker {font-size: 2rem;}
            .log-page-container, .oil-due-container { margin: 10px; padding: 15px; }
            .oil-due-table th, .oil-due-table td { font-size: 0.8rem; padding: 5px;}
            .log-table th, .log-table td { font-size: 0.8rem; padding: 5px;} /* Also for log table */
            .search-container { flex-direction: column; align-items: stretch;}
            .search-container input { max-width: 100%; }
        }
    </style>
</head>
<body>
    <div class="header">رقم واحد لتأجير المعدات</div>
    <div class="container" id="main"></div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>

<script>
// بيانات الأقسام
const sections = [
    { name: "كمبروسر", label: "كمبروسر رقم", count: 35 },
    { name: "رولات", label: "رولا رقم", count: 65 },
    { name: "تور لايت", label: "تور لايت رقم", count: 35 },
    { name: "المولدات", label: "مولد رقم", count: 15 },
    { name: "رولات بسائق", label: "رولا بسائق رقم", count: 10 }
];
let equipmentLogs = {};
let lastOilChangeDate = {}; // stores the last manual oil change date for each equipment
let storeBannerActive = {}; // stores the active store banner state for each equipment
let formData = {}; // جميع بيانات الحقول لكل معدة
let currentOilDueFilter = ''; // New variable to store the current search filter for oil due page

// ----- LocalStorage -----
function saveAllToLocal() {
    localStorage.setItem("equipmentLogs", JSON.stringify(equipmentLogs));
    localStorage.setItem("lastOilChangeDate", JSON.stringify(lastOilChangeDate));
    localStorage.setItem("storeBannerActive", JSON.stringify(storeBannerActive)); // Save banner state
    localStorage.setItem("formData", JSON.stringify(formData));
}
function loadAllFromLocal() {
    try {
        equipmentLogs = JSON.parse(localStorage.getItem("equipmentLogs") || '{}');
        lastOilChangeDate = JSON.parse(localStorage.getItem("lastOilChangeDate") || '{}');
        storeBannerActive = JSON.parse(localStorage.getItem("storeBannerActive") || '{}'); // Load banner state
        formData = JSON.parse(localStorage.getItem("formData") || '{}');
    } catch(e) { equipmentLogs={}; lastOilChangeDate={}; storeBannerActive={}; formData={}; }
}
// ------------------------

function addLog(idx, i, type, desc) {
    let key = `${idx}-${i}`;
    if (!equipmentLogs[key]) equipmentLogs[key] = [];
    equipmentLogs[key].push({
        type: type,
        desc: desc,
        date: new Date()
    });
    saveAllToLocal();
}

function showSections(push = false) {
    let html = "";
    sections.forEach((sec, idx) => {
        html += `<div class="card" onclick="showEquipments(${idx}, true)">${sec.name}</div>`;
    });
    // Add the new "Oil Change Due" section card
    html += `<div class="card" onclick="showOilChangeDuePage(true)">غيارات الزيت المستحقة</div>`;
    document.getElementById("main").innerHTML = html;
    if (push) {
        history.pushState({page: "sections"}, "", "#sections");
    }
}

function showEquipments(idx, push = false) {
    let sec = sections[idx];
    let html = `<button class="back-btn" onclick="showSections(true)">الرجوع للأقسام</button>`;
    html += `<h3 style="text-align:center;margin:15px 0 5px 0;">${sec.name}</h3>`;
    for (let i = 1; i <= sec.count; i++) {
        let key = `${idx}-${i}`;
        let data = formData[key] || {};

        // Determine initial visibility based on stored banner state
        let fieldsHiddenClass = storeBannerActive[key] ? " hidden-section" : "";

        html += `
        <div class="equip-card" id="equip-card-${idx}-${i}">
            <div class="equip-name">${sec.label} ${i}</div>
            <div id="store-banner-red-${idx}-${i}"></div>
            <div id="fields-section-${idx}-${i}" class="${fieldsHiddenClass}">
                <form id="form-${idx}-${i}" onsubmit="event.preventDefault();">
                    <div class="input-row">
                        <label>اسم العميل</label>
                        <input type="text" name="client" placeholder="اسم العميل" value="${data.client ? data.client.replace(/"/g,"&quot;") : ''}">
                    </div>
                    <div class="input-row">
                        <label>الموقع</label>
                        <input type="text" name="location" placeholder="الموقع" value="${data.location ? data.location.replace(/"/g,"&quot;") : ''}">
                    </div>
                    <div class="input-row">
                        <label>تاريخ العمل</label>
                        <input type="date" name="startdate" onchange="updateOilDate(${idx},${i})" value="${data.startdate || ''}">
                    </div>
                    <div class="input-row">
                        <label>ملاحظات</label>
                        <textarea name="notes" rows="1" placeholder="ملاحظات">${data.notes ? data.notes : ''}</textarea>
                    </div>
                    <div id="oil-date-${idx}-${i}" style="margin-top:3px;"></div>
                </form>
                <div class="btn-group" id="btns-${idx}-${i}">
                    <button class="my-btn" onclick="showStoreBanner(${idx},${i},'${sec.label} ${i}','مستودع ضباء');return false;">مستودع ضباء</button>
                    <button class="my-btn" onclick="showStoreBanner(${idx},${i},'${sec.label} ${i}','مستودع تبوك');return false;">مستودع تبوك</button>
                    <button class="my-btn" onclick="showStoreBanner(${idx},${i},'${sec.label} ${i}','مستودع الوافر');return false;">مستودع الوافر</button>
                    <button class="my-btn" onclick="openLogPage(${idx},${i},'${sec.label} ${i}');return false;">السجل</button>
                    <button class="my-btn" onclick="oilChangeNow(${idx},${i},'${sec.label} ${i}');return false;">غيار زيت</button>
                    <button class="my-btn" onclick="saveForm(${idx},${i});return false;">حفظ</button>
                </div>
            </div>
        </div>
        `;
    }
    document.getElementById("main").innerHTML = html;

    // After rendering, check and re-display banners if active
    for (let i = 1; i <= sec.count; i++) {
        let key = `${idx}-${i}`;
        let data = formData[key] || {};
        if (storeBannerActive[key]) {
            if(data.lastStoreAction) {
                showStoreBanner(idx, i, `${sec.label} ${i}`, data.lastStoreAction.storeName, data.lastStoreAction.date, data.lastStoreAction.time);
            } else {
                showStoreBanner(idx, i, `${sec.label} ${i}`, 'مستودع'); // Fallback generic name
            }
        }
        // Always update oil date, regardless of banner state, only if fields are visible
        // Or if there's a startdate/lastOilChangeDate, make sure it's reflected
        if (!storeBannerActive[key] && (data.startdate || lastOilChangeDate[key])) {
             setTimeout(()=>updateOilDate(idx,i), 200);
        } else if (storeBannerActive[key]) { // If banner is active, hide oil date div
            let oilDiv = document.getElementById(`oil-date-${idx}-${i}`);
            if (oilDiv) oilDiv.innerHTML = "";
        }
    }
    if (push) {
        history.pushState({page: "equipments", idx: idx}, "", "#equipments-"+idx);
    }
}

function calcOilChange(startDate) {
    if (!startDate) return null;
    let date = new Date(startDate);
    let count = 0;
    while (count < 8) {
        if (date.getDay() !== 5) { // 5 is Friday
            count++;
        }
        if (count < 8) {
            date.setDate(date.getDate() + 1);
        }
    }
    return date;
}

function updateOilDate(idx, i) {
    let form = document.getElementById(`form-${idx}-${i}`);
    // Only update if the form is visible (not hidden by a banner)
    if (!form || form.closest('.hidden-section')) {
        let oilDiv = document.getElementById(`oil-date-${idx}-${i}`);
        if(oilDiv) oilDiv.innerHTML = ""; // Clear oil date if section is hidden
        return;
    }

    let key = `${idx}-${i}`;
    let startDate = form.elements["startdate"].value;
    let oilDiv = document.getElementById(`oil-date-${idx}-${i}`);

    // Prioritize manual oil change date if it exists
    let calculationDate = lastOilChangeDate[key] || startDate;

    if (!calculationDate) {
        oilDiv.innerHTML = "";
        return;
    }

    let nextOil = calcOilChange(calculationDate);
    if (!nextOil) { oilDiv.innerHTML = ""; return;}

    let today = new Date();
    today.setHours(0,0,0,0);

    let daysLate = Math.floor((today - nextOil)/(1000*60*60*24));
    let oilMsg = "", oilClass = "";
    if (daysLate > 0) {
        oilMsg = `موعد غيار الزيت: <b>${formatDateAr(nextOil)}</b> <span style="margin-right:8px;">(<b style="color:#b40000;">متأخر ${daysLate} يوم</b>)</span>`;
        oilClass = "oil-alert oil-late";
    } else {
        oilMsg = `موعد غيار الزيت: <b>${formatDateAr(nextOil)}</b>`;
        oilClass = "oil-alert oil-normal";
    }
    oilDiv.innerHTML = `<span class="${oilClass}">${oilMsg}</span>`;
}

function oilChangeNow(idx, i, equipName) {
    let key = `${idx}-${i}`;
    let todayStr = (new Date()).toISOString().slice(0,10);
    lastOilChangeDate[key] = todayStr; // Update the last manual oil change date
    updateOilDate(idx, i); // Recalculate and display based on new date
    addLog(idx, i, "غيار زيت", `تم غيار الزيت للمعدة (${equipName}) بتاريخ ${formatDateAr(todayStr)}`);
    saveAllToLocal();
    alert("تم غيار الزيت لهذه المعدة. سيبدأ العد من جديد من اليوم.");
}

function formatDateAr(date) {
    if (typeof date === "string") date = new Date(date);
    let d = date.getDate();
    let m = date.getMonth()+1;
    let y = date.getFullYear();
    return (d<10?"0":"")+d+"-"+(m<10?"0":"")+m+"-"+y;
}

function saveForm(idx, i) {
    let form = document.getElementById(`form-${idx}-${i}`);
    let key = `${idx}-${i}`;
    let data = {
        client: form.elements["client"].value,
        location: form.elements["location"].value,
        startdate: form.elements["startdate"].value,
        notes: form.elements["notes"].value,
        lastStoreAction: formData[key] ? formData[key].lastStoreAction : undefined // Preserve last store action if exists
    };
    formData[key] = data;
    saveAllToLocal();
    let desc = `تم حفظ بيانات المعدة:\n` +
        `- اسم العميل: ${data.client}\n` +
        `- الموقع: ${data.location}\n` +
        `- تاريخ العمل: ${formatDateAr(data.startdate)}\n` +
        `- ملاحظات: ${data.notes}`;
    addLog(idx, i, "حفظ", desc.replace(/\n/g,"<br>"));
    alert("تم حفظ البيانات:\n" +
        "اسم العميل: " + data.client + "\n" +
        "الموقع: " + data.location + "\n" +
        "تاريخ العمل: " + data.startdate + "\n" +
        "ملاحظات: " + data.notes
    );
    // After saving, ensure oil date is updated in case startdate changed
    updateOilDate(idx, i);
}

// Added optional date and time parameters to reconstruct banner correctly on load
function showStoreBanner(idx, i, equipName, storeName, storedDate = null, storedTime = null) {
    let bannerDiv = document.getElementById(`store-banner-red-${idx}-${i}`);
    let fieldsDiv = document.getElementById(`fields-section-${idx}-${i}`);
    let key = `${idx}-${i}`;

    // If banner is already active and we're not explicitly reconstructing from stored data, just return
    // This prevents re-rendering the banner if it's already visible due to user clicks.
    if (storeBannerActive[key] && !storedDate) {
        return;
    }

    const now = new Date();
    const dateStr = storedDate || formatDateAr(now);
    const timeStr = storedTime || now.toLocaleTimeString('ar-EG', {hour: '2-digit', minute:'2-digit', second:'2-digit'});

    // Only add log if it's a new user action, not a page reload reconstruction
    if (!storedDate) { // If storedDate is null, it means it's a fresh click
        addLog(idx, i, "مستودع", `تم الضغط على زر ${storeName}`);
    }

    bannerDiv.innerHTML = `
        <div class="store-banner-red">
            <span class="store-hacker">${storeName}</span>
            <div class="banner-info">${dateStr} / ${timeStr}</div>
            <div class="centered-btns" style="margin-top:14px;">
                <button class="store-btn log-btn" data-idx="${idx}" data-i="${i}" data-equip="${equipName}">السجل</button>
                <button class="store-btn" onclick="resetStoreBanner(${idx},${i})">إعادة تعيين</button>
            </div>
        </div>
    `;
    fieldsDiv.classList.add("hidden-section");
    storeBannerActive[key] = true;

    // Store the last store action details in formData for reconstruction
    if (!formData[key]) formData[key] = {};
    formData[key].lastStoreAction = {
        storeName: storeName,
        date: dateStr,
        time: timeStr
    };

    saveAllToLocal();

    // Ensure the log button correctly points to the new log page
    setTimeout(()=>{
        let btn = document.querySelector('.store-btn.log-btn[data-idx="'+idx+'"][data-i="'+i+'"]');
        if(btn) btn.onclick = function(){ openLogPage(idx,i,equipName); return false; };
    }, 100);

    // Hide the oil date when the banner is active
    let oilDiv = document.getElementById(`oil-date-${idx}-${i}`);
    if (oilDiv) oilDiv.innerHTML = "";
}

function resetStoreBanner(idx, i) {
    let bannerDiv = document.getElementById(`store-banner-red-${idx}-${i}`);
    let fieldsDiv = document.getElementById(`fields-section-${idx}-${i}`);
    bannerDiv.innerHTML = "";
    fieldsDiv.classList.remove("hidden-section");
    let form = document.getElementById(`form-${idx}-${i}`);
    let key = `${idx}-${i}`;

    // Clear form fields
    if (form) {
        form.elements["client"].value = "";
        form.elements["location"].value = "";
        form.elements["startdate"].value = "";
        form.elements["notes"].value = "";
        let oilDiv = document.getElementById(`oil-date-${idx}-${i}`);
        if (oilDiv) oilDiv.innerHTML = ""; // تم تصحيح الخطأ الإملائي هنا
    }

    // Clear formData, lastOilChangeDate and storeBannerActive for this equipment and save
    formData[key] = {}; // Clear all form data for this specific equipment
    lastOilChangeDate[key] = undefined; // Clear manual oil change date
    storeBannerActive[key] = false; // Deactivate banner state
    saveAllToLocal(); // هنا يجب أن يتم الحفظ مباشرة بعد تغيير الحالة
    addLog(idx, i, "إعادة تعيين", "تم إعادة تعيين بيانات المعدة وإفراغ الحقول.");
    // بعد إعادة التعيين، قم بتحديث عرض تاريخ الزيت إذا كانت الحقول مرئية
    updateOilDate(idx, i);
}

// Function to open log page
function openLogPage(idx, i, equipName) {
    let key = `${idx}-${i}`;
    let logArr = equipmentLogs[key] || [];

    let logHtml = `
        <div class="log-page-container">
            <button class="back-btn" onclick="history.back()">الرجوع للمعدة</button>
            <h2>سجل الإجراءات لـ ${equipName}</h2>
    `;
    if (logArr.length === 0) {
        logHtml += "<p style='text-align:center;'>لا يوجد أي إجراء بعد.</p>";
    } else {
        logHtml += `
            <table class="log-table">
                <thead>
                    <tr>
                        <th>النوع</th>
                        <th>الوصف</th>
                        <th>التاريخ والوقت</th>
                    </tr>
                </thead>
                <tbody>
        `;
        logArr.slice().reverse().forEach(log => { // Reverse to show latest first
            let date = formatDateAr(log.date) + " " + new Date(log.date).toLocaleTimeString('ar-EG', {hour:'2-digit',minute:'2-digit',second:'2-digit'});
            logHtml += `
                <tr>
                    <td>${log.type}</td>
                    <td>${log.desc}</td>
                    <td>${date}</td>
                </tr>
            `;
        });
        logHtml += `
                </tbody>
            </table>
        `;
    }
    logHtml += `
            <div class="print-button-container">
                <button class="my-btn" onclick="printLogPage()">طباعة السجل</button>
            </div>
        </div>
    `;

    document.getElementById("main").innerHTML = logHtml;
    history.pushState({page: "log", idx: idx, i: i, equipName: equipName}, "", `#log-${idx}-${i}`);
}

// NEW FUNCTION: Print the log page content
function printLogPage() {
    const logContainer = document.querySelector('.log-page-container');
    if (!logContainer) {
        alert("لا يوجد سجل للطباعة.");
        return;
    }

    // Add a temporary class to the body for print styling
    document.body.classList.add('print-mode-log');

    // Trigger print
    window.print();

    // After printing, remove the temporary class
    setTimeout(() => {
        document.body.classList.remove('print-mode-log');
    }, 500); // Small delay to ensure print dialog is handled
}


// Show Oil Change Due Page
function showOilChangeDuePage(push = false) {
    let allOilDueEquipments = [];
    const today = new Date();
    today.setHours(0,0,0,0);

    // Collect all equipments due for oil change
    sections.forEach((sec, secIdx) => {
        for (let i = 1; i <= sec.count; i++) {
            let key = `${secIdx}-${i}`;
            let data = formData[key] || {};
            let calculationDate = lastOilChangeDate[key] || data.startdate;

            if (calculationDate) {
                let nextOil = calcOilChange(calculationDate);
                if (nextOil) {
                    let daysLate = Math.floor((today - nextOil) / (1000 * 60 * 60 * 24));
                    allOilDueEquipments.push({
                        name: `${sec.label} ${i}`,
                        client: data.client || 'غير مسجل',
                        location: data.location || 'غير مسجل',
                        startDate: formatDateAr(calculationDate),
                        nextOilDate: formatDateAr(nextOil),
                        daysLate: daysLate,
                        _nextOilDateObj: nextOil,
                        _startDateObj: new Date(calculationDate)
                    });
                }
            }
        }
    });

    // Apply filter if currentOilDueFilter is set
    let filteredEquipments = allOilDueEquipments.filter(equip => {
        if (!currentOilDueFilter) return true; // No filter, show all
        const searchTerm = currentOilDueFilter.toLowerCase();
        return equip.name.toLowerCase().includes(searchTerm) ||
               equip.client.toLowerCase().includes(searchTerm) ||
               equip.location.toLowerCase().includes(searchTerm);
    });

    // Sort filtered equipments
    filteredEquipments.sort((a, b) => {
        if (a.daysLate > 0 && b.daysLate <= 0) return -1;
        if (a.daysLate <= 0 && b.daysLate > 0) return 1;
        return a._nextOilDateObj - b._nextOilDateObj;
    });

    let html = `
        <div class="oil-due-container">
            <button class="back-btn" onclick="showSections(true)">الرجوع للصفحة الرئيسية</button>
            <h2>المعدات المستحقة لغيار الزيت</h2>
            <div class="search-container">
                <input type="text" id="oilSearchInput" placeholder="البحث باسم المعدة أو العميل أو الموقع" value="${currentOilDueFilter}">
                <button onclick="applyOilSearch()">بحث</button>
                <button onclick="clearOilSearch()">مسح البحث</button>
            </div>
            <div class="print-button-container">
                <button class="my-btn" onclick="printSelectedOilDue()">طباعة المحدد</button>
                <button class="my-btn" onclick="exportSelectedOilDueAsImage()">تصدير كصورة</button> <button class="my-btn" onclick="selectAllOilDue(true)">تحديد الكل</button>
                <button class="my-btn" onclick="selectAllOilDue(false)">إلغاء تحديد الكل</button>
            </div>
            <div id="oil-due-table-container">`; // New container for the table to refresh it easily

    if (filteredEquipments.length === 0) {
        html += "<p style='text-align:center;'>لا توجد معدات مستحقة لغيار الزيت حالياً أو لا يوجد نتائج للبحث.</p>";
    } else {
        html += `<table class="oil-due-table">
            <thead>
                <tr>
                    <th><input type="checkbox" id="checkAllOilDue" onclick="toggleAllOilDue(this)"></th> <th>المعدة</th>
                    <th>اسم العميل</th>
                    <th>الموقع</th>
                    <th>تاريخ بدء العمل/آخر غيار</th>
                    <th>موعد الغيار القادم</th>
                    <th>أيام التأخير</th>
                </tr>
            </thead>
            <tbody>`;
        filteredEquipments.forEach((equip, index) => {
            let rowClass = '';
            if (equip.daysLate > 0) {
                rowClass = 'late-oil';
            } else if (equip.daysLate >= -7 && equip.daysLate <= 0) { // Due within 7 days including today
                rowClass = 'due-soon';
            }
            // Add a unique ID to each row for easy selection and add 'data-index' for re-rendering logic
            html += `<tr class="${rowClass}" id="oil-due-row-${index}">
                <td><input type="checkbox" class="oil-due-checkbox"></td>
                <td>${equip.name}</td>
                <td>${equip.client}</td>
                <td>${equip.location}</td>
                <td>${equip.startDate}</td>
                <td>${equip.nextOilDate}</td>
                <td style="color:${equip.daysLate > 0 ? '#b40000' : 'inherit'};">
                    ${equip.daysLate > 0 ? `متأخر ${equip.daysLate} يوم` : `متبقي ${Math.abs(equip.daysLate)} يوم`}
                </td>
            </tr>`;
        });
        html += `</tbody></table>`;
    }
    html += `</div></div>`; // Close oil-due-table-container and oil-due-container

    document.getElementById("main").innerHTML = html;
    if (push) {
        history.pushState({page: "oilDue", filter: currentOilDueFilter}, "", "#oil-due");
    }
}

// New functions for search
function applyOilSearch() {
    currentOilDueFilter = document.getElementById("oilSearchInput").value.trim();
    showOilChangeDuePage(false); // Re-render the page with the new filter
}

function clearOilSearch() {
    document.getElementById("oilSearchInput").value = '';
    currentOilDueFilter = '';
    showOilChangeDuePage(false); // Re-render to show all
}

// New functions for selecting rows
function toggleAllOilDue(source) {
    let checkboxes = document.querySelectorAll('.oil-due-checkbox');
    for (let i = 0; i < checkboxes.length; i++) {
        checkboxes[i].checked = source.checked;
    }
}

function selectAllOilDue(select) {
    let checkboxes = document.querySelectorAll('.oil-due-checkbox');
    for (let i = 0; i < checkboxes.length; i++) {
        checkboxes[i].checked = select;
    }
    // Update the "check all" checkbox state
    const checkAllBox = document.getElementById('checkAllOilDue');
    if (checkAllBox) {
        checkAllBox.checked = select;
    }
}

// Function to print selected rows
function printSelectedOilDue() {
    const tableRows = document.querySelectorAll('.oil-due-table tbody tr');
    let anySelected = false;

    // Add a class to selected rows for print styling
    tableRows.forEach(row => {
        const checkbox = row.querySelector('.oil-due-checkbox');
        if (checkbox && checkbox.checked) {
            row.classList.add('print-selected');
            anySelected = true;
        } else {
            row.classList.remove('print-selected'); // Ensure unselected rows don't have the class
        }
    });

    if (!anySelected) {
        alert("الرجاء تحديد صف واحد على الأقل للطباعة.");
        return;
    }

    // Trigger print
    window.print();

    // After printing, remove the 'print-selected' class to restore normal display
    setTimeout(() => {
        tableRows.forEach(row => {
            row.classList.remove('print-selected');
        });
    }, 500); // Small delay to ensure print dialog is handled
}

// NEW FUNCTION: Export selected table rows as an image
async function exportSelectedOilDueAsImage() {
    const oilDueContainer = document.querySelector('.oil-due-container');
    const tableRows = document.querySelectorAll('.oil-due-table tbody tr');
    let anySelected = false;

    // Temporarily add 'print-selected' class to selected rows and check if any are selected
    tableRows.forEach(row => {
        const checkbox = row.querySelector('.oil-due-checkbox');
        if (checkbox && checkbox.checked) {
            row.classList.add('print-selected');
            anySelected = true;
        } else {
            row.classList.remove('print-selected');
        }
    });

    if (!anySelected) {
        alert("الرجاء تحديد صف واحد على الأقل للتصدير كصورة.");
        return;
    }

    // Apply temporary styles for export (similar to print styles but without print media query issues)
    document.body.classList.add('export-mode');

    // Wait for styles to apply before rendering
    await new Promise(resolve => setTimeout(resolve, 50));

    try {
        // Use html2canvas to capture the content of the oil-due-container
        const canvas = await html2canvas(oilDueContainer, {
            scale: 2, // Increase scale for higher quality image
            useCORS: true, // Needed if you have images from different origins (unlikely here)
            logging: false, // Disable logging for cleaner console
            backgroundColor: null // Set to null to allow CSS background to take effect
        });

        // Create a temporary link to download the image
        const imgData = canvas.toDataURL('image/png');
        const link = document.createElement('a');
        link.href = imgData;
        link.download = 'غيارات_الزيت_المستحقة_المحددة.png';
        document.body.appendChild(link); // Append to body to make it clickable
        link.click(); // Programmatically click the link to trigger download
        document.body.removeChild(link); // Remove the link

    } catch (error) {
        console.error("Error generating image:", error);
        alert("حدث خطأ أثناء تصدير الصورة. الرجاء المحاولة مرة أخرى.");
    } finally {
        // Clean up: remove temporary classes and restore normal display
        document.body.classList.remove('export-mode');
        tableRows.forEach(row => {
            row.classList.remove('print-selected');
        });
    }
}


window.onpopstate = function(event) {
    if (!event.state || event.state.page === "sections") {
        showSections(false);
    } else if (event.state.page === "equipments") {
        showEquipments(event.state.idx, false);
    } else if (event.state.page === "log") {
        openLogPage(event.state.idx, event.state.i, event.state.equipName); // Re-call openLogPage to reconstruct
    } else if (event.state.page === "oilDue") {
        currentOilDueFilter = event.state.filter || ''; // Restore filter
        showOilChangeDuePage(false);
    }
};

window.onload = function() {
    loadAllFromLocal();
    showSections(false);
    // Replace current state to ensure initial back button press works correctly
    history.replaceState({page: "sections"}, "", "#sections");
}
</script>
</body>
</html>

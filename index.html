<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Life History & Daily Diary</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.1.1/crypto-js.min.js"></script>
  <style>
    :root { --primary: #1a73e8; --bg: #f8f9fa; --card: #ffffff; --text: #202124; --danger: #d93025; }
    body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background: var(--bg); color: var(--text); margin: 0; padding: 20px; }
    .container { max-width: 900px; margin: 0 auto; }
    header { display: flex; justify-content: space-between; align-items: center; border-bottom: 2px solid #e0e0e0; padding-bottom: 15px; margin-bottom: 20px; }
    .tabs { display: flex; gap: 10px; margin-bottom: 20px; }
    .tab-btn { padding: 10px 18px; border: none; background: #e8eaed; cursor: pointer; border-radius: 6px; font-weight: bold; }
    .tab-btn.active { background: var(--primary); color: white; }
    .card { background: var(--card); border-radius: 8px; padding: 20px; box-shadow: 0 2px 6px rgba(0,0,0,0.08); margin-bottom: 20px; position: relative; }
    input, textarea, select, button { width: 100%; padding: 10px; margin-top: 8px; margin-bottom: 15px; border: 1px solid #dadce0; border-radius: 6px; box-sizing: border-box; }
    button.submit-btn { background: var(--primary); color: white; font-weight: bold; border: none; cursor: pointer; }
    .delete-btn { background: #fce8e6; color: var(--danger); border: 1px solid var(--danger); font-weight: bold; padding: 6px 12px; border-radius: 6px; cursor: pointer; width: auto; margin-top: 10px; }
    .delete-btn:hover { background: var(--danger); color: white; }
    .entry-header { display: flex; justify-content: space-between; align-items: center; }
    .entry-photo { max-width: 100%; max-height: 250px; border-radius: 6px; margin-top: 10px; }
    .secret-block { background: #fff0f0; border-left: 4px solid #d93025; padding: 10px; border-radius: 4px; margin-top: 10px; }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <h1>📖 Life History & Daily Diary</h1>
      <small>Host: deykrajay.github.io</small>
    </header>

    <div class="tabs">
      <button class="tab-btn active" onclick="switchTab('new-entry')">✍️ New Entry</button>
      <button class="tab-btn" onclick="switchTab('dashboard')">📊 Dashboard</button>
      <button class="tab-btn" onclick="switchTab('monthly')">📅 Monthly Review</button>
    </div>

    <!-- TAB 1: NEW ENTRY -->
    <div id="new-entry" class="tab-content">
      <div class="card">
        <h3>Daily Entry & Reflection</h3>
        <label>Date</label>
        <input type="date" id="entry-date">
        
        <label>Title / Special Note</label>
        <input type="text" id="entry-title" placeholder="Summary or highlight of the day">

        <label>Daily Journal Write-up</label>
        <textarea id="entry-content" rows="5" placeholder="Write about your day..."></textarea>

        <label>Attach Photo</label>
        <input type="file" id="entry-photo" accept="image/*" onchange="previewImage(event)">
        <img id="photo-preview" class="entry-photo" style="display:none;">

        <label>🔒 Secret Text (Encrypted with Password)</label>
        <textarea id="secret-content" rows="2" placeholder="Write confidential notes here..."></textarea>
        <input type="password" id="secret-pass" placeholder="Enter passphrase to lock this secret text">

        <label>⏰ Set Reminder / Alarm Notification</label>
        <input type="datetime-local" id="reminder-time">

        <button class="submit-btn" onclick="saveEntry()">Save Daily Entry</button>
      </div>
    </div>

    <!-- TAB 2: DASHBOARD -->
    <div id="dashboard" class="tab-content" style="display:none;">
      <div class="card">
        <h3>Recent Timeline & Entries</h3>
        <div id="entries-list"></div>
      </div>
    </div>

    <!-- TAB 3: MONTHLY REVIEW -->
    <div id="monthly" class="tab-content" style="display:none;">
      <div class="card">
        <h3>Monthly Reflection Aggregator</h3>
        <label>Select Month</label>
        <input type="month" id="review-month" onchange="renderMonthlyReview()">
        <div id="monthly-summary" style="margin-top:15px;"></div>
      </div>
    </div>
  </div>

  <script>
    document.getElementById('entry-date').valueAsDate = new Date();
    let imageBase64 = "";

    function previewImage(event) {
      const reader = new FileReader();
      reader.onload = function() {
        imageBase64 = reader.result;
        const img = document.getElementById('photo-preview');
        img.src = imageBase64;
        img.style.display = 'block';
      };
      reader.readAsDataURL(event.target.files[0]);
    }

    function switchTab(tabId) {
      document.querySelectorAll('.tab-content').forEach(el => el.style.display = 'none');
      document.querySelectorAll('.tab-btn').forEach(el => el.classList.remove('active'));
      document.getElementById(tabId).style.display = 'block';
      event.target.classList.add('active');
      if (tabId === 'dashboard') renderDashboard();
    }

    function saveEntry() {
      const date = document.getElementById('entry-date').value;
      const title = document.getElementById('entry-title').value;
      const content = document.getElementById('entry-content').value;
      const secret = document.getElementById('secret-content').value;
      const pass = document.getElementById('secret-pass').value;
      const reminder = document.getElementById('reminder-time').value;

      let encryptedSecret = "";
      if (secret && pass) {
        encryptedSecret = CryptoJS.AES.encrypt(secret, pass).toString();
      }

      const id = Date.now(); // Unique ID for each entry
      const entry = { id, date, title, content, photo: imageBase64, secret: encryptedSecret, reminder };
      let entries = JSON.parse(localStorage.getItem('diary_entries') || '[]');
      entries.push(entry);
      localStorage.setItem('diary_entries', JSON.stringify(entries));

      if (reminder) {
        const timeDiff = new Date(reminder).getTime() - new Date().getTime();
        if (timeDiff > 0) {
          Notification.requestPermission().then(perm => {
            if (perm === 'granted') {
              setTimeout(() => {
                new Notification("⏰ Diary Alarm", { body: title || "You have a scheduled diary note!" });
              }, timeDiff);
            }
          });
        }
      }

      alert("Entry saved successfully!");
      document.getElementById('entry-title').value = '';
      document.getElementById('entry-content').value = '';
      document.getElementById('secret-content').value = '';
      document.getElementById('secret-pass').value = '';
      document.getElementById('photo-preview').style.display = 'none';
      imageBase64 = "";
    }

    function deleteEntry(id) {
      if (confirm("Are you sure you want to delete this diary entry? This action cannot be undone.")) {
        let entries = JSON.parse(localStorage.getItem('diary_entries') || '[]');
        entries = entries.filter(e => e.id !== id);
        localStorage.setItem('diary_entries', JSON.stringify(entries));
        renderDashboard(); // Refresh the list
      }
    }

    function renderDashboard() {
      const list = document.getElementById('entries-list');
      const entries = JSON.parse(localStorage.getItem('diary_entries') || '[]').reverse();
      if (entries.length === 0) { list.innerHTML = "<p>No entries logged yet.</p>"; return; }
      
      list.innerHTML = entries.map((e, index) => `
        <div class="card" style="border: 1px solid #e0e0e0;">
          <div class="entry-header">
            <h4>📅 ${e.date} - ${e.title || 'Untitled'}</h4>
            <button class="delete-btn" onclick="deleteEntry(${e.id})">🗑️ Delete</button>
          </div>
          <p>${e.content}</p>
          ${e.photo ? `<img src="${e.photo}" class="entry-photo">` : ''}
          ${e.secret ? `
            <div class="secret-block">
              <strong>🔒 Encrypted Secret Text</strong><br>
              <input type="password" id="unlock-${index}" placeholder="Passphrase" style="width: 200px; display:inline;">
              <button onclick="unlockSecret(${index}, '${e.secret}')" style="width:auto;">Unlock</button>
              <p id="secret-text-${index}" style="font-weight:bold; color:#b30000;"></p>
            </div>
          ` : ''}
        </div>
      `).join('');
    }

    function unlockSecret(id, cipher) {
      const pass = document.getElementById(`unlock-${id}`).value;
      try {
        const bytes = CryptoJS.AES.decrypt(cipher, pass);
        const decrypted = bytes.toString(CryptoJS.enc.Utf8);
        document.getElementById(`secret-text-${id}`).innerText = decrypted || "❌ Wrong Password!";
      } catch(err) {
        document.getElementById(`secret-text-${id}`).innerText = "❌ Wrong Password!";
      }
    }

    function renderMonthlyReview() {
      const monthVal = document.getElementById('review-month').value;
      if (!monthVal) return;
      const entries = JSON.parse(localStorage.getItem('diary_entries') || '[]');
      const filtered = entries.filter(e => e.date.startsWith(monthVal));
      
      const summaryDiv = document.getElementById('monthly-summary');
      summaryDiv.innerHTML = `
        <p><strong>Total Entries logged in ${monthVal}:</strong> ${filtered.length}</p>
        <ul>
          ${filtered.map(e => `<li><strong>${e.date}:</strong>${e.title || 'Entry'}</li>`).join('')}
        </ul>
      `;
    }
  </script>
</body>
</html>

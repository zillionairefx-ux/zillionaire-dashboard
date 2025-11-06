<!doctype html>
<html>
<head>
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Zillionaire Aviator Assistant</title>
  <style>
    body { background:#050505; color:#bfff8c; font-family:Arial,sans-serif; margin:0; padding:16px;}
    .big { font-size:72px; color:#1aff00; text-align:center; margin-top:8px;}
    button { background:#0f0; color:#000; border:none; padding:10px 18px; border-radius:8px; font-weight:bold;}
    .card { background:#111; border-radius:12px; padding:12px; margin:12px 0; }
  </style>
</head>
<body>
  <h1>Zillionaire Aviator Assistant</h1>
  <div class="card">
    <div id="mult" class="big">—</div>
    <div style="text-align:center;">
      <button id="signalBtn">GET SIGNAL</button>
    </div>
  </div>
  <div class="card">
    <div><strong>Active Servers / Console</strong></div>
    <pre id="console" style="height:200px; overflow:auto; background:#000; color:#0f0;"></pre>
  </div>

<script>
  let latestSignal = {signal:'WAIT', reason:''};
  document.getElementById('signalBtn').addEventListener('click', () => {
    alert(`Signal: ${latestSignal.signal}\nReason: ${latestSignal.reason}`);
  });

  // Demo: random multiplier updates so you can test browser notification and layout.
  setInterval(() => {
    const m = (Math.random()*6 + 1).toFixed(2);
    document.getElementById('mult').innerText = m + 'x';
    const log = document.getElementById('console');
    log.textContent += new Date().toLocaleTimeString() + ' Round -> ' + m + 'x\n';
    if (parseFloat(m) >= 3.0) {
      latestSignal = {signal:'BET', reason:'demo threshold >= 3.0'};
      if (Notification && Notification.permission === 'granted') {
        new Notification('Zillionaire: BET signal', {body: `${m}x — Demo`});
      }
    } else {
      latestSignal = {signal:'WAIT', reason:'demo'};
    }
  }, 4000);

  // Request notification permission when page loads
  if ('Notification' in window && Notification.permission !== 'granted') {
    Notification.requestPermission();
  }
</script>
</body>
</html>

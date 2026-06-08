<!doctype html>
<html lang="tr">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Eren & Melis - Düğün Geri Sayımı</title>
  <style>
    *{box-sizing:border-box} body{margin:0;min-height:100vh;font-family:Arial,Helvetica,sans-serif;background:linear-gradient(135deg,#fff7f1,#f5d9d0);color:#2b2024;display:flex;align-items:center;justify-content:center;padding:24px}.card{width:100%;max-width:980px;background:rgba(255,255,255,.78);border:1px solid rgba(183,110,121,.25);border-radius:32px;box-shadow:0 25px 80px rgba(123,61,73,.18);overflow:hidden;display:grid;grid-template-columns:1fr 1fr}.left{padding:56px}.small{letter-spacing:3px;text-transform:uppercase;color:#c79a43;font-weight:800;font-size:13px}h1{font-size:64px;line-height:1;margin:20px 0 10px;color:#7b3d49}.subtitle{font-size:24px;font-weight:700}.date{display:inline-block;margin-top:18px;padding:12px 18px;border-radius:999px;background:#fff;border:1px solid rgba(183,110,121,.25);font-weight:800;color:#7b3d49}.msg{margin-top:24px;color:#765f68;line-height:1.7;font-size:17px}.right{background:linear-gradient(160deg,#7b3d49,#b76e79);color:white;padding:48px 32px;display:flex;align-items:center}.panel{width:100%}.panel-title{text-align:center;letter-spacing:3px;text-transform:uppercase;color:rgba(255,255,255,.78);font-weight:800;margin-bottom:22px}.countdown{display:grid;grid-template-columns:repeat(2,1fr);gap:14px}.box{text-align:center;background:rgba(255,255,255,.14);border:1px solid rgba(255,255,255,.24);border-radius:22px;padding:24px 10px}.num{display:block;font-size:58px;font-weight:900;line-height:1}.label{display:block;margin-top:8px;font-size:13px;letter-spacing:2px;text-transform:uppercase;color:rgba(255,255,255,.8);font-weight:700}.note{text-align:center;margin-top:24px;line-height:1.6;color:rgba(255,255,255,.85)}.btn{display:block;width:max-content;margin:22px auto 0;color:white;text-decoration:none;border:1px solid rgba(255,255,255,.4);border-radius:999px;padding:12px 18px;font-weight:800;background:rgba(255,255,255,.12)}@media(max-width:800px){.card{grid-template-columns:1fr}.left{text-align:center;padding:42px 24px}h1{font-size:52px}.right{padding:36px 20px}.num{font-size:42px}}
  </style>
</head>
<body>
  <main class="card">
    <section class="left">
      <div class="small">Düğünümüze Davetlisiniz</div>
      <h1>Eren &amp; Melis</h1>
      <div class="subtitle">Sonsuzluğa bir adım daha...</div>
      <div class="date">27 Eylül 2026</div>
      <p class="msg">Bu özel günümüzde mutluluğumuzu sevdiklerimizle paylaşmak istiyoruz. Aşkımızın en güzel anına sayılı günler kala, geri sayım başladı.</p>
    </section>
    <section class="right">
      <div class="panel">
        <div class="panel-title">Düğüne Kalan Süre</div>
        <div class="countdown">
          <div class="box"><span class="num" id="days">00</span><span class="label">Gün</span></div>
          <div class="box"><span class="num" id="hours">00</span><span class="label">Saat</span></div>
          <div class="box"><span class="num" id="minutes">00</span><span class="label">Dakika</span></div>
          <div class="box"><span class="num" id="seconds">00</span><span class="label">Saniye</span></div>
        </div>
        <p class="note" id="note">27 Eylül 2026 için geri sayım devam ediyor.</p>
        <a class="btn" href="https://www.google.com/calendar/render?action=TEMPLATE&text=Eren%20%26%20Melis%20D%C3%BC%C4%9F%C3%BCn%C3%BC&dates=20260927T170000Z/20260927T210000Z" target="_blank" rel="noopener">Takvime Ekle</a>
      </div>
    </section>
  </main>
  <script>
    const targetDate = new Date('2026-09-27T20:00:00+03:00').getTime();
    function pad(n){return String(n).padStart(2,'0')}
    function updateCountdown(){
      const now = Date.now();
      const distance = targetDate - now;
      if(distance <= 0){
        days.textContent='00'; hours.textContent='00'; minutes.textContent='00'; seconds.textContent='00';
        note.textContent='Bugün Eren & Melis’in en özel günü. Mutluluklar!';
        return;
      }
      const d = Math.floor(distance/(1000*60*60*24));
      const h = Math.floor((distance%(1000*60*60*24))/(1000*60*60));
      const m = Math.floor((distance%(1000*60*60))/(1000*60));
      const s = Math.floor((distance%(1000*60))/1000);
      document.getElementById('days').textContent=d;
      document.getElementById('hours').textContent=pad(h);
      document.getElementById('minutes').textContent=pad(m);
      document.getElementById('seconds').textContent=pad(s);
    }
    updateCountdown(); setInterval(updateCountdown,1000);
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>HIMADIKTI</title>
<style>
:root{--bg:#f4f7fb;--card:#fff;--text:#16202e;--muted:#5b6a7d;--pri:#1d4ed8;--pri2:#1e3a8a;--acc:#f59e0b;--line:#e2e8f0;--ok:#16a34a;--err:#dc2626}
@media(prefers-color-scheme:dark){:root{--bg:#0b1119;--card:#131c27;--text:#e8eef6;--muted:#97a6b8;--pri:#5b8cff;--line:#24313f}}
*{box-sizing:border-box}html{scroll-behavior:smooth;scroll-padding-top:70px}
body{margin:0;font-family:system-ui,sans-serif;background:var(--bg);color:var(--text);line-height:1.65}
header{position:sticky;top:0;z-index:20;background:var(--card);border-bottom:1px solid var(--line)}
.nav{max-width:1000px;margin:auto;display:flex;align-items:center;justify-content:space-between;padding:10px 16px}
.logo{display:flex;align-items:center;gap:10px;font-weight:800;font-size:1.15rem;color:var(--text);text-decoration:none}
.logo i{width:34px;height:34px;border-radius:10px;background:linear-gradient(135deg,var(--pri2),var(--pri));color:#fff;display:grid;place-items:center;font-style:normal}
.menu{display:flex;gap:2px}
.menu a{color:var(--text);text-decoration:none;padding:7px 11px;border-radius:8px;font-size:.92rem}
.menu a.cta{background:var(--pri);color:#fff;font-weight:600}
#burger{display:none;background:none;border:1px solid var(--line);color:var(--text);border-radius:8px;padding:6px 10px;font-size:1.2rem}
@media(max-width:760px){#burger{display:block}.menu{display:none;position:absolute;top:100%;left:0;right:0;background:var(--card);flex-direction:column;padding:8px 16px 14px}.menu.open{display:flex}}
.hero{background:linear-gradient(135deg,#0f1f55,#1d4ed8);color:#fff;padding:72px 16px 64px;text-align:center}
.hero .in{max-width:720px;margin:auto}
.badge{display:inline-block;background:rgba(255,255,255,.15);padding:4px 14px;border-radius:99px;font-size:.82rem;margin-bottom:14px}
.hero h1{font-size:clamp(1.9rem,6vw,3rem);line-height:1.2;margin:0 0 12px}
.hero p{opacity:.92;margin:0 auto 26px;max-width:540px}
.btn{display:inline-block;border:0;cursor:pointer;font:inherit;font-weight:700;padding:12px 24px;border-radius:12px;text-decoration:none;background:var(--acc);color:#1b1300}
.btn.o{background:transparent;color:#fff;border:1.5px solid rgba(255,255,255,.7);margin-left:8px}
.btn.p{background:var(--pri);color:#fff;width:100%}
.btn:disabled{opacity:.6}
.stats{max-width:1000px;margin:-34px auto 0;padding:0 16px;display:grid;grid-template-columns:repeat(auto-fit,minmax(130px,1fr));gap:12px;position:relative}
.stat{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:14px;text-align:center}
.stat b{display:block;font-size:1.5rem;color:var(--pri)}.stat span{font-size:.82rem;color:var(--muted)}
section{max-width:1000px;margin:auto;padding:46px 16px 10px}
h2{margin:0 0 6px;font-size:1.6rem}.sub{color:var(--muted);margin:0 0 22px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:14px}
.card{background:var(--card);border:1px solid var(--line);border-radius:16px;padding:18px}
.card h3{margin:0 0 6px;font-size:1.05rem}.muted{color:var(--muted);font-size:.92rem}
.tag{display:inline-block;background:rgba(29,78,216,.1);color:var(--pri);border-radius:99px;padding:2px 11px;font-size:.75rem;font-weight:600;margin-bottom:8px}
.av{width:56px;height:56px;border-radius:50%;background:linear-gradient(135deg,var(--pri2),var(--pri));color:#fff;display:grid;place-items:center;font-weight:800;font-size:1.3rem;margin-bottom:10px}
.ag{display:flex;gap:14px;align-items:center}
.date{min-width:62px;text-align:center;background:var(--pri);color:#fff;border-radius:12px;padding:8px 4px}
.date b{display:block;font-size:1.4rem;line-height:1.1}.date span{font-size:.72rem;text-transform:uppercase}
details{background:var(--card);border:1px solid var(--line);border-radius:12px;padding:12px 16px;margin-bottom:10px}
summary{cursor:pointer;font-weight:600}
.formbox{max-width:620px;margin:auto}
label{display:block;font-size:.88rem;font-weight:600;margin:12px 0 4px}
input,select,textarea{width:100%;padding:12px;border:1px solid var(--line);border-radius:10px;background:var(--bg);color:var(--text);font:inherit}
.hp{position:absolute;left:-9999px;height:0;overflow:hidden}
.msg{display:none;padding:12px 14px;border-radius:10px;margin-top:14px;font-size:.95rem}
.msg.ok{display:block;color:var(--ok);border:1px solid var(--ok)}
.msg.er{display:block;color:var(--err);border:1px solid var(--err)}
footer{margin-top:50px;background:#0f1f55;color:#cbd5f5;padding:28px 16px;text-align:center;font-size:.9rem}
</style>
</head>
<body>
<header><div class="nav">
<a class="logo" href="#beranda"><i>H</i><span id="brand"></span></a>
<button id="burger" aria-label="Menu">☰</button>
<nav class="menu" id="menu">
<a href="#tentang">Tentang</a><a href="#pengurus">Pengurus</a><a href="#proker">Program</a><a href="#agenda">Agenda</a><a href="#faq">FAQ</a><a class="cta" href="#daftar">Daftar</a>
</nav></div></header>
<div class="hero" id="beranda"><div class="in">
<div class="badge" id="periode"></div>
<h1 id="heroT"></h1><p id="heroD"></p>
<a class="btn" href="#daftar">Daftar Sekarang</a><a class="btn o" href="#tentang">Kenali Kami</a>
</div></div>
<div class="stats" id="stats"></div>
<section id="tentang"><h2>Tentang Kami</h2><p class="sub" id="about"></p>
<div class="grid"><div class="card"><div class="tag">Visi</div><p id="visi" style="margin:0"></p></div>
<div class="card"><div class="tag">Misi</div><ul id="misi" style="margin:0;padding-left:18px"></ul></div></div></section>
<section id="pengurus"><h2>Struktur Pengurus</h2><p class="sub">Orang-orang yang menggerakkan organisasi.</p><div class="grid" id="pengurusL"></div></section>
<section id="proker"><h2>Program Kerja</h2><p class="sub">Kegiatan unggulan kami.</p><div class="grid" id="prokerL"></div></section>
<section id="agenda"><h2>Agenda Kegiatan</h2><p class="sub">Catat tanggalnya dan ikut berpartisipasi.</p><div class="grid" id="agendaL"></div></section>
<section id="daftar"><div class="formbox"><h2>Pendaftaran Anggota</h2><p class="sub">Isi formulir berikut. Data akan diterima langsung oleh pengurus.</p>
<div class="card"><form id="f" novalidate>
<div class="hp"><label>Jangan diisi</label><input name="website" tabindex="-1" autocomplete="off"></div>
<label for="nama">Nama lengkap</label><input id="nama" name="nama" required>
<label for="nim">NIM</label><input id="nim" name="nim" required inputmode="numeric" pattern="[0-9]{6,20}">
<label for="kelas">Kelas / Program studi</label><input id="kelas" name="kelas" required placeholder="Contoh: PTI 2A">
<label for="email">Email</label><input id="email" name="email" type="email" required>
<label for="wa">Nomor WhatsApp</label><input id="wa" name="wa" type="tel" required inputmode="tel" placeholder="08xxxxxxxxxx">
<label for="divisi">Divisi pilihan</label><select id="divisi" name="divisi" required></select>
<label for="alasan">Alasan bergabung</label><textarea id="alasan" name="alasan" rows="3"></textarea>
<div style="margin-top:16px"><button class="btn p" id="send" type="submit">Kirim Pendaftaran</button></div>
<div class="msg" id="msg"></div>
</form></div></div></section>
<section id="faq"><h2>Pertanyaan Umum</h2><div id="faqL" style="margin-top:16px"></div></section>
<footer><div id="kontak"></div><p style="margin:10px 0 0;opacity:.8" id="cp"></p></footer>
<script>
var CONFIG={
 nama:"HIMADIKTI",
 periode:"Periode 2026/2027",
 tagline:"Wadah aspirasi, kolaborasi, dan pengembangan diri mahasiswa. Bergabunglah bersama kami.",
 tentang:"HIMADIKTI adalah organisasi kemahasiswaan yang mewadahi mahasiswa untuk berkembang dalam akademik, organisasi, dan pengabdian kepada masyarakat.",
 visi:"Menjadi himpunan yang aktif, inovatif, dan berintegritas.",
 misi:["Meningkatkan kualitas akademik dan keterampilan anggota.","Membangun solidaritas dan komunikasi antaranggota.","Menyelenggarakan kegiatan yang bermanfaat bagi kampus dan masyarakat."],
 statistik:[["50+","Anggota"],["4","Divisi"],["10+","Program Kerja"],["2026","Berdiri"]],
 pengurus:[["Ketua Umum","Nama Ketua"],["Wakil Ketua","Nama Wakil"],["Sekretaris","Nama Sekretaris"],["Bendahara","Nama Bendahara"],["Kadiv Akademik","Nama Kadiv"],["Kadiv Humas & Media","Nama Kadiv"]],
 proker:[["Akademik","Seminar & Workshop","Pelatihan keterampilan dan wawasan teknologi."],["Kaderisasi","Pengenalan Anggota Baru","Orientasi dan penerimaan anggota baru."],["Sosial","Bakti Sosial","Kegiatan pengabdian kepada masyarakat."],["Humas & Media","Media & Publikasi","Pengelolaan media sosial dan dokumentasi."]],
 agenda:[["2026-11-05","Rapat Kerja Pengurus","Ruang Rapat Kampus"],["2026-11-20","Workshop Web & Cloud","Laboratorium Komputer"],["2026-12-10","Bakti Sosial","Desa Binaan"]],
 divisi:["Akademik","Kaderisasi","Sosial","Humas & Media"],
 faq:[["Siapa yang boleh mendaftar?","Seluruh mahasiswa aktif yang tertarik berorganisasi."],["Apakah ada biaya pendaftaran?","Tidak ada. Pendaftaran gratis."],["Berapa lama proses seleksi?","Pengurus akan menghubungi lewat WhatsApp atau email setelah formulir diterima."]],
 kontak:"Sekretariat HIMADIKTI, Garut &middot; Email: himadikti@example.com &middot; Instagram: @himadikti",
 endpoint:"",
 whatsapp:""
};
var $=function(i){return document.getElementById(i)};
function esc(s){var d=document.createElement("div");d.textContent=s;return d.innerHTML}
function build(){
 var C=CONFIG;document.title=C.nama+" | Organisasi Mahasiswa";
 $("brand").textContent=C.nama;$("periode").textContent=C.periode;
 $("heroT").textContent="Selamat Datang di "+C.nama;$("heroD").textContent=C.tagline;
 $("about").textContent=C.tentang;$("visi").textContent=C.visi;
 $("misi").innerHTML=C.misi.map(function(m){return"<li>"+esc(m)+"</li>"}).join("");
 $("stats").innerHTML=C.statistik.map(function(s){return'<div class="stat"><b>'+esc(s[0])+"</b><span>"+esc(s[1])+"</span></div>"}).join("");
 $("pengurusL").innerHTML=C.pengurus.map(function(p){return'<div class="card"><div class="av">'+esc(p[1].charAt(0))+"</div><h3>"+esc(p[1])+'</h3><div class="muted">'+esc(p[0])+"</div></div>"}).join("");
 $("prokerL").innerHTML=C.proker.map(function(p){return'<div class="card"><span class="tag">'+esc(p[0])+"</span><h3>"+esc(p[1])+'</h3><div class="muted">'+esc(p[2])+"</div></div>"}).join("");
 $("agendaL").innerHTML=C.agenda.map(function(a){var d=new Date(a[0]+"T00:00:00");return'<div class="card ag"><div class="date"><b>'+d.getDate()+"</b><span>"+d.toLocaleDateString("id-ID",{month:"short"})+'</span></div><div><h3>'+esc(a[1])+'</h3><div class="muted">'+esc(a[2])+" &middot; "+d.getFullYear()+"</div></div></div>"}).join("");
 $("divisi").innerHTML='<option value="">Pilih divisi</option>'+C.divisi.map(function(d){return"<option>"+esc(d)+"</option>"}).join("");
 $("faqL").innerHTML=C.faq.map(function(q){return"<details><summary>"+esc(q[0])+'</summary><p class="muted" style="margin:8px 0 0">'+esc(q[1])+"</p></details>"}).join("");
 $("kontak").innerHTML=C.kontak;$("cp").textContent="© "+new Date().getFullYear()+" "+C.nama+". All rights reserved.";
}
function show(t,m){var e=$("msg");e.className="msg "+t;e.textContent=m}
$("burger").onclick=function(){$("menu").classList.toggle("open")};
$("menu").onclick=function(){$("menu").classList.remove("open")};
$("f").addEventListener("submit",function(ev){
 ev.preventDefault();var f=ev.target;
 if(f.website.value)return;
 if(!f.checkValidity()){f.reportValidity();return}
 var d={};new FormData(f).forEach(function(v,k){if(k!=="website")d[k]=String(v).trim()});
 try{if(localStorage.getItem("hmd_"+d.nim)){show("er","NIM ini sudah pernah mendaftar dari perangkat ini.");return}}catch(e){}
 var btn=$("send");btn.disabled=true;btn.textContent="Mengirim...";
 var done=function(){try{localStorage.setItem("hmd_"+d.nim,"1")}catch(e){}f.reset();show("ok","Pendaftaran berhasil dikirim. Pengurus akan menghubungi kamu segera.");btn.disabled=false;btn.textContent="Kirim Pendaftaran"};
 var fail=function(){show("er","Gagal mengirim. Periksa koneksi lalu coba lagi.");btn.disabled=false;btn.textContent="Kirim Pendaftaran"};
 var ep=CONFIG.endpoint;
 if(!ep){
  if(CONFIG.whatsapp){
   var t="Halo, saya ingin mendaftar "+CONFIG.nama+".%0ANama: "+encodeURIComponent(d.nama)+"%0ANIM: "+d.nim+"%0AKelas: "+encodeURIComponent(d.kelas)+"%0AEmail: "+encodeURIComponent(d.email)+"%0AWA: "+d.wa+"%0ADivisi: "+encodeURIComponent(d.divisi)+"%0AAlasan: "+encodeURIComponent(d.alasan||"-");
   window.open("https://wa.me/"+CONFIG.whatsapp+"?text="+t,"_blank");done();
  }else{show("er","Pendaftaran belum dihubungkan. Pengurus perlu mengisi endpoint.");btn.disabled=false;btn.textContent="Kirim Pendaftaran"}
  return;
 }
 if(ep.indexOf("script.google.com")>-1){
  fetch(ep,{method:"POST",mode:"no-cors",body:new URLSearchParams(d)}).then(done).catch(fail);
 }else{
  fetch(ep,{method:"POST",headers:{Accept:"application/json","Content-Type":"application/json"},body:JSON.stringify(d)}).then(function(r){r.ok?done():fail()}).catch(fail);
 }
});
build();
</script>
</body>
</html>

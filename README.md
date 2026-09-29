# THE-SHOW-MAN

🎭 JEU DE SPECTACLE IA
THE SHOW MAN
🎤
# 🎤 THE SHOW MAN

Jeu vidéo de comédie utilisant l'intelligence 

<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>THE SHOW MAN</title>

<style>
*{box-sizing:border-box}

body{
margin:0;
font-family:Arial,sans-serif;
color:white;
background:
radial-gradient(circle at 50% 0%,#35127a 0,#12001f 45%,#050008 100%);
min-height:100vh;
}

button{
font-family:inherit;
cursor:pointer;
}

.header{
position:sticky;
top:0;
z-index:20;
display:flex;
justify-content:space-between;
align-items:center;
padding:14px 20px;
background:rgba(5,0,10,.9);
border-bottom:1px solid #ffffff18;
backdrop-filter:blur(15px);
}

.logo{
font-size:25px;
font-weight:900;
color:#ffd83d;
text-shadow:0 0 20px #ff8500;
}

.stats{
display:flex;
gap:8px;
flex-wrap:wrap;
justify-content:center;
}

.stat{
background:#ffffff12;
border:1px solid #ffffff15;
padding:8px 12px;
border-radius:12px;
font-size:13px;
}

.container{
max-width:1150px;
margin:auto;
padding:20px;
}

.tabs{
display:flex;
gap:8px;
overflow-x:auto;
margin-bottom:20px;
}

.tab{
border:1px solid #ffffff18;
background:#ffffff0d;
color:white;
padding:11px 16px;
border-radius:12px;
white-space:nowrap;
}

.tab.active{
background:#7c3aed;
}

.page{display:none}
.page.active{display:block}

.hero{
text-align:center;
padding:15px;
}

.hero h1{
font-size:clamp(40px,8vw,75px);
margin:5px;
color:#ffd83d;
text-shadow:0 0 20px #ff7300,0 0 45px #7c3aed;
}

.hero p{
color:#ddd;
}

.panel{
background:#ffffff0b;
border:1px solid #ffffff16;
border-radius:22px;
padding:20px;
margin-bottom:20px;
box-shadow:0 10px 40px #0005;
}

.themes{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(130px,1fr));
gap:10px;
}

.theme{
padding:16px;
border-radius:15px;
background:#140c22;
border:2px solid transparent;
color:white;
font-size:14px;
}

.theme.selected{
border-color:#ffd83d;
background:#2a1744;
}

.stage{
height:440px;
position:relative;
overflow:hidden;
border-radius:25px;
border:2px solid #7c3aed;
background:
radial-gradient(circle at 50% 5%,#ffd83d55,transparent 20%),
linear-gradient(#26105d,#0b0011 65%);
box-shadow:0 0 50px #7c3aed66;
}

.stage:before{
content:"";
position:absolute;
width:360px;
height:360px;
left:50%;
top:-60px;
transform:translateX(-50%);
background:#ffffff0d;
border-radius:50%;
filter:blur(5px);
}

.character{
position:absolute;
left:50%;
top:85px;
transform:translateX(-50%);
z-index:2;
}

.head{
position:relative;
width:90px;
height:90px;
background:#efb47d;
border-radius:50%;
margin:auto;
}

.hair{
position:absolute;
top:-8px;
left:7px;
width:76px;
height:38px;
background:#111;
border-radius:50% 50% 25% 25%;
}

.eye{
position:absolute;
top:40px;
width:8px;
height:8px;
background:#111;
border-radius:50%;
}

.eye.left{left:25px}
.eye.right{right:25px}

.mouth{
position:absolute;
left:29px;
top:55px;
width:32px;
height:18px;
border-bottom:4px solid #111;
border-radius:50%;
}

.body{
width:120px;
height:150px;
margin-top:-2px;
background:#7c3aed;
border-radius:30px 30px 12px 12px;
}

.arm{
position:absolute;
top:105px;
width:25px;
height:105px;
background:#efb47d;
border-radius:20px;
}

.arm.left{
left:-25px;
transform:rotate(15deg);
}

.arm.right{
right:-25px;
transform:rotate(-25deg);
}

.micro{
position:absolute;
right:-52px;
top:105px;
width:18px;
height:100px;
background:#bbb;
border-radius:15px;
transform:rotate(-20deg);
}

.audience{
position:absolute;
bottom:12px;
width:100%;
text-align:center;
font-size:30px;
letter-spacing:4px;
z-index:4;
}

.dialogue{
min-height:130px;
margin-top:20px;
padding:20px;
background:#0008;
border-radius:15px;
font-size:18px;
line-height:1.7;
}

.showline{
color:#ffd83d;
font-weight:bold;
}

.publicline{
color:#86efac;
font-style:italic;
}

.controls{
display:flex;
flex-wrap:wrap;
gap:10px;
margin-top:15px;
}

.btn{
border:0;
color:white;
font-weight:bold;
padding:14px 20px;
border-radius:14px;
font-size:15px;
}

.ai{
background:linear-gradient(135deg,#7c3aed,#ec4899);
}

.play{
background:linear-gradient(135deg,#f59e0b,#ef4444);
}

.next{
background:#2563eb;
}

.btn:disabled{
opacity:.45;
cursor:not-allowed;
}

.message{
min-height:25px;
text-align:center;
margin-top:12px;
color:#ffd83d;
}

.result{
display:none;
text-align:center;
}

.score{
font-size:75px;
font-weight:900;
color:#ffd83d;
}

.stars{
font-size:32px;
}

.cards{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
gap:15px;
}

.card{
padding:20px;
border-radius:18px;
background:#ffffff0c;
border:1px solid #ffffff15;
}

.card h3{
margin-top:0;
}

.shop{
width:100%;
border:0;
border-radius:10px;
padding:11px;
background:#7c3aed;
color:white;
font-weight:bold;
}

.locked{
opacity:.45;
}

.levelbox{
margin-top:10px;
}

.progress{
height:10px;
background:#222;
border-radius:10px;
overflow:hidden;
}

.progressbar{
height:100%;
width:0;
background:linear-gradient(90deg,#7c3aed,#ec4899);
}

@media(max-width:600px){
.header{
flex-direction:column;
gap:10px;
}
.stage{
height:410px;
}
.audience{
font-size:23px;
}
}
</style>
</head>

<body>

<header class="header">

<div class="logo">
🎤 THE SHOW MAN
</div>

<div class="stats">

<div class="stat">
🪙 <span id="coins">100</span>
</div>

<div class="stat">
💎 <span id="gems">5</span>
</div>

<div class="stat">
⭐ Niveau <span id="level">1</span>
</div>

<div class="stat">
🔥 XP <span id="xp">0</span>
</div>

</div>

</header>

<main class="container">

<nav class="tabs">

<button class="tab active" onclick="page('show',this)">
🎤 Spectacle
</button>

<button class="tab" onclick="page('character',this)">
🧍 Personnage
</button>

<button class="tab" onclick="page('shop',this)">
🛍️ Boutique
</button>

<button class="tab" onclick="page('scenes',this)">
🎭 Scènes
</button>

<button class="tab" onclick="page('ranking',this)">
🏆 Classement
</button>

</nav>


<!-- SPECTACLE -->

<section id="show" class="page active">

<div class="hero">

<h1>THE SHOW MAN</h1>

<p>
Monte sur scène. Fais rire le public. Deviens une légende.
</p>

</div>


<div class="panel">

<h2>🎯 Choisis ton thème</h2>

<div class="themes">

<button class="theme selected"
onclick="theme(this,'Vie quotidienne')">
🏠<br>Vie quotidienne
</button>

<button class="theme"
onclick="theme(this,'Travail')">
💼<br>Travail
</button>

<button class="theme"
onclick="theme(this,'Technologie')">
🤖<br>Technologie
</button>

<button class="theme"
onclick="theme(this,'Voyage')">
✈️<br>Voyage
</button>

<button class="theme"
onclick="theme(this,'Famille')">
👨‍👩‍👧<br>Famille
</button>

</div>

</div>


<div class="stage">

<div class="character">

<div class="head">

<div class="hair"></div>

<div class="eye left"></div>
<div class="eye right"></div>

<div class="mouth"></div>

</div>

<div class="body"></div>

<div class="arm left"></div>
<div class="arm right"></div>

<div class="micro"></div>

</div>

<div class="audience">
👨‍🦱 👩 👨 👩‍🦰 👨‍🦳 👩‍🦱 👨 👩
</div>

</div>


<div class="panel">

<h2>🤖 Intelligence artificielle</h2>

<div id="dialogue" class="dialogue">

Ton spectacle va être créé ici.

<br><br>

Choisis un thème puis appuie sur
<strong>GÉNÉRER LE SPECTACLE</strong>.

</div>

<div class="controls">

<button class="btn ai"
onclick="generate()"
id="generate">

🤖 Générer le spectacle
</button>

<button class="btn next"
onclick="next()"
id="next"
disabled>

▶️ Réplique suivante

</button>

</div>

<div id="message" class="message"></div>

</div>


<div class="panel result" id="result">

<h2>🎉 Spectacle terminé !</h2>

<div class="score" id="score">
0/10
</div>

<div class="stars" id="stars">
⭐⭐⭐⭐⭐
</div>

<p>Note du public</p>

<p id="reward"></p>

<button class="btn play"
onclick="newShow()">

🎤 Nouveau spectacle

</button>

</div>

</section>


<!-- PERSONNAGE -->

<section id="character" class="page">

<div class="panel">

<h2>🧍 PERSONNAGE</h2>

<div class="cards">

<div class="card">
<h3>🎤 THE SHOW MAN</h3>
<p>Humoriste débutant.</p>
<p>⭐ Style : 10</p>
</div>

<div class="card">
<h3>😎 Star</h3>
<p>Débloqué niveau 5.</p>
<p>🔒</p>
</div>

<div class="card">
<h3>👑 Superstar</h3>
<p>Débloqué niveau 10.</p>
<p>🔒</p>
</div>

</div>

</div>

</section>


<!-- BOUTIQUE -->

<section id="shop" class="page">

<div class="panel">

<h2>🛍️ BOUTIQUE</h2>

<div class="cards">

<div class="card">

<h3>🎤 Micro doré</h3>

<p>Un micro de star.</p>

<button class="shop"
onclick="buy(100,'Micro doré')">

🪙 100

</button>

</div>


<div class="card">

<h3>🕶️ Lunettes VIP</h3>

<p>+10 style.</p>

<button class="shop"
onclick="buy(150,'Lunettes VIP')">

🪙 150

</button>

</div>


<div class="card">

<h3>👑 Costume STAR</h3>

<p>+25 style.</p>

<button class="shop"
onclick="buy(500,'Costume STAR')">

🪙 500

</button>

</div>

</div>

<div id="shopMessage"
class="message"></div>

</div>

</section>


<!-- SCENES -->

<section id="scenes" class="page">

<div class="panel">

<h2>🎭 SCÈNES</h2>

<div class="cards">

<div class="card">
<h3>🎙️ Petit Club</h3>
<p>50 spectateurs.</p>
<p>✅ Débloqué</p>
</div>

<div class="card">
<h3>🌃 Grande Ville</h3>
<p>500 spectateurs.</p>
<p id="city">🔒 Niveau 3</p>
</div>

<div class="card">
<h3>🏟️ Mega Arena</h3>
<p>10 000 spectateurs.</p>
<p>🔒 Niveau 10</p>
</div>

<div class="card">
<h3>🌍 World Stage</h3>
<p>100 000 spectateurs.</p>
<p>🔒 Niveau 20</p>
</div>

</div>

</div>

</section>


<!-- CLASSEMENT -->

<section id="ranking" class="page">

<div class="panel">

<h2>🏆 CLASSEMENT</h2>

<div class="cards">

<div class="card">
🥇 THE KING
<br>
<strong>9.8/10</strong>
</div>

<div class="card">
🥈 COMEDY STAR
<br>
<strong>9.6/10</strong>
</div>

<div class="card">
🥉 LOL MASTER
<br>
<strong>9.4/10</strong>
</div>

<div class="card">
🎤 TOI
<br>
<strong id="best">0/10</strong>
</div>

</div>

</div>

</section>

</main>


<script>

let selectedTheme="Vie quotidienne";

let lines=[];

let current=0;

let coins=100;

let gems=5;

let xp=0;

let level=1;

let bestScore=0;


/* NAVIGATION */

function page(name,button){

document.querySelectorAll(".page")
.forEach(x=>x.classList.remove("active"));

document.querySelectorAll(".tab")
.forEach(x=>x.classList.remove("active"));

document.getElementById(name)
.classList.add("active");

button.classList.add("active");

}


/* THEME */

function theme(button,name){

document.querySelectorAll(".theme")
.forEach(x=>x.classList.remove("selected"));

button.classList.add("selected");

selectedTheme=name;

document.getElementById("message")
.innerText="🎯 Thème : "+name;

}


/*
==================================================
MOTEUR DE DIALOGUE DU PROTOTYPE
==================================================
*/

const dialogues={

"Vie quotidienne":[

"SHOW: Vous avez remarqué que le réveil sonne toujours au moment où vous dormez le mieux ?",
"PUBLIC: 😂😂😂",
"SHOW: À 6h du matin, mon réveil ne me réveille pas… il me donne juste une occasion de le détester.",
"PUBLIC: 🤣👏",
"SHOW: Et quand je mets cinq alarmes, je ne me lève pas plus tôt. Je deviens juste spécialiste du bouton SNOOZE.",
"PUBLIC: 😂😂👏",
"SHOW: Maintenant mon téléphone me connaît tellement bien qu'il sait que la sixième alarme ne sert absolument à rien.",
"PUBLIC: 🤣🤣🤣",
"SHOW: Alors il arrête de sonner… par respect pour ma dignité.",
"PUBLIC: 😂👏🔥"

],

"Travail":[

"SHOW: Au travail, il y a toujours quelqu'un qui dit : « Petite réunion rapide ».",
"PUBLIC: 😂",
"SHOW: Quand quelqu'un dit ça, tu sais déjà que ton café va devenir froid.",
"PUBLIC: 🤣👏",
"SHOW: La réunion commence à 9h.",
"PUBLIC: 😐",
"SHOW: À 9h30, quelqu'un partage son écran.",
"PUBLIC: 😂😂",
"SHOW: À 10h, tout le monde cherche encore le bouton « quitter la réunion ».",
"PUBLIC: 🤣🤣🤣"

],

"Technologie":[

"SHOW: Aujourd'hui mon téléphone est plus intelligent que moi.",
"PUBLIC: 😂",
"SHOW: Il connaît mon visage, mon empreinte, ma position et même mon sommeil.",
"PUBLIC: 🤣",
"SHOW: Moi, par contre, je cherche encore où j'ai posé mes clés.",
"PUBLIC: 😂😂",
"SHOW: Le téléphone me dit : « Vous avez marché 8 000 pas aujourd'hui ».",
"PUBLIC: 👏😂",
"SHOW: Oui… parce que j'ai cherché mes clés pendant deux heures.",
"PUBLIC: 🤣🤣🤣🔥"

],

"Voyage":[

"SHOW: J'adore voyager. Le problème, c'est ma valise.",
"PUBLIC: 😂",
"SHOW: Je pars trois jours avec suffisamment de vêtements pour survivre trois mois.",
"PUBLIC: 🤣",
"SHOW: Et je prends toujours quelque chose que je ne porterai jamais.",
"PUBLIC: 😂😂",
"SHOW: La dernière fois, j'avais pris une veste pour la neige.",
"PUBLIC: 😆",
"SHOW: Je suis parti dans une ville où il faisait 35 degrés.",
"PUBLIC: 🤣🤣",
"SHOW: Ma veste a passé de meilleures vacances que moi.",
"PUBLIC: 😂👏🔥"

],

"Famille":[

"SHOW: Dans une famille, il y a toujours quelqu'un qui sait tout.",
"PUBLIC: 😂",
"SHOW: Même quand personne ne lui demande son avis.",
"PUBLIC: 🤣",
"SHOW: Tu dis : « Je vais acheter du pain ».",
"PUBLIC: 😂",
"SHOW: Et quelqu'un répond : « Prends aussi du lait, des œufs et regarde si le magasin est ouvert. »",
"PUBLIC: 🤣🤣",
"SHOW: Je voulais du pain… je suis revenu avec un plan stratégique pour la semaine.",
"PUBLIC: 😂😂😂🔥"

]

};


/* GENERATION */

function generate(){

document.getElementById("generate").disabled=true;

document.getElementById("next").disabled=false;

document.getElementById("result").style.display="none";

lines=dialogues[selectedTheme] || dialogues["Vie quotidienne"];

current=0;

document.getElementById("dialogue").innerHTML=
"🎬 <strong>Le spectacle est prêt !</strong><br><br>"+
"Appuie sur <strong>Réplique suivante</strong>.";

document.getElementById("message").innerText=
"🎤 THE SHOW MAN entre sur scène.";

}


/* REPLIQUE */

function next(){

if(current>=lines.length){

finish();

return;

}

let line=lines[current];

if(line.startsWith("SHOW:")){

document.getElementById("dialogue").innerHTML=
'<span class="showline">'+
line+
'</span>';

document.getElementById("message").innerText=
"🎤 THE SHOW MAN parle...";

}

else{

document.getElementById("dialogue").innerHTML=
'<span class="publicline">'+
line+
'</span>';

document.getElementById("message").innerText=
"😂 Le public réagit !";

}

current++;

}


/* FIN */

function finish(){

let score=
Math.floor(Math.random()*4)+7;

let reward=score*10;

let gained=score*5;

coins+=reward;

xp+=gained;

if(score>bestScore){

bestScore=score;

}

levelUp();

document.getElementById("score").innerText=
score+"/10";

document.getElementById("stars").innerText=
"⭐".repeat(Math.round(score/2));

document.getElementById("reward").innerText=
"🎁 Récompense : +"+
reward+
" 🪙 | +"+
gained+
" XP";

document.getElementById("best").innerText=
bestScore+"/10";

document.getElementById("result").style.display=
"block";

document.getElementById("next").disabled=true;

document.getElementById("generate").disabled=false;

update();

}


/* NOUVEAU */

function newShow(){

document.getElementById("result").style.display="none";

document.getElementById("dialogue").innerHTML=
"Choisis ton thème et lance un nouveau spectacle.";

document.getElementById("message").innerText="";

current=0;

lines=[];

}


/* NIVEAU */

function levelUp(){

while(xp>=level*100){

xp-=level*100;

level++;

document.getElementById("message").innerText=
"🎉 NOUVEAU NIVEAU : "+level+" !";

}

if(level>=3){

document.getElementById("city").innerText=
"⭐ Débloquée";

}

}


/* ACHAT */

function buy(price,item){

if(coins<price){

document.getElementById("shopMessage").innerText=
"❌ Pas assez de pièces.";

return;

}

coins-=price;

document.getElementById("shopMessage").innerText=
"✅ "+item+" acheté !";

update();

}


/* STATS */

function update(){

document.getElementById("coins").innerText=coins;

document.getElementById("gems").innerText=gems;

document.getElementById("xp").innerText=xp;

document.getElementById("level").innerText=level;

}

update();

</script>

</body>
</html>






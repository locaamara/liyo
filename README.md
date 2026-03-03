#liyo

<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TonPseudo</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;}

body{
    font-family:Arial, sans-serif;
    background:url('TON_GIF_ICI.gif') no-repeat center center fixed;
    background-size:cover;
    height:100vh;
    overflow:hidden;
    color:white;
}

/* 🎥 Intro fade */
body{
    animation:fadeIn 2s ease forwards;
}
@keyframes fadeIn{
    from{opacity:0;}
    to{opacity:1;}
}

/* 🎤 Spotlight */
.spotlight{
    position:absolute;
    top:-200px;
    left:50%;
    transform:translateX(-50%);
    width:700px;
    height:700px;
    background:radial-gradient(circle, rgba(140,0,255,0.4) 0%, rgba(0,0,0,0) 70%);
    animation:moveLight 6s infinite alternate ease-in-out;
    pointer-events:none;
}
@keyframes moveLight{
    from{transform:translateX(-50%) rotate(-15deg);}
    to{transform:translateX(-50%) rotate(15deg);}
}

/* ✨ Background stars */
.stars{
    position:absolute;
    width:100%;
    height:100%;
    background-image:radial-gradient(white 1px, transparent 1px);
    background-size:50px 50px;
    opacity:0.2;
    animation:moveStars 80s linear infinite;
}
@keyframes moveStars{
    from{background-position:0 0;}
    to{background-position:2000px 2000px;}
}

.overlay{
    background:rgba(0,0,0,0.65);
    height:100vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    position:relative;
    z-index:2;
}

/* ⭐ Nom avec étoiles internes */
.neon{
    font-size:80px;
    font-weight:bold;
    text-transform:uppercase;
    background:linear-gradient(90deg,#00ccff,#9400ff,#00ccff);
    background-size:200%;
    -webkit-background-clip:text;
    -webkit-text-fill-color:transparent;
    animation:shine 3s linear infinite;
    position:relative;
}

.neon::after{
    content:"★";
    position:absolute;
    right:-30px;
    top:-10px;
    font-size:30px;
    color:white;
    text-shadow:0 0 10px #00ccff,0 0 20px #9400ff;
    animation:starBlink 1.5s infinite alternate;
}

@keyframes shine{
    from{background-position:0%;}
    to{background-position:200%;}
}

@keyframes starBlink{
    from{opacity:0.4;}
    to{opacity:1;}
}

/* 🌌 Boutons */
.btn{
    position:relative;
    width:260px;
    margin:12px;
    padding:14px;
    border-radius:16px;
    background:rgba(255,255,255,0.08);
    border:1px solid rgba(255,255,255,0.2);
    backdrop-filter:blur(15px);
    color:white;
    text-decoration:none;
    font-size:18px;
    transition:0.4s;
    animation:pulseBeat 3s infinite;
}

/* Pulsation douce */
@keyframes pulseBeat{
    0%,100%{transform:scale(1);}
    50%{transform:scale(1.03);}
}

/* Aura magique hover */
.btn::before{
    content:"";
    position:absolute;
    top:-5px;left:-5px;right:-5px;bottom:-5px;
    border-radius:18px;
    background:linear-gradient(45deg,#4d4dff,#9400ff,#00ccff);
    opacity:0;
    filter:blur(20px);
    z-index:-1;
    transition:0.4s;
}

.btn:hover::before{
    opacity:1;
}

.btn:hover{
    transform:scale(1.1);
    box-shadow:0 0 25px #8a2be2,0 0 50px #00ccff;
}

/* 👥 Pseudos */
.users{
    position:absolute;
    bottom:25px;
    text-align:center;
    width:100%;
}

.user-link{
    margin:0 15px;
    font-weight:bold;
    text-decoration:none;
    color:white;
    transition:0.3s;
}

.user-link:hover{
    color:#00ccff;
    text-shadow:0 0 10px #9400ff;
}

/* 💫 Mouse particles */
.particle{
    position:absolute;
    width:6px;
    height:6px;
    background:white;
    border-radius:50%;
    pointer-events:none;
    animation:fadeParticle 1s forwards;
}

@keyframes fadeParticle{
    from{opacity:1;}
    to{opacity:0;transform:translateY(-20px);}
}
</style>
</head>

<body>

<div class="spotlight"></div>
<div class="stars"></div>

<audio autoplay loop>
<source src="TON_MUSIQUE.mp3" type="audio/mpeg">
</audio>

<div class="overlay">
<div class="neon">TONPSEUDO</div>

<a href="LIEN_DISCORD" class="btn" target="_blank">Discord</a>
<a href="LIEN_INSTAGRAM" class="btn" target="_blank">Instagram</a>
</div>

<div class="users">
<a href="LIEN_DISCORD_LOCAAMARA" class="user-link" target="_blank">locaamara</a>
<a href="LIEN_DISCORD_AUTRE" class="user-link" target="_blank">autrepseudo</a>
</div>

<script>
document.addEventListener("mousemove", function(e){
    let particle = document.createElement("div");
    particle.className = "particle";
    particle.style.left = e.pageX + "px";
    particle.style.top = e.pageY + "px";
    document.body.appendChild(particle);
    setTimeout(()=>{ particle.remove(); }, 1000);
});
</script>

</body>
</html>

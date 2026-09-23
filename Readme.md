<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Ayush Verma — Colourful 3D Portfolio</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">

<style>

:root{
    --bg:#05020d;
    --card:rgba(255,255,255,.06);
    --text:#f8fbff;
    --muted:#aaa9ba;

    --pink:#ff2bd6;
    --cyan:#21e6ff;
    --purple:#7c4dff;
    --lime:#a8ff3e;
    --orange:#ff8a1f;
    --blue:#4f7cff;
}

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:"Inter",sans-serif;
    color:var(--text);
    background:
        radial-gradient(circle at 10% 15%,rgba(255,43,214,.16),transparent 26%),
        radial-gradient(circle at 90% 20%,rgba(33,230,255,.15),transparent 28%),
        radial-gradient(circle at 50% 90%,rgba(124,77,255,.16),transparent 30%),
        #05020d;
    overflow-x:hidden;
}

/* Background */

body::before{
    content:"";
    position:fixed;
    inset:-20%;
    pointer-events:none;
    z-index:-5;

    background:
        conic-gradient(
            from 90deg,
            rgba(255,43,214,.10),
            rgba(33,230,255,.08),
            rgba(168,255,62,.07),
            rgba(124,77,255,.10),
            rgba(255,43,214,.10)
        );

    filter:blur(70px);

    animation:aurora 14s ease-in-out infinite alternate;
}

@keyframes aurora{

    from{
        transform:rotate(0deg) scale(1);
    }

    to{
        transform:rotate(12deg) scale(1.12);
    }
}

/* Floating Orbs */

.color-orb{
    position:fixed;
    border-radius:50%;
    pointer-events:none;
    z-index:-2;
    mix-blend-mode:screen;
    filter:blur(1px);
    opacity:.5;

    animation:floatOrb 10s ease-in-out infinite;
}

.orb1{
    width:90px;
    height:90px;
    background:var(--pink);
    left:6%;
    top:32%;
    box-shadow:0 0 70px var(--pink);
}

.orb2{
    width:70px;
    height:70px;
    background:var(--cyan);
    right:7%;
    top:58%;
    box-shadow:0 0 70px var(--cyan);
    animation-delay:-3s;
}

.orb3{
    width:55px;
    height:55px;
    background:var(--lime);
    left:45%;
    top:12%;
    box-shadow:0 0 60px var(--lime);
    animation-delay:-6s;
}

@keyframes floatOrb{

    0%,100%{
        transform:translate3d(0,0,0) scale(1);
    }

    50%{
        transform:translate3d(35px,-45px,0) scale(1.25);
    }
}

/* Navigation */

nav{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    z-index:100;

    display:flex;
    justify-content:space-between;
    align-items:center;

    padding:20px 7%;

    background:rgba(5,2,13,.72);
    border-bottom:1px solid rgba(255,255,255,.1);

    backdrop-filter:blur(18px);
}

.logo{
    font-family:"Space Grotesk";
    font-size:24px;
    font-weight:800;

    background:linear-gradient(
        90deg,
        var(--cyan),
        var(--pink)
    );

    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
}

nav ul{
    display:flex;
    gap:28px;
    list-style:none;
}

nav a{
    color:white;
    text-decoration:none;
    font-size:14px;
    transition:.3s;
}

nav a:hover{
    color:var(--cyan);
    text-shadow:0 0 15px var(--cyan);
}

/* Hero */

.hero{
    min-height:100vh;

    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;

    text-align:center;

    padding:120px 20px 70px;

    position:relative;
}

.hero::before{

    content:"";

    position:absolute;

    width:420px;
    height:420px;

    border-radius:50%;

    left:50%;
    top:45%;

    transform:translate(-50%,-50%);

    background:
        conic-gradient(
            var(--pink),
            var(--purple),
            var(--cyan),
            var(--lime),
            var(--orange),
            var(--pink)
        );

    filter:blur(55px);

    opacity:.22;

    animation:spinGlow 12s linear infinite;

    z-index:-1;
}

@keyframes spinGlow{

    to{
        transform:translate(-50%,-50%) rotate(360deg);
    }
}

.eyebrow{

    color:var(--cyan);

    letter-spacing:4px;

    font-size:13px;
    font-weight:700;

    margin-bottom:20px;

    text-shadow:
        0 0 18px rgba(33,230,255,.65);
}

.hero h1{

    font-family:"Space Grotesk";

    font-size:clamp(60px,12vw,150px);

    line-height:.9;

    letter-spacing:-6px;

    margin-bottom:25px;

    background:
        linear-gradient(
            90deg,
            var(--cyan),
            #fff,
            var(--pink),
            var(--purple),
            var(--lime)
        );

    background-size:300% 100%;

    -webkit-background-clip:text;
    background-clip:text;

    color:transparent;

    animation:gradientMove 6s ease infinite;

    text-shadow:
        0 0 40px rgba(124,77,255,.25);
}

@keyframes gradientMove{

    0%,100%{
        background-position:0%;
    }

    50%{
        background-position:100%;
    }
}

.hero h2{

    font-size:22px;
    color:#ddd;

    margin-bottom:18px;
}

.hero p{

    max-width:650px;

    color:var(--muted);

    line-height:1.8;

    margin-bottom:30px;
}

/* Buttons */

.buttons{

    display:flex;
    gap:15px;

    flex-wrap:wrap;

    justify-content:center;
}

.btn{

    display:inline-block;

    padding:14px 25px;

    border-radius:50px;

    text-decoration:none;

    color:white;

    border:1px solid rgba(255,255,255,.18);

    background:
        linear-gradient(
            135deg,
            rgba(255,43,214,.18),
            rgba(33,230,255,.14)
        );

    box-shadow:
        0 0 24px rgba(124,77,255,.14),
        inset 0 0 20px rgba(255,255,255,.03);

    transition:.35s ease;
}

.btn:hover{

    transform:
        translateY(-5px)
        scale(1.04);

    border-color:var(--cyan);

    box-shadow:
        0 0 28px rgba(33,230,255,.28),
        0 0 50px rgba(255,43,214,.18);
}

/* Sections */

section{

    max-width:1200px;

    margin:auto;

    padding:100px 7%;
}

.section-label{

    color:var(--pink);

    letter-spacing:3px;

    font-size:13px;

    font-weight:700;

    margin-bottom:12px;

    text-shadow:
        0 0 18px rgba(255,43,214,.55);
}

section h2{

    font-family:"Space Grotesk";

    font-size:48px;

    margin-bottom:40px;

    text-shadow:
        0 0 25px rgba(124,77,255,.20);
}

/* Cards */

.grid{

    display:grid;

    grid-template-columns:
        repeat(auto-fit,minmax(260px,1fr));

    gap:25px;
}

.card{

    position:relative;

    overflow:hidden;

    padding:30px;

    min-height:220px;

    border-radius:24px;

    background:
        linear-gradient(
            145deg,
            rgba(255,255,255,.075),
            rgba(255,255,255,.025)
        );

    border:1px solid rgba(255,255,255,.12);

    box-shadow:
        0 20px 60px rgba(0,0,0,.35),
        inset 0 1px rgba(255,255,255,.08);

    transition:
        transform .4s ease,
        border .4s ease,
        box-shadow .4s ease;

    transform-style:preserve-3d;
}

.card::before{

    content:"";

    position:absolute;

    width:180px;
    height:180px;

    border-radius:50%;

    top:-90px;
    right:-70px;

    background:
        radial-gradient(
            circle,
            var(--cyan),
            transparent 68%
        );

    opacity:.18;

    filter:blur(8px);

    transition:.5s;
}

.card:hover::before{

    transform:scale(1.7);

    opacity:.30;
}

.card:nth-child(3n+1){
    --accent:var(--cyan);
}

.card:nth-child(3n+2){
    --accent:var(--pink);
}

.card:nth-child(3n+3){
    --accent:var(--lime);
}

.card:hover{

    transform:
        perspective(900px)
        rotateX(5deg)
        rotateY(-5deg)
        translateY(-10px);

    border-color:var(--accent);

    box-shadow:
        0 25px 70px rgba(0,0,0,.45),
        0 0 30px rgba(33,230,255,.15);
}

.card h3{

    font-family:"Space Grotesk";

    font-size:25px;

    margin-bottom:15px;

    color:white;
}

.card p{

    color:var(--muted);

    line-height:1.7;
}

/* Tech Tags */

.tags{

    display:flex;

    flex-wrap:wrap;

    gap:10px;

    margin-top:20px;
}

.tag{

    padding:9px 14px;

    border-radius:50px;

    font-size:13px;

    border:1px solid rgba(255,255,255,.16);

    background:
        linear-gradient(
            90deg,
            rgba(255,43,214,.12),
            rgba(33,230,255,.12)
        );

    transition:.3s;
}

.tag:hover{

    transform:translateY(-3px) scale(1.05);

    border-color:var(--cyan);

    box-shadow:
        0 0 18px rgba(33,230,255,.25);
}

/* Timeline */

.timeline{

    position:relative;

    max-width:800px;

    margin:auto;
}

.timeline::before{

    content:"";

    position:absolute;

    left:15px;
    top:0;
    bottom:0;

    width:2px;

    background:
        linear-gradient(
            var(--pink),
            var(--purple),
            var(--cyan),
            var(--lime)
        );
}

.timeline-item{

    position:relative;

    padding-left:55px;

    margin-bottom:40px;
}

.dot{

    position:absolute;

    left:5px;
    top:5px;

    width:22px;
    height:22px;

    border-radius:50%;

    background:
        radial-gradient(
            circle,
            var(--cyan),
            var(--purple)
        );

    box-shadow:
        0 0 20px rgba(33,230,255,.7),
        0 0 35px rgba(255,43,214,.35);
}

.timeline-item h3{

    margin-bottom:8px;

    font-size:22px;
}

.timeline-item p{

    color:var(--muted);

    line-height:1.7;
}

/* Stats */

.stats{

    display:grid;

    grid-template-columns:
        repeat(auto-fit,minmax(180px,1fr));

    gap:20px;

    margin-top:30px;
}

.stat{

    padding:25px;

    text-align:center;

    border-radius:20px;

    background:rgba(255,255,255,.04);

    border:1px solid rgba(255,255,255,.1);
}

.stat strong{

    display:block;

    font-size:36px;

    font-family:"Space Grotesk";

    background:
        linear-gradient(
            90deg,
            var(--cyan),
            var(--pink)
        );

    -webkit-background-clip:text;
    background-clip:text;

    color:transparent;
}

.stat span{

    color:var(--muted);

    font-size:13px;
}

/* Quote */

.quote{

    text-align:center;

    padding:80px 20px;

    font-family:"Space Grotesk";

    font-size:clamp(28px,5vw,55px);

    line-height:1.2;

    background:
        linear-gradient(
            90deg,
            var(--cyan),
            var(--pink),
            var(--purple),
            var(--lime)
        );

    -webkit-background-clip:text;

    background-clip:text;

    color:transparent;
}

/* Footer */

footer{

    text-align:center;

    padding:50px 20px;

    color:var(--muted);

    border-top:
        1px solid rgba(255,255,255,.1);
}

footer span{

    color:var(--pink);

    text-shadow:
        0 0 12px var(--pink);
}

/* Mobile */

@media(max-width:700px){

    nav{
        padding:16px 20px;
    }

    nav ul{
        display:none;
    }

    .hero h1{
        font-size:65px;
        letter-spacing:-3px;
    }

    section{
        padding:70px 20px;
    }

    section h2{
        font-size:38px;
    }

}

@media(prefers-reduced-motion:reduce){

    *,
    *::before,
    *::after{
        animation-duration:.01ms !important;
        animation-iteration-count:1 !important;
        scroll-behavior:auto !important;
    }

}

</style>
</head>

<body>

<div class="color-orb orb1"></div>
<div class="color-orb orb2"></div>
<div class="color-orb orb3"></div>


<!-- NAVIGATION -->

<nav>

    <div class="logo">
        AYUSH.
    </div>

    <ul>

        <li>
            <a href="#about">About</a>
        </li>

        <li>
            <a href="#skills">Skills</a>
        </li>

        <li>
            <a href="#projects">Projects</a>
        </li>

        <li>
            <a href="#journey">Journey</a>
        </li>

        <li>
            <a href="#contact">Contact</a>
        </li>

    </ul>

</nav>


<!-- HERO -->

<header class="hero">

    <div class="eyebrow">
        DATA SCIENCE • MACHINE LEARNING • PYTHON
    </div>

    <h1>
        AYUSH<br>VERMA
    </h1>

    <h2>
        BCA Student · Data Science · Machine Learning
    </h2>

    <p>
        Building with Python, Data & Machine Learning.
        Exploring data, creating ML projects and continuously
        improving my technical skills.
    </p>

    <div class="buttons">

        <a
            class="btn"
            href="https://github.com/aayu258"
            target="_blank"
        >
            💻 GitHub
        </a>

        <a
            class="btn"
            href="https://linkedin.com/in/ayush-verma-8b5a3034a"
            target="_blank"
        >
            🔗 LinkedIn
        </a>

        <a
            class="btn"
            href="#projects"
        >
            🚀 Explore Projects
        </a>

    </div>

</header>


<!-- ABOUT -->

<section id="about">

    <div class="section-label">
        01 — ABOUT ME
    </div>

    <h2>
        Who I Am
    </h2>

    <div class="grid">

        <div class="card">

            <h3>
                👨‍💻 BCA Student
            </h3>

            <p>
                I am a BCA student interested in Data Science,
                Data Analytics and Machine Learning.
                I enjoy learning programming and building
                practical projects.
            </p>

        </div>


        <div class="card">

            <h3>
                🧠 Data Enthusiast
            </h3>

            <p>
                Currently learning Python, NumPy, Pandas,
                Matplotlib, Seaborn, Statistics, SQL and
                Machine Learning.
            </p>

        </div>


        <div class="card">

            <h3>
                🚀 Future Goal
            </h3>

            <p>
                My goal is to become a Data Scientist and
                build real-world Machine Learning applications
                that solve practical problems.
            </p>

        </div>

    </div>

</section>


<!-- SKILLS -->

<section id="skills">

    <div class="section-label">
        02 — TECH STACK
    </div>

    <h2>
        My Toolkit
    </h2>

    <div class="grid">

        <div class="card">

            <h3>
                🐍 Python
            </h3>

            <p>
                Programming, Object-Oriented Programming
                and project development.
            </p>

            <div class="tags">

                <span class="tag">Python</span>
                <span class="tag">OOP</span>

            </div>

        </div>


        <div class="card">

            <h3>
                📊 Data Analysis
            </h3>

            <p>
                Working with datasets, cleaning data and
                extracting useful insights.
            </p>

            <div class="tags">

                <span class="tag">NumPy</span>
                <span class="tag">Pandas</span>

            </div>

        </div>


        <div class="card">

            <h3>
                📈 Visualization
            </h3>

            <p>
                Creating charts and visual representations
                to understand data.
            </p>

            <div class="tags">

                <span class="tag">Matplotlib</span>
                <span class="tag">Seaborn</span>

            </div>

        </div>


        <div class="card">

            <h3>
                🤖 Machine Learning
            </h3>

            <p>
                Learning ML algorithms, model training,
                prediction and evaluation.
            </p>

            <div class="tags">

                <span class="tag">ML</span>
                <span class="tag">EDA</span>
                <span class="tag">Prediction</span>

            </div>

        </div>

    </div>

</section>


<!-- PROJECTS -->

<section id="projects">

    <div class="section-label">
        03 — PROJECTS
    </div>

    <h2>
        Things I've Built
    </h2>

    <div class="grid">


        <div class="card">

            <h3>
                🚗 Car Price Prediction
            </h3>

            <p>
                A Machine Learning project that focuses on
                predicting car prices using data and ML
                techniques.
            </p>

            <div class="tags">

                <span class="tag">Python</span>
                <span class="tag">Pandas</span>
                <span class="tag">Machine Learning</span>

            </div>

        </div>


        <div class="card">

            <h3>
                🎓 Admission Process Management
            </h3>

            <p>
                An individual Python project developed using
                Object-Oriented Programming concepts to
                manage admission-related information.
            </p>

            <div class="tags">

                <span class="tag">Python</span>
                <span class="tag">OOP</span>
                <span class="tag">Management System</span>

            </div>

        </div>


        <div class="card">

            <h3>
                💻 Student Portal
            </h3>

            <p>
                A project concept focused on managing
                student information and improving basic
                data management workflows.
            </p>

            <div class="tags">

                <span class="tag">Python</span>
                <span class="tag">Data</span>

            </div>

        </div>

    </div>

</section>


<!-- JOURNEY -->

<section id="journey">

    <div class="section-label">
        04 — LEARNING JOURNEY
    </div>

    <h2>
        My Roadmap
    </h2>


    <div class="timeline">


        <div class="timeline-item">

            <div class="dot"></div>

            <h3>
                Python
            </h3>

            <p>
                Programming fundamentals, functions,
                OOP and problem solving.
            </p>

        </div>


        <div class="timeline-item">

            <div class="dot"></div>

            <h3>
                NumPy & Pandas
            </h3>

            <p>
                Data manipulation, arrays, DataFrames
                and dataset handling.
            </p>

        </div>


        <div class="timeline-item">

            <div class="dot"></div>

            <h3>
                Data Visualization
            </h3>

            <p>
                Learning Matplotlib and Seaborn to
                understand patterns visually.
            </p>

        </div>


        <div class="timeline-item">

            <div class="dot"></div>

            <h3>
                Statistics & SQL
            </h3>

            <p>
                Building strong foundations in statistics,
                databases and data querying.
            </p>

        </div>


        <div class="timeline-item">

            <div class="dot"></div>

            <h3>
                Machine Learning
            </h3>

            <p>
                Learning regression, classification,
                model evaluation and prediction.
            </p>

        </div>


        <div class="timeline-item">

            <div class="dot"></div>

            <h3>
                Deep Learning & MLOps
            </h3>

            <p>
                Future learning goals include Deep Learning,
                deployment and MLOps.
            </p>

        </div>

    </div>

</section>


<!-- GOALS -->

<section>

    <div class="section-label">
        05 — GOALS
    </div>

    <h2>
        Where I'm Going
    </h2>


    <div class="stats">

        <div class="stat">

            <strong>
                01
            </strong>

            <span>
                Become Data Scientist
            </span>

        </div>


        <div class="stat">

            <strong>
                02
            </strong>

            <span>
                Build Real ML Projects
            </span>

        </div>


        <div class="stat">

            <strong>
                03
            </strong>

            <span>
                Learn Deep Learning
            </span>

        </div>


        <div class="stat">

            <strong>
                04
            </strong>

            <span>
                Learn Deployment & MLOps
            </span>

        </div>

    </div>

</section>


<!-- QUOTE -->

<div class="quote">

    “Learn. Build. Fail.
    Improve. Repeat. 🚀”

</div>


<!-- CONTACT -->

<section id="contact">

    <div class="section-label">
        06 — CONTACT
    </div>

    <h2>
        Let's Connect
    </h2>


    <div class="card">

        <h3>
            Have an idea?
        </h3>

        <p>
            I'm always interested in learning,
            building projects and connecting with
            people interested in technology and
            Data Science.
        </p>

        <br>

        <div class="buttons">

            <a
                class="btn"
                href="mailto:aaayushaaavermaaa258@gmail.com"
            >
                📧 Email Me
            </a>

            <a
                class="btn"
                href="https://github.com/aayu258"
                target="_blank"
            >
                GitHub
            </a>

            <a
                class="btn"
                href="https://linkedin.com/in/ayush-verma-8b5a3034a"
                target="_blank"
            >
                LinkedIn
            </a>

        </div>

    </div>

</section>


<!-- FOOTER -->

<footer>

    <p>
        Designed & Built by
        <span>
            Ayush Verma
        </span>
        © 2026
    </p>

</footer>


<script>

/* 3D Mouse Effect */

const cards = document.querySelectorAll(".card");

cards.forEach(card => {

    card.addEventListener("mousemove", function(e){

        const rect =
            card.getBoundingClientRect();

        const x =
            e.clientX - rect.left;

        const y =
            e.clientY - rect.top;

        const centerX =
            rect.width / 2;

        const centerY =
            rect.height / 2;

        const rotateX =
            ((y - centerY) / centerY) * -5;

        const rotateY =
            ((x - centerX) / centerX) * 5;

        card.style.transform =
            `perspective(900px)
             rotateX(${rotateX}deg)
             rotateY(${rotateY}deg)
             translateY(-10px)`;

    });


    card.addEventListener("mouseleave", function(){

        card.style.transform =
            "perspective(900px) rotateX(0deg) rotateY(0deg) translateY(0)";

    });

});


/* Typing Effect */

const roles = [

    "Python Developer",
    "Data Science Learner",
    "Machine Learning Enthusiast",
    "Future Data Scientist"

];

let roleIndex = 0;
let charIndex = 0;

const heroText =
    document.querySelector(".hero h2");

function typeEffect(){

    const role =
        roles[roleIndex];

    heroText.textContent =
        role.substring(0,charIndex);

    charIndex++;

    if(charIndex > role.length){

        setTimeout(() => {

            charIndex = 0;

            roleIndex =
                (roleIndex + 1) % roles.length;

        },1200);

    }

    setTimeout(typeEffect,90);

}

setTimeout(typeEffect,1500);


/* Scroll Reveal */

const observer =
    new IntersectionObserver(
        entries => {

            entries.forEach(entry => {

                if(entry.isIntersecting){

                    entry.target.style.opacity = "1";

                    entry.target.style.transform =
                        "translateY(0)";

                }

            });

        },
        {
            threshold:.12
        }
    );


document
    .querySelectorAll(
        "section .card, .timeline-item, .stat"
    )
    .forEach(el => {

        el.style.opacity = "0";

        el.style.transform =
            "translateY(30px)";

        el.style.transition =
            "opacity .7s ease, transform .7s ease";

        observer.observe(el);

    });

</script>

</body>
</html>

# SonjaLettersGarden
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sonja Letters Garden 🌸</title>
<!-- Whimsical pixel font to embrace the Minecraft & Miffy aesthetic -->
<link href="https://googleapis.com" rel="stylesheet">
<style>
:root {
--baby-pink: #FFD1DC;
--pastel-pink-dark: #FFA6BC;
--sage-green: #2E5A44; /* Darkened slightly to guarantee AAA text readability on pink */
--sage-light: #527E67;
--minecraft-container: #FFF0F3;
}

* {
box-sizing: border-box;
margin: 0;
padding: 0;
}

body {
font-family: 'Quicksand', sans-serif;
background-color: var(--baby-pink);
color: var(--sage-green);
min-height: 100vh;
display: flex;
justify-content: center;
align-items: center;
overflow-x: hidden;
position: relative;
}

/* --- Minecraft Background Pixels & Whimsy Elements --- */
.bg-decorations {
position: absolute;
width: 100%;
height: 100%;
top: 0;
left: 0;
pointer-events: none;
z-index: 1;
}

/* Pixel Minecraft Stars */
.mc-star {
position: absolute;
width: 12px;
height: 12px;
background: var(--sage-light);
opacity: 0.3;
box-shadow: 0 12px var(--sage-light), 12px 0 var(--sage-light), -12px 0 var(--sage-light), 0 -12px var(--sage-light);
animation: float 6s infinite ease-in-out;
}

@keyframes float {
0%, 100% { transform: translateY(0px) rotate(0deg); }
50% { transform: translateY(-20px) rotate(15deg); }
}

/* --- CSS Miffy Pixel Art Component --- /
.miffy-sprite {
width: 32px;
height: 48px;
display: inline-block;
position: relative;
transform: scale(1.5);
margin: 10px;
}
/ Pure CSS generation mimicking Miffy pixel badges /
.miffy-sprite::before {
content: '';
position: absolute;
width: 4px;
height: 4px;
background: #FFF;
/ Head, ears, and base structures */
box-shadow:
4px 0 #FFF, 8px 0 #FFF, 16px 0 #FFF, 20px 0 #FFF,
4px 4px #FFF, 8px 4px #FFF, 16px 4px #FFF, 20px 4px #FFF,
4px 8px #FFF, 8px 8px #FFF, 16px 8px #FFF, 20px 8px #FFF,
4px 12px #FFF, 8px 12px #FFF, 12px 12px #FFF, 16px 12px #FFF, 20px 12px #FFF,
0px 16px #FFF, 4px 16px #FFF, 8px 16px #FFF, 12px 16px #FFF, 16px 16px #FFF, 20px 16px #FFF, 24px 16px #FFF,
0px 20px #FFF, 4px 20px #FFF, 8px 20px #000, 12px 20px #FFF, 16px 20px #000, 20px 20px #FFF, 24px 20px #FFF,
0px 24px #FFF, 4px 24px #FFF, 8px 24px #FFF, 12px 24px #000, 16px 24px #FFF, 20px 24px #FFF, 24px 24px #FFF,
4px 28px #FFF, 8px 28px #FFF, 12px 28px #FFF, 16px 28px #FFF, 20px 28px #FFF,
0px 32px var(--pastel-pink-dark), 4px 32px var(--pastel-pink-dark), 8px 32px var(--pastel-pink-dark), 12px 32px var(--pastel-pink-dark), 16px 32px var(--pastel-pink-dark), 20px 32px var(--pastel-pink-dark), 24px 32px var(--pastel-pink-dark),
0px 36px var(--pastel-pink-dark), 4px 36px var(--pastel-pink-dark), 8px 36px var(--pastel-pink-dark), 12px 36px var(--pastel-pink-dark), 16px 36px var(--pastel-pink-dark), 20px 36px var(--pastel-pink-dark), 24px 36px var(--pastel-pink-dark),
4px 40px #FFF, 8px 40px #FFF, 16px 40px #FFF, 20px 40px #FFF;
}

/* --- Passcode View Container --- /
#login-screen {
background-color: var(--minecraft-container);
border: 4px solid var(--sage-green);
box-shadow: 8px 8px 0px var(--sage-green);
padding: 40px;
border-radius: 0px; / Rigid Minecraft theme blocks */
text-align: center;
max-width: 450px;
width: 90%;
z-index: 10;
}

h1, h2, h3 {
font-family: 'VT323', monospace;
letter-spacing: 1px;
}

#login-screen h1 {
font-size: 2.5rem;
margin-bottom: 10px;
}

.subtitle {
font-size: 0.95rem;
margin-bottom: 25px;
font-style: italic;
opacity: 0.9;
}

.mc-input-wrapper {
margin: 20px 0;
}

/* Minecraft Style Buttons and Inputs */
input[type="password"] {
font-family: 'VT323', monospace;
font-size: 1.8rem;
width: 100%;
padding: 10px;
text-align: center;
border: 4px solid var(--sage-light);
background-color: #FFF;
color: var(--sage-green);
outline: none;
}

input[type="password"]:focus {
border-color: var(--sage-green);
}

.mc-btn {
font-family: 'VT323', monospace;
font-size: 1.5rem;
background-color: var(--sage-green);
color: var(--baby-pink);
padding: 10px 25px;
border: none;
cursor: pointer;
box-shadow: 4px 4px 0px var(--sage-light);
transition: all 0.1s ease;
width: 100%;
margin-top: 15px;
}

.mc-btn:active {
transform: translate(2px, 2px);
box-shadow: 2px 2px 0px var(--sage-light);
}

#error-msg {
color: #D32F2F;
font-family: 'VT323', monospace;
font-size: 1.2rem;
margin-top: 15px;
display: none;
}

/* --- Main Content View Container --- */
#main-content {
display: none;
width: 95%;
max-width: 800px;
background-color: var(--minecraft-container);
border: 4px solid var(--sage-green);
box-shadow: 12px 12px 0px var(--sage-green);
padding: 30px;
z-index: 10;
margin: 40px 0;
animation: fadeIn 0.5s ease-in-out forwards;
}

@keyframes fadeIn {
from { opacity: 0; transform: scale(0.95); }
to { opacity: 1; transform: scale(1); }
}

.header-area {
text-align: center;
border-bottom: 4px dashed var(--sage-light);
padding-bottom: 20px;
margin-bottom: 30px;
position: relative;
}

.header-area h1 {
font-size: 3.5rem;
line-height: 1;
margin-bottom: 10px;
}

/* Custom Lily Pixel Icon Placement */
.lily-icon {
display: inline-block;
width: 24px;
height: 24px;
background: #FFF;
box-shadow:
0 -4px #FFF, 4px -4px #FFF, -4px -4px #FFF,
8px 0 var(--sage-light), -8px 0 var(--sage-light),
0 4px var(--sage-green), 0 8px var(--sage-green);
margin: 0 10px;
vertical-align: middle;
}

/* --- Three Line Button Grid / Row Concept --- */
.letters-grid {
display: grid;
grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
gap: 15px;
margin-bottom: 30px;
}

.letter-row-btn {
background: #FFF;
border: 3px solid var(--sage-light);
padding: 15px;
text-align: left;
font-size: 1.05rem;
font-weight: bold;
color: var(--sage-green);
cursor: pointer;
display: flex;
align-items: center;
transition: all 0.2s ease;
box-shadow: 4px 4px 0px var(--sage-light);
}

.letter-row-btn:hover {
background-color: #FFFDF2;
border-color: var(--sage-green);
transform: translateY(-2px);
box-shadow: 6px 6px 0px var(--sage-green);
}

.letter-row-btn .emoji {
font-size: 1.4rem;
margin-right: 12px;
}

/* --- Dynamic Letter Modal/Display --- */
#letter-display-box {
display: none;
background-color: #FFF;
border: 3px solid var(--sage-green);
padding: 25px;
margin-top: 20px;
box-shadow: inset 4px 4px 0px rgba(0,0,0,0.05);
animation: slideDown 0.3s ease-out forwards;
}

@keyframes slideDown {
from { opacity: 0; transform: translateY(-10px); }
to { opacity: 1; transform: translateY(0); }
}

#letter-title {
font-size: 2rem;
margin-bottom: 15px;
display: flex;
align-items: center;
border-bottom: 2px solid var(--baby-pink);
padding-bottom: 5px;
}

#letter-body {
font-size: 1.1rem;
line-height: 1.6;
white-space: pre-wrap; /* Keeps manual linebreaks clean */
}

/* --- Footer Signature Sign-off --- */
.footer-sig {
text-align: center;
margin-top: 40px;
font-family: 'VT323', monospace;
font-size: 1.8rem;
border-top: 4px dashed var(--sage-light);
padding-top: 20px;
}

.minecraft-heart {
display: inline-block;
width: 18px;
height: 14px;
background-color: var(--pastel-pink-dark);
position: relative;
margin: 0 5px;
vertical-align: middle;
box-shadow: 2px 2px #000;
}


Enter Secret Code
(Our birthdays MM/DD then the day we met one another!)
UNLOCK LETTERS

Incorrect code, try again my love! 💕
Sonja's Letters Garden
Pick how you are feeling right now, my beautiful girl:
😢 Open when you're sad
☀ Open when you're happy
🎉 Open when you're excited
😤 Open when you're upset at me
😡 Open when you're mad at someone
🤯 Open when you're stressed
🧸 Open when you're doubtful
🔋 Open when you lack motivation
📚 Open for an exam / huge event
🎲 Open randomly
Letter Title
Letter body content goes here...
With love, from yaya;) 

// Secure token match
const secretCode = "032509040820";
// Letters database - Easy for you to customize, edit, or extend anytime!
const lettersContent = {
sad: {
title: "😢 When You're Feeling Sad",
body: "Hey my beautiful lady, I'm so sorry you're feeling down right now. Remember how you almost drowned at beach, and I told you to stand up, MIND YOU still afloat, yet scared the pooh out of me. ( Hoped you laughed and not made a face.Lol.)

Seriously, just call me and we can add some joy to that blue mfker from insideout. :)  & Take a deep breath. Yaya is always right here with you. 💕"
},
happy: {
title: "☀ When You're Happy",
body: "Your happiness is literally my favorite thing in the entire world! Seeing you smile or hearing you laugh brightens up my whole life. Seeing you happy is amazing and heartwarming to me. Just you in general Sonja. So, whatever is making you happy to open this, I want you to know your joy brings me additional joy. Keep shining and keep completing your goals.!"
},
excited: {
title: "🎉 When You're Excited",
body: "Whatever just happened, I know you worked hard for it and 101% deserve it.!! Tell me everything! I love seeing your beautiful eyes light up when you're excited about something. Big or small. You deserve all the exciting, amazing things the world has to offer!"
},
upset: {
title: "😤 When You're Upset At Me",
body: "I probably overreacted, but maybe I am just as dramatic as you are, but... I will always communicate with you on everything. My frustration brings me alot of overwhelming emotions and I tend to get overly emotional. Knowing this makes me what to become more considerate about what I say and how I react. I am only improving everyday.

Now text me, after we had our lil min apart to talk and fix our conflicted feelings."
},
mad: {
title: "😡 First off, you're 100% right, ans they are just 100% incomprehensive. Do not let others frustrate you or have control over how you react. That was always the goal to make you react. Do not let them accomplish, and don't let them rent space in your head. Take a deep breath, and remember that you are a total badass.

Also, you can always vent to me, but if I cannot respond in time, here's the letter to read for quicker reassurance."
},
stressed: {
title: "🤯 When You're Stressed or Overwhelmed",
body: "Stop whatever you are doing for just a second. Drop your shoulders, unclench your jaw, and breathe. You are trying your absolute best and that is more than enough. We can take things one tiny step at a time together. Call me if needed I will do it with you."
}, 
title: "🧸 When You're Feeling Doubtful",
body: "I wish you could see yourself through my eyes for just one minute. If you did, you would never doubt yourself in any aspect. You are stunning, whimsical, bright, sexcc, doing amazing in life, a pleasure, caring, kind, and just every beauty in this life on earth.

As of right now tall to yourself KINDLY RT NOW! OR call me, and I will reassure you.:)"
},
motivation: {
title: "🔋 When You're Lacking Motivation",
body: "Getting started is always the hardest block to place. Just focus on doing five minutes of whatever task is ahead of you. If you need a break, let's take a cozy rest together. I believe in your work ethic and your dreams!"
},
exam: {
title: "📚👏🏾 When You Have An Exam / Big Event",
body: "You have studied so hard and prepared beautifully for this! Don't let the nerves take over. Walk in there with your head held high. No matter what the outcome is, I am already so proud of you and your beautiful mind."
},
random: {
title: "🎲 Open Randomly!",
body: "Surprise! Hey, sexcc! I like you alot, and I do not want to take things slow, however I want to increase our knowledge of one another. I am so excited to learn who you are and who we will become. You are amazing, you take one thing and make it so beautiful in every way there is to do so.

I too wish to become the person you imagine to let be with you one day. Til then lets continue to learn each other inside and out."
}
};
// Gate controller function
function checkCode() {
const userInput = document.getElementById("passcode-input").value;
const errorMsg = document.getElementById("error-msg");
const loginScreen = document.getElementById("login-screen");
const mainContent = document.getElementById("main-content");
if (userInput === secretCode) {
errorMsg.style.display = "none";
loginScreen.style.display = "none";
mainContent.style.display = "block";
} else {
errorMsg.style.display = "block";
}
}
// Live display action
function readLetter(key) {
const displayBox = document.getElementById("letter-display-box");
const titleElem = document.getElementById("letter-title");
const bodyElem = document.getElementById("letter-body");
if (lettersContent[key]) {
titleElem.innerHTML = lettersContent[key].title;
bodyElem.innerHTML = lettersContent[key].body;
displayBox.style.display = "block";
// Smooth scroll directly to the opened letter
displayBox.scrollIntoView({ behavior: 'smooth' });
}
}
// Permit press "Enter" to unlock
document.getElementById("passcode-input").addEventListener("keyup", function(event) {
if (event.key === "Enter") {
checkCode();
}
});

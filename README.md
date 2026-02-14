# apex5-stream-skin
apex5-stream-skin
:root{
  --bgGif: url("https://media.discordapp.net/attachments/1471380153996410971/1471380154629623966/11_1.gif");
  --main: #4cc9ff;
  --accent: #9b5cff;
  --white: #eaf2ff;
  --dark: #070a12;

  --glow: 0 0 10px rgba(76,201,255,.65), 0 0 22px rgba(155,92,255,.35);
  --glowStrong: 0 0 16px rgba(76,201,255,.90), 0 0 40px rgba(155,92,255,.60);
}

body{
  background: transparent !important;
}

#app, #root, .app, .overlay, .gamepad, .controller{
  background: transparent !important;
}

.gamepad, .controller, svg{
  filter: drop-shadow(0 14px 36px rgba(0,0,0,.60));
}

.gamepad::before, .controller::before{
  content:"";
  position:absolute;
  inset:-45px;
  background-image: var(--bgGif);
  background-size: cover;
  background-position: center;
  opacity:.55;
  pointer-events:none;
  border-radius: 30px;
  mix-blend-mode: screen;
}

text, .label, .labels, .buttonLabel{
  fill: var(--white) !important;
  color: var(--white) !important;
  font-weight: 700 !important;
  letter-spacing: .6px;
  text-shadow: 0 0 10px rgba(76,201,255,.25);
  opacity: .95;
}

svg *{
  transition: transform .08s ease, filter .12s ease, opacity .12s ease;
}

/* Allgemein Buttons Sticks Dpad Trigger Bumper */
[id*="A"], [id*="B"], [id*="X"], [id*="Y"],
[class*="a"], [class*="b"], [class*="x"], [class*="y"],
[class*="dpad"], [id*="dpad"],
[class*="stick"], [id*="stick"], [id*="ls"], [id*="rs"],
[class*="trigger"], [id*="lt"], [id*="rt"],
[class*="bumper"], [id*="lb"], [id*="rb"],
[class*="button"], [class*="face"]{
  filter: drop-shadow(0 0 14px rgba(76,201,255,.28));
}

/* Base Look */
[class*="button"], [class*="face"], [id*="A"], [id*="B"], [id*="X"], [id*="Y"]{
  fill: rgba(11,16,32,.92) !important;
  stroke: rgba(234,242,255,.18) !important;
  stroke-width: 2px !important;
}

/* Farbringe ABXY */
[id*="A"], [class*="a"]{ stroke: rgba(76,201,255,.50) !important; }
[id*="B"], [class*="b"]{ stroke: rgba(255,90,90,.45) !important; }
[id*="X"], [class*="x"]{ stroke: rgba(90,170,255,.45) !important; }
[id*="Y"], [class*="y"]{ stroke: rgba(255,220,90,.45) !important; }

/* Dpad */
[class*="dpad"], [id*="dpad"]{
  fill: rgba(11,16,32,.94) !important;
  stroke: rgba(76,201,255,.28) !important;
  stroke-width: 2px !important;
  filter: drop-shadow(0 0 16px rgba(76,201,255,.30));
}

/* Trigger */
[class*="trigger"], [id*="lt"], [id*="rt"]{
  fill: rgba(11,16,32,.96) !important;
  stroke: rgba(76,201,255,.22) !important;
  stroke-width: 2px !important;
  box-shadow: var(--glow);
}

/* Bumper */
[class*="bumper"], [id*="lb"], [id*="rb"]{
  fill: rgba(11,16,32,.96) !important;
  stroke: rgba(155,92,255,.22) !important;
  stroke-width: 2px !important;
}

/* Sticks */
[class*="stick"], [id*="stick"], [id*="ls"], [id*="rs"]{
  fill: rgba(11,16,32,.90) !important;
  stroke: rgba(76,201,255,.24) !important;
  stroke-width: 2px !important;
  filter: drop-shadow(0 0 18px rgba(76,201,255,.30));
}

/* Press Animation */
@keyframes pressPop{
  0%{ transform: scale(1); filter: brightness(1); }
  100%{ transform: scale(1.08); filter: brightness(1.25); }
}

.pressed, .active, .down, .isPressed,
.pressed * , .active * , .down * , .isPressed *{
  animation: pressPop .09s ease forwards;
  filter: drop-shadow(0 0 22px rgba(76,201,255,.55)) !important;
}

.pressed [class*="button"], .active [class*="button"], .down [class*="button"], .isPressed [class*="button"]{
  filter: drop-shadow(0 0 26px rgba(76,201,255,.70)) !important;
}

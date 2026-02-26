@import url('https://fonts.googleapis.com/css2?family=Bangers&family=Roboto:wght@400;700;900&display=swap');

* { margin:0; padding:0; box-sizing:border-box; touch-action:manipulation; user-select:none; -webkit-user-select:none; -webkit-tap-highlight-color:transparent; }
body { font-family:'Roboto',sans-serif; background:linear-gradient(135deg,#1a1a2e 0%,#16213e 50%,#0f3460 100%); overflow:hidden; height:100vh; position:relative; }
#gameCanvas { display:block; width:100%; height:100%; position:absolute; top:0; left:0; z-index:1; }

.ui-layer { position:absolute; top:0; left:0; width:100%; height:100%; pointer-events:none; display:flex; flex-direction:column; justify-content:space-between; padding:10px; z-index:10; }
.map-indicator { position:absolute; top:70px; left:50%; transform:translateX(-50%); background:rgba(0,0,0,0.8); color:#fff; padding:6px 15px; border-radius:15px; font-family:'Bangers',cursive; font-size:14px; border:2px solid #ffd700; z-index:20; }
.health-bars { display:flex; justify-content:space-between; align-items:flex-start; gap:20px; width:100%; margin-top:30px; }
.team-section { flex:1; max-width:200px; }
.team-name { font-family:'Bangers',cursive; font-size:14px; color:#ffd700; text-align:center; margin-bottom:5px; }
.fighter-status { margin-bottom:5px; }
.fighter-name { font-family:'Bangers',cursive; font-size:12px; color:#fff; margin-bottom:3px; }
.health-bar-container { background:rgba(0,0,0,0.6); border:2px solid #fff; border-radius:8px; height:20px; overflow:hidden; position:relative; }
.health-fill { height:100%; transition:width 0.3s ease; }
.player1 .health-fill, .player3 .health-fill { background:linear-gradient(90deg,#ff6b6b,#ee5a24); }
.player2 .health-fill, .player4 .health-fill { background:linear-gradient(90deg,#4ecdc4,#44a3aa); }
.health-text { position:absolute; top:50%; left:50%; transform:translate(-50%,-50%); color:#fff; font-weight:900; font-size:12px; }
.combo-counter { font-family:'Bangers',cursive; font-size:36px; color:#ffd700; text-align:center; opacity:0; transform:scale(0.5); transition:all 0.2s; }
.combo-counter.active { opacity:1; transform:scale(1); }
.controls-hint { text-align:center; color:#fff; font-size:14px; margin-bottom:5px; }
.controls-hint span { background:rgba(0,0,0,0.5); padding:5px 15px; border-radius:20px; }

.camera-target-indicator {
  position: absolute;
  width: 60px;
  height: 60px;
  border: 3px solid #ffd700;
  border-radius: 50%;
  pointer-events: none;
  z-index: 15;
  transform: translate(-50%, -50%);
  box-shadow: 0 0 20px rgba(255, 215, 0, 0.5);
  animation: pulse-camera 1.5s infinite;
}

@keyframes pulse-camera {
  0%, 100% { transform: translate(-50%, -50%) scale(1); opacity: 0.8; }
  50% { transform: translate(-50%, -50%) scale(1.2); opacity: 0.4; }
}

.joystick-container { position:absolute; bottom:20px; pointer-events:all; display:flex; flex-direction:column; align-items:center; z-index:50; }
#joystick1 { left:20px; }
#joystick2 { right:20px; }
.joystick-base { width:80px; height:80px; background:rgba(255,255,255,0.2); border:3px solid rgba(255,255,255,0.5); border-radius:50%; position:relative; touch-action:none; }
.joystick-stick { width:35px; height:35px; background:linear-gradient(135deg,#e74c3c,#c0392b); border-radius:50%; position:absolute; top:50%; left:50%; transform:translate(-50%,-50%); box-shadow:0 2px 5px rgba(0,0,0,0.3); touch-action:none; }
.joystick-label { color:#fff; font-size:10px; margin-top:5px; text-shadow:1px 1px 2px #000; }

.menu-screen { position:absolute; top:0; left:0; width:100%; height:100%; background:linear-gradient(135deg,rgba(26,26,46,0.98),rgba(22,33,62,0.98)); display:flex; flex-direction:column; align-items:center; z-index:100; overflow-y:auto; -webkit-overflow-scrolling:touch; padding:20px 10px; }
.menu-screen.hidden { display:none; }
.menu-content { width:100%; max-width:400px; display:flex; flex-direction:column; align-items:center; gap:15px; padding-bottom:30px; }

.game-title { font-family:'Bangers',cursive; font-size:50px; color:#fff; text-shadow:4px 4px 0 #e74c3c,8px 8px 0 #c0392b; margin-top:10px; letter-spacing:3px; }
.game-subtitle { font-size:16px; color:#ffd700; margin-bottom:10px; }

.btn { background:linear-gradient(135deg,#e74c3c,#c0392b); border:none; padding:15px 30px; font-size:18px; font-family:'Bangers',cursive; color:#fff; border-radius:30px; cursor:pointer; box-shadow:0 6px 0 #962d22,0 6px 10px rgba(0,0,0,0.3); transition:all 0.1s; width:100%; max-width:280px; touch-action:manipulation; }
.btn:active { transform:translateY(6px); box-shadow:0 0 0 #962d22; }
.btn-quick { background:linear-gradient(135deg,#f39c12,#e67e22); box-shadow:0 6px 0 #d35400; font-size:22px; animation:pulse 2s infinite; }
.btn-small { padding:10px 20px; font-size:14px; max-width:120px; }
.btn-confirm { background:linear-gradient(135deg,#2ecc71,#27ae60); box-shadow:0 6px 0 #1e8449; font-size:20px; }
.btn-menu { background:linear-gradient(135deg,#95a5a6,#7f8c8d); box-shadow:0 6px 0 #606f70; }

.divider { color:rgba(255,255,255,0.6); font-size:14px; margin:5px 0; }

.compact-section { background:rgba(255,255,255,0.05); border-radius:15px; padding:15px; width:100%; max-width:280px; }
.mode-select { display:flex; align-items:center; gap:10px; margin-bottom:10px; }
.mode-select label { color:#ffd700; font-size:14px; font-weight:700; }
.mode-select select { flex:1; background:rgba(0,0,0,0.3); border:2px solid rgba(255,255,255,0.3); color:#fff; padding:8px; border-radius:10px; font-size:14px; outline:none; }
.name-inputs { display:flex; gap:10px; }
.name-inputs input { flex:1; background:rgba(0,0,0,0.3); border:2px solid rgba(255,255,255,0.3); color:#fff; padding:10px; border-radius:10px; font-size:14px; text-align:center; outline:none; }

.select-title { font-family:'Bangers',cursive; font-size:36px; color:#ffd700; margin:10px 0; }

.char-grid, .map-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:10px; width:100%; max-width:300px; }
.map-grid { grid-template-columns:repeat(3,1fr); }
.char-card, .map-card { background:rgba(255,255,255,0.1); border:3px solid rgba(255,255,255,0.2); border-radius:15px; padding:15px 10px; cursor:pointer; transition:all 0.3s; display:flex; flex-direction:column; align-items:center; gap:5px; touch-action:manipulation; }
.char-card:hover, .map-card:hover { transform:scale(1.05); background:rgba(255,255,255,0.15); }
.char-card.selected, .map-card.selected { border-color:#ffd700; background:rgba(255,215,0,0.2); box-shadow:0 0 20px rgba(255,215,0,0.3); }
.char-icon, .map-icon { font-size:40px; }
.char-name, .map-name { font-family:'Bangers',cursive; color:#fff; font-size:14px; }
.char-diff { font-size:10px; padding:3px 8px; border-radius:10px; font-weight:700; }
.char-diff.easy { background:#2ecc71; color:#fff; }
.char-diff.medium { background:#f39c12; color:#fff; }
.char-diff.hard { background:#e74c3c; color:#fff; }

.selected-info { background:rgba(255,255,255,0.1); border-radius:10px; padding:12px; color:#fff; font-size:14px; text-align:center; width:100%; max-width:300px; }
.selected-info strong { color:#ffd700; }

.button-row { display:flex; gap:10px; width:100%; max-width:300px; justify-content:center; margin-top:10px; }

.countdown { position:absolute; top:50%; left:50%; transform:translate(-50%,-50%); font-family:'Bangers',cursive; font-size:100px; color:#ffd700; text-shadow:4px 4px 8px rgba(0,0,0,0.8); z-index:150; display:none; pointer-events:none; }
.winner-screen { position:absolute; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.9); display:none; flex-direction:column; justify-content:center; align-items:center; z-index:200; gap:20px; }
.winner-text { font-family:'Bangers',cursive; font-size:50px; color:#ffd700; text-align:center; padding:0 20px; }

@keyframes pulse {
  0%, 100% { transform:scale(1); }
  50% { transform:scale(1.05); }
}

@media (max-width:380px) {
  .game-title { font-size:40px; }
  .char-grid, .map-grid { grid-template-columns:repeat(2,1fr); }
  .joystick-base { width:70px; height:70px; }
  .joystick-stick { width:30px; height:30px; }
}

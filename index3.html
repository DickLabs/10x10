<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TENGRID</title>
<style>
  :root{
    --ink:#eef0e8;
    --paper:#12181f;
    --paper-2:#1a2229;
    --grid-line:#2a3541;
    --accent:#e8b23d;
    --muted:#5c6773;
    --danger:#d6564a;
    --ok:#4caf7d;
    --cell: 32px;
  }
  *{box-sizing:border-box;}
  html,body{
    margin:0; padding:0; height:100%;
    background:
      radial-gradient(circle at 15% 10%, #1c2a35 0%, transparent 45%),
      radial-gradient(circle at 85% 90%, #1a2431 0%, transparent 45%),
      var(--paper);
    color:var(--ink);
    font-family: 'Courier New', ui-monospace, monospace;
    -webkit-user-select:none; user-select:none;
    touch-action:none;
  }
  .wrap{
    display:flex; flex-direction:column; align-items:center;
    padding:24px 16px 60px;
    min-height:100%;
  }
  header{
    display:flex; align-items:baseline; justify-content:space-between;
    width:100%; max-width:420px; margin-bottom:18px;
  }
  h1{
    font-family: Georgia, 'Times New Roman', serif;
    font-weight:700; letter-spacing:6px;
    font-size:26px; margin:0; color:var(--ink);
  }
  h1 span{color:var(--accent);}
  .scorebox{
    text-align:right; font-size:12px; color:var(--muted);
    letter-spacing:2px; text-transform:uppercase;
  }
  .scorebox .num{
    display:block; font-size:28px; color:var(--accent);
    font-family: Georgia, serif; letter-spacing:0px; line-height:1.1;
  }
  #board{
    position:relative;
    width:calc(var(--cell) * 10);
    height:calc(var(--cell) * 10);
    background:
      repeating-linear-gradient(0deg, var(--grid-line) 0 1px, transparent 1px calc(var(--cell))),
      repeating-linear-gradient(90deg, var(--grid-line) 0 1px, transparent 1px calc(var(--cell))),
      var(--paper-2);
    border:2px solid var(--grid-line);
    box-shadow: 0 0 0 6px var(--paper), 0 12px 30px rgba(0,0,0,0.45);
    border-radius:4px;
  }
  .cell{
    position:absolute;
    width:var(--cell); height:var(--cell);
    box-sizing:border-box;
    border-radius:2px;
  }
  .cell.filled{
    box-shadow: inset 0 0 0 2px rgba(0,0,0,0.25), 0 1px 0 rgba(255,255,255,0.08);
  }
  .cell.preview-ok{
    background:rgba(76,175,125,0.35) !important;
    box-shadow: inset 0 0 0 2px var(--ok);
  }
  .cell.preview-bad{
    background:rgba(214,86,74,0.30) !important;
    box-shadow: inset 0 0 0 2px var(--danger);
  }
  .cell.clearing{
    animation: flash 0.32s ease-out forwards;
  }
  @keyframes flash{
    0%{ filter:brightness(2.4); transform:scale(1); opacity:1;}
    100%{ filter:brightness(2.4); transform:scale(0.4); opacity:0;}
  }

  #tray{
    display:flex; gap:14px; margin-top:26px;
    width:100%; max-width:420px; justify-content:center;
  }
  .slot{
    width:112px; height:112px;
    background:var(--paper-2);
    border:1px solid var(--grid-line);
    border-radius:6px;
    display:flex; align-items:center; justify-content:center;
    position:relative;
    cursor:grab;
  }
  .slot.empty{ opacity:0.25; cursor:default; }
  .slot.dragging-source{ opacity:0.2; }
  .piece-grid{ position:relative; }
  .piece-grid .cell{ position:absolute; }

  #status{
    margin-top:18px; min-height:20px;
    font-size:12px; letter-spacing:1px; color:var(--muted);
    text-transform:uppercase;
  }

  #ghost{
    position:fixed; top:0; left:0; pointer-events:none; z-index:50;
    opacity:0.9;
  }
  #ghost .cell{ position:absolute; }

  #overlay{
    position:fixed; inset:0; background:rgba(10,14,18,0.86);
    display:none; align-items:center; justify-content:center; z-index:100;
    flex-direction:column; gap:14px;
  }
  #overlay.show{ display:flex; }
  #overlay .msg{ font-family:Georgia,serif; font-size:30px; letter-spacing:2px; color:var(--accent); }
  #overlay .sub{ color:var(--muted); font-size:13px; letter-spacing:1px; }
  #overlay button{
    margin-top:10px;
    background:var(--accent); color:#1a1408; border:none;
    font-family:inherit; font-weight:700; letter-spacing:2px;
    padding:10px 22px; border-radius:4px; cursor:pointer; font-size:13px;
    text-transform:uppercase;
  }

  footer{
    margin-top:22px; font-size:11px; color:var(--muted); text-align:center; max-width:360px; line-height:1.6;
  }
</style>
</head>
<body>
<div class="wrap">
  <header>
    <h1>TEN<span>GRID</span></h1>
    <div style="display:flex; gap:22px;">
      <div class="scorebox">SCORE<span class="num" id="scoreNum">0</span></div>
      <div class="scorebox">BEST<span class="num" id="bestNum">0</span></div>
      <div class="scorebox">WORST<span class="num" id="worstNum">—</span></div>
    </div>
  </header>

  <div id="board"></div>

  <div id="tray">
    <div class="slot" id="slot0"><div class="piece-grid" id="piece0"></div></div>
    <div class="slot" id="slot1"><div class="piece-grid" id="piece1"></div></div>
    <div class="slot" id="slot2"><div class="piece-grid" id="piece2"></div></div>
  </div>

  <div id="status">Drag a piece onto the grid</div>

  <footer>Fixed orientations — no rotation. Full rows and columns of 10 clear together; overlapping cells only count once toward your score.</footer>
</div>

<div id="ghost"></div>

<div id="overlay">
  <div class="msg">NO MOVES LEFT</div>
  <div class="sub" id="finalScore"></div>
  <button id="restartBtn">Play Again</button>
</div>

<script>
(function(){
  const CELL = 32;
  const BOARD_N = 10;

  const BLOCK_COLOR = '#e8b23d';

  const SHAPES = [
    {name:'full',      cells:[[0,0],[0,1],[0,2],[1,0],[1,1],[1,2],[2,0],[2,1],[2,2]]},
    {name:'bigL-BL',   cells:[[0,0],[1,0],[2,0],[2,1],[2,2]]},
    {name:'bigL-BR',   cells:[[0,2],[1,2],[2,0],[2,1],[2,2]]},
    {name:'bigL-TR',   cells:[[0,0],[0,1],[0,2],[1,2],[2,2]]},
    {name:'bigL-TL',   cells:[[0,0],[0,1],[0,2],[1,0],[2,0]]},
    {name:'smallL-0',  cells:[[0,0],[1,0],[1,1]]},
    {name:'smallL-90', cells:[[0,0],[0,1],[1,0]]},
    {name:'smallL-180',cells:[[0,0],[0,1],[1,1]]},
    {name:'smallL-270',cells:[[0,1],[1,0],[1,1]]},
    {name:'line1',     cells:[[0,0]]},
    {name:'line2-h',   cells:[[0,0],[0,1]]},
    {name:'line2-v',   cells:[[0,0],[1,0]]},
    {name:'line3-h',   cells:[[0,0],[0,1],[0,2]]},
    {name:'line3-v',   cells:[[0,0],[1,0],[2,0]]},
    {name:'line4-h',   cells:[[0,0],[0,1],[0,2],[0,3]]},
    {name:'line4-v',   cells:[[0,0],[1,0],[2,0],[3,0]]},
    {name:'line5-h',   cells:[[0,0],[0,1],[0,2],[0,3],[0,4]]},
    {name:'line5-v',   cells:[[0,0],[1,0],[2,0],[3,0],[4,0]]},
  ].map(s=>{
    const rows = Math.max(...s.cells.map(c=>c[0]))+1;
    const cols = Math.max(...s.cells.map(c=>c[1]))+1;
    return {...s, rows, cols};
  });

  function randShape(){
    const s = SHAPES[Math.floor(Math.random()*SHAPES.length)];
    return {...s, color: BLOCK_COLOR};
  }

  // board state: null or color string
  let board = Array.from({length:BOARD_N}, ()=>Array(BOARD_N).fill(null));
  let score = 0;
  let highScore = 0;
  let worstScore = null;
  let tray = [randShape(), randShape(), randShape()];
  let gameOver = false;

  const boardEl = document.getElementById('board');
  const scoreEl = document.getElementById('scoreNum');
  const bestEl = document.getElementById('bestNum');
  const worstEl = document.getElementById('worstNum');
  const statusEl = document.getElementById('status');
  const ghostEl = document.getElementById('ghost');
  const overlayEl = document.getElementById('overlay');

  const boardCellEls = Array.from({length:BOARD_N}, ()=>Array(BOARD_N).fill(null));

  function initBoardDom(){
    boardEl.innerHTML='';
    for(let r=0;r<BOARD_N;r++){
      for(let c=0;c<BOARD_N;c++){
        const d = document.createElement('div');
        d.className='cell';
        d.style.left = (c*CELL)+'px';
        d.style.top = (r*CELL)+'px';
        boardEl.appendChild(d);
        boardCellEls[r][c]=d;
      }
    }
  }

  function renderBoard(){
    for(let r=0;r<BOARD_N;r++){
      for(let c=0;c<BOARD_N;c++){
        const el = boardCellEls[r][c];
        const val = board[r][c];
        el.classList.remove('preview-ok','preview-bad');
        if(val){
          el.classList.add('filled');
          el.style.background = val;
        } else {
          el.classList.remove('filled');
          el.style.background = 'transparent';
        }
      }
    }
  }

  function renderPieceGrid(container, shape, cellSize){
    container.innerHTML='';
    container.style.width = (shape.cols*cellSize)+'px';
    container.style.height = (shape.rows*cellSize)+'px';
    shape.cells.forEach(([r,c])=>{
      const d = document.createElement('div');
      d.className='cell filled';
      d.style.width = cellSize+'px';
      d.style.height = cellSize+'px';
      d.style.left = (c*cellSize)+'px';
      d.style.top = (r*cellSize)+'px';
      d.style.background = shape.color;
      container.appendChild(d);
    });
  }

  function renderTray(){
    for(let i=0;i<3;i++){
      const slot = document.getElementById('slot'+i);
      const grid = document.getElementById('piece'+i);
      if(!tray[i]){
        slot.classList.add('empty');
        grid.innerHTML='';
      } else {
        slot.classList.remove('empty');
        renderPieceGrid(grid, tray[i], 22);
      }
    }
  }

  function isValidPlacement(shape, rowStart, colStart){
    for(const [dr,dc] of shape.cells){
      const r = rowStart+dr, c = colStart+dc;
      if(r<0||r>=BOARD_N||c<0||c>=BOARD_N) return false;
      if(board[r][c]) return false;
    }
    return true;
  }

  function canPlaceAnywhere(shape){
    for(let r=0;r<BOARD_N;r++){
      for(let c=0;c<BOARD_N;c++){
        if(isValidPlacement(shape,r,c)) return true;
      }
    }
    return false;
  }

  function checkGameOver(){
    const anyPlaceable = tray.some(s=>s && canPlaceAnywhere(s));
    if(!anyPlaceable){
      gameOver = true;
      maybeSaveWorstScore(score);
      document.getElementById('finalScore').textContent =
        'Final score: '+score+(score>=highScore && score>0 ? '  •  New best!' : '  •  Best: '+highScore);
      overlayEl.classList.add('show');
    }
  }

  function commitPlacement(pieceIndex, shape, rowStart, colStart){
    shape.cells.forEach(([dr,dc])=>{
      board[rowStart+dr][colStart+dc] = shape.color;
    });

    // find full rows/cols
    const cellsToClear = new Set();
    for(let r=0;r<BOARD_N;r++){
      if(board[r].every(v=>v)){
        for(let c=0;c<BOARD_N;c++) cellsToClear.add(r+','+c);
      }
    }
    for(let c=0;c<BOARD_N;c++){
      let full = true;
      for(let r=0;r<BOARD_N;r++) if(!board[r][c]){full=false;break;}
      if(full){
        for(let r=0;r<BOARD_N;r++) cellsToClear.add(r+','+c);
      }
    }

    renderBoard();

    if(cellsToClear.size>0){
      cellsToClear.forEach(key=>{
        const [r,c] = key.split(',').map(Number);
        boardCellEls[r][c].classList.add('clearing');
      });
      score += cellsToClear.size;
      scoreEl.textContent = score;
      statusEl.textContent = cellsToClear.size+' blocks cleared';
      maybeSaveHighScore();
      setTimeout(()=>{
        cellsToClear.forEach(key=>{
          const [r,c] = key.split(',').map(Number);
          board[r][c]=null;
          boardCellEls[r][c].classList.remove('clearing');
        });
        renderBoard();
      }, 320);
    } else {
      statusEl.textContent = 'Placed';
    }

    tray[pieceIndex] = null;
    if(tray.every(s=>s===null)){
      tray = [randShape(), randShape(), randShape()];
    }
    renderTray();
    checkGameOver();
  }

  async function loadHighScore(){
    try{
      const res = await window.storage.get('highscore');
      highScore = res ? parseInt(res.value,10)||0 : 0;
    }catch(e){
      highScore = 0;
    }
    bestEl.textContent = highScore;
  }

  async function maybeSaveHighScore(){
    if(score>highScore){
      highScore = score;
      bestEl.textContent = highScore;
      try{
        await window.storage.set('highscore', String(highScore));
      }catch(e){ /* storage unavailable, best score just won't persist */ }
    }
  }

  async function loadWorstScore(){
    try{
      const res = await window.storage.get('worstscore');
      worstScore = res ? parseInt(res.value,10) : null;
    }catch(e){
      worstScore = null;
    }
    worstEl.textContent = worstScore===null ? '—' : worstScore;
  }

  async function maybeSaveWorstScore(finalScore){
    if(worstScore===null || finalScore<worstScore){
      worstScore = finalScore;
      worstEl.textContent = worstScore;
      try{
        await window.storage.set('worstscore', String(worstScore));
      }catch(e){ /* storage unavailable, worst score just won't persist */ }
    }
  }

  // ---- Drag logic ----
  let drag = null; // {index, shape, grabOffsetX, grabOffsetY}

  function clearPreview(){
    for(let r=0;r<BOARD_N;r++)
      for(let c=0;c<BOARD_N;c++)
        boardCellEls[r][c].classList.remove('preview-ok','preview-bad');
  }

  function showPreview(shape, rowStart, colStart){
    clearPreview();
    const valid = isValidPlacement(shape, rowStart, colStart);
    shape.cells.forEach(([dr,dc])=>{
      const r=rowStart+dr, c=colStart+dc;
      if(r>=0&&r<BOARD_N&&c>=0&&c<BOARD_N){
        boardCellEls[r][c].classList.add(valid?'preview-ok':'preview-bad');
      }
    });
    return valid;
  }

  function startDrag(e, index){
    if(gameOver) return;
    const shape = tray[index];
    if(!shape) return;
    const slot = document.getElementById('slot'+index);
    const grid = document.getElementById('piece'+index);
    const gridRect = grid.getBoundingClientRect();

    // scale factor between tray render (22px) and board cell (CELL)
    const scale = CELL/22;

    drag = {
      index, shape,
      grabOffsetX: (e.clientX - gridRect.left)*scale,
      grabOffsetY: (e.clientY - gridRect.top)*scale,
      lastRow: null, lastCol: null, lastValid:false
    };

    slot.classList.add('dragging-source');
    renderPieceGrid(ghostEl, shape, CELL);
    ghostEl.style.display='block';
    positionGhost(e.clientX, e.clientY);

    document.addEventListener('pointermove', onDragMove);
    document.addEventListener('pointerup', onDragEnd);
  }

  function positionGhost(x,y){
    ghostEl.style.left = (x - drag.grabOffsetX)+'px';
    ghostEl.style.top = (y - drag.grabOffsetY)+'px';
  }

  function onDragMove(e){
    if(!drag) return;
    positionGhost(e.clientX, e.clientY);
    const boardRect = boardEl.getBoundingClientRect();
    const colStart = Math.round((e.clientX - drag.grabOffsetX - boardRect.left)/CELL);
    const rowStart = Math.round((e.clientY - drag.grabOffsetY - boardRect.top)/CELL);
    drag.lastRow = rowStart; drag.lastCol = colStart;
    drag.lastValid = showPreview(drag.shape, rowStart, colStart);
  }

  function onDragEnd(e){
    if(!drag) return;
    document.removeEventListener('pointermove', onDragMove);
    document.removeEventListener('pointerup', onDragEnd);

    const slot = document.getElementById('slot'+drag.index);
    slot.classList.remove('dragging-source');
    ghostEl.style.display='none';
    clearPreview();

    if(drag.lastValid){
      commitPlacement(drag.index, drag.shape, drag.lastRow, drag.lastCol);
    } else {
      statusEl.textContent = 'Can\'t place there';
    }
    drag = null;
  }

  function attachTrayHandlers(){
    for(let i=0;i<3;i++){
      const slot = document.getElementById('slot'+i);
      slot.addEventListener('pointerdown', (e)=>{
        e.preventDefault();
        startDrag(e, i);
      });
    }
  }

  function restart(){
    board = Array.from({length:BOARD_N}, ()=>Array(BOARD_N).fill(null));
    score = 0;
    scoreEl.textContent = '0';
    bestEl.textContent = highScore;
    worstEl.textContent = worstScore===null ? '—' : worstScore;
    tray = [randShape(), randShape(), randShape()];
    gameOver = false;
    overlayEl.classList.remove('show');
    statusEl.textContent = 'Drag a piece onto the grid';
    renderBoard();
    renderTray();
  }

  document.getElementById('restartBtn').addEventListener('click', restart);

  initBoardDom();
  renderBoard();
  renderTray();
  attachTrayHandlers();
  loadHighScore();
  loadWorstScore();
})();
</script>
</body>
</html>

// Slot symbols (use emojis for demo. Replace with images for closer match.)
const slotSymbols = [
  { symbol: '👁️', color: '#cfcf00' }, // Eye of Horus
  { symbol: '🪙', color: '#e1a228' }, // Pot of gold
  { symbol: '🦅', color: '#db3e00' }, // Falcon
  { symbol: '🔱', color: '#38cfea' }, // Lotus
  { symbol: 'Q', color: '#66e066' },
  { symbol: 'K', color: '#e06666' },
  { symbol: 'J', color: '#66a3e0' },
  { symbol: 'A', color: '#fff' },
];

// 5x3 grid
const rows = 3;
const cols = 5;

// Game state
let balance = 100.00;
let bet = 25.00;
let lastWin = 0.00;

function randomSymbol() {
  const idx = Math.floor(Math.random() * slotSymbols.length);
  return slotSymbols[idx];
}

function renderGrid() {
  const grid = document.getElementById('slot-grid');
  grid.innerHTML = '';
  for (let r = 0; r < rows; r++) {
    for (let c = 0; c < cols; c++) {
      const sym = randomSymbol();
      const div = document.createElement('div');
      div.className = 'slot-symbol';
      div.style.color = sym.color;
      div.textContent = sym.symbol;
      grid.appendChild(div);
    }
  }
}

function updateUI() {
  document.getElementById('balance').textContent = balance.toFixed(2);
  document.getElementById('lastWin').textContent = lastWin.toFixed(2);
  document.getElementById('betValue').textContent = bet.toFixed(2);
}

function spin() {
  if (balance < bet) {
    alert('Not enough balance!');
    return;
  }
  balance -= bet;
  renderGrid();
  // Random win for demo
  if (Math.random() < 0.3) {
    lastWin = Math.floor(Math.random() * 100) + bet;
    balance += lastWin;
  } else {
    lastWin = 0;
  }
  updateUI();
}

// UI events
document.addEventListener('DOMContentLoaded', () => {
  renderGrid();
  updateUI();
  document.getElementById('spinBtn').addEventListener('click', spin);
  document.getElementById('turboSpinBtn').addEventListener('mousedown', function() {
    spin();
    this.turboSpinInterval = setInterval(spin, 300);
  });
  document.getElementById('turboSpinBtn').addEventListener('mouseup', function() {
    clearInterval(this.turboSpinInterval);
  });
  document.getElementById('turboSpinBtn').addEventListener('mouseleave', function() {
    clearInterval(this.turboSpinInterval);
  });
  document.getElementById('autoSpinBtn').addEventListener('click', () => {
    let spins = 10;
    const autoSpin = setInterval(() => {
      spin();
      if (--spins <= 0) clearInterval(autoSpin);
    }, 500);
  });
});

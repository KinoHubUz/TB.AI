
<html lang="uz">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>TB.AI v0.0.5</title>
<link id="fav" rel="icon" href="data:,">
<style>
:root{
  --bg:#FAF9F5; --panel:#FFFFFF; --ink:#1F1E1D; --muted:#73726C; --line:#E6E3DA;
  --user:#F0EEE6; --accent:#C96442; --accent-ink:#fff; --soft:#F5F1E8;
}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    --bg:#262624; --panel:#30302E; --ink:#F2F0E8; --muted:#A09F97; --line:#3E3E3B;
    --user:#3A3936; --accent:#D97757; --accent-ink:#fff; --soft:#2F2E2B;
  }
}
*{box-sizing:border-box;margin:0;padding:0}
[hidden]{display:none !important}
html,body{height:100%}
body{
  background:var(--bg);color:var(--ink);
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
  font-size:16px;line-height:1.6;display:flex;flex-direction:column;height:100dvh;
}
.serif{font-family:Georgia,"Iowan Old Style","Times New Roman",serif}
header{
  display:flex;align-items:center;justify-content:space-between;gap:8px;
  padding:10px 14px;border-bottom:1px solid var(--line);background:var(--bg);
}
.brand{display:flex;align-items:center;gap:9px;min-width:0}
.brand svg{flex:0 0 auto;display:block}
.wm{display:flex;flex-direction:column;line-height:1.1}
.wm b{font-weight:700;font-size:17px;letter-spacing:.2px}
.wm small{color:var(--muted);font-size:11px}
.ver{font-size:11px;color:var(--muted);border:1px solid var(--line);border-radius:999px;padding:1px 8px;white-space:nowrap}
.off{font-size:11px;color:#2f7d4f;display:flex;align-items:center;gap:5px;white-space:nowrap}
.off i{width:7px;height:7px;border-radius:50%;background:#3aa468;display:inline-block}
.tools{display:flex;gap:6px;align-items:center}
.btn{
  background:transparent;border:1px solid var(--line);color:var(--ink);
  border-radius:10px;padding:5px 9px;font-size:12px;cursor:pointer;
}
.btn:hover{background:var(--soft)}
.seg{display:flex;border:1px solid var(--line);border-radius:10px;overflow:hidden}
.seg button{padding:5px 9px;font-size:12px;border:0;background:transparent;color:var(--muted);cursor:pointer}
.seg button.on{background:var(--accent);color:#fff}
@media (max-width:560px){ .off span{display:none} .wm small{display:none} }
main{flex:1;overflow-y:auto;padding:20px 16px 8px}
.wrap{max-width:720px;margin:0 auto}
.welcome{text-align:center;padding:8vh 0 20px}
.welcome .lg{margin:0 auto 16px;width:60px}
.welcome h1{font-weight:400;font-size:clamp(26px,6vw,36px);letter-spacing:-.01em}
.welcome p{color:var(--muted);margin-top:6px}
.chips{display:flex;flex-wrap:wrap;gap:8px;justify-content:center;margin-top:22px}
.chip{
  border:1px solid var(--line);background:var(--panel);color:var(--ink);
  border-radius:999px;padding:8px 14px;font-size:14px;cursor:pointer;
}
.chip:hover{background:var(--soft)}
.msg{display:flex;gap:12px;margin:18px 0}
.msg.user{justify-content:flex-end}
.bubble{background:var(--user);padding:10px 16px;border-radius:18px;max-width:85%;white-space:pre-wrap;word-break:break-word}
.ai-av{flex:0 0 28px;width:28px;height:28px;margin-top:2px}
.ai-av svg{display:block}
.ai-body{flex:1;min-width:0}
.line{margin:3px 0;word-break:break-word;white-space:pre-wrap}
.step{color:var(--muted);font-size:15px}
.result{
  display:inline-block;margin:6px 6px 6px 0;background:var(--soft);border:1px solid var(--line);
  border-radius:12px;padding:6px 14px;font-size:20px;font-weight:600;
}
.result small{color:var(--accent);font-weight:600;font-size:13px;margin-right:8px}
.dots{display:inline-flex;gap:4px;padding:8px 0}
.dots span{width:7px;height:7px;border-radius:50%;background:var(--accent);opacity:.3;animation:b 1s infinite}
.dots span:nth-child(2){animation-delay:.15s}.dots span:nth-child(3){animation-delay:.3s}
@keyframes b{0%,100%{opacity:.25;transform:translateY(0)}50%{opacity:1;transform:translateY(-3px)}}
footer{padding:8px 16px calc(14px + env(safe-area-inset-bottom));background:var(--bg)}
.box{
  max-width:720px;margin:0 auto;background:var(--panel);border:1px solid var(--line);
  border-radius:24px;padding:10px 10px 10px 18px;display:flex;align-items:flex-end;gap:8px;
  box-shadow:0 2px 10px rgba(0,0,0,.05);
}
.box:focus-within{border-color:var(--accent)}
textarea{
  flex:1;border:0;outline:0;resize:none;background:transparent;color:var(--ink);
  font:inherit;max-height:140px;padding:6px 0;
}
textarea::placeholder{color:var(--muted)}
.send{
  width:36px;height:36px;border-radius:50%;border:0;background:var(--accent);color:var(--accent-ink);
  cursor:pointer;display:grid;place-items:center;flex:0 0 36px;
}
.note{text-align:center;color:var(--muted);font-size:12px;margin-top:8px}
.settings-wrap{position:relative}.dots-btn{font-size:22px;line-height:1;min-width:34px;height:34px;padding:2px 9px}
.settings-menu{position:absolute;right:0;top:42px;z-index:20;width:min(270px,80vw);padding:6px;background:var(--panel);border:1px solid var(--line);border-radius:14px;box-shadow:0 12px 35px #0002}
.settings-menu button{display:flex;align-items:center;gap:9px;width:100%;padding:11px;border:0;border-radius:9px;background:transparent;color:var(--ink);text-align:left;font:inherit;font-size:14px;cursor:pointer}.settings-menu button:hover{background:var(--soft)}
.settings-shade{position:fixed;inset:0;z-index:50;background:#0007;display:grid;place-items:center;padding:18px}.settings-dialog{width:min(520px,100%);max-height:82dvh;overflow:auto;background:var(--panel);color:var(--ink);border:1px solid var(--line);border-radius:20px;padding:18px;box-shadow:0 20px 70px #0004}.dialog-head{display:flex;align-items:center;justify-content:space-between;gap:12px;margin-bottom:14px}.dialog-head h2{font-size:20px}.settings-dialog h3{font-size:16px;margin:12px 0 7px}.settings-dialog p,.settings-dialog li{font-size:14px;color:var(--muted);line-height:1.65}.settings-dialog ul{padding-left:20px}.lang-options{display:flex;flex-wrap:wrap;gap:8px;margin:12px 0}.lang-options button,.sample-q{border:1px solid var(--line);background:var(--bg);color:var(--ink);padding:9px 12px;border-radius:10px;cursor:pointer}.lang-options button.active{background:var(--accent);color:white}.qa-list{display:grid;gap:8px}.qa-row{padding:10px 12px;border:1px solid var(--line);border-radius:12px}.qa-row b{display:block;font-size:14px}.qa-row span{display:block;font-size:14px;color:var(--muted);margin-top:3px}.sample-q{margin:4px 5px 4px 0}
</style>
</head>
<body>

<header>
  <div class="brand">
    <span id="hLogo"></span>
    <div class="wm"><b>TB.AI</b><small id="tag"></small></div>
    <span class="ver">v0.0.5</span>
    <span class="off"><i></i><span>offline</span></span>
  </div>
  <div class="tools">
    <button class="btn" id="degBtn" title="Sin/cos/tan">RAD</button>
    <button class="btn" id="newBtn"></button>
    <div class="settings-wrap"><button class="btn dots-btn" id="settingsBtn" aria-label="Settings" title="Sozlamalar">⋮</button>
      <div class="settings-menu" id="settingsMenu" hidden>
        <button data-panel="languages">🌐 <span id="menuLang">Tillar</span></button>
        <button data-panel="questions">❔ <span id="menuQuestions">Qanday savollarga javob beradi?</span></button>
        <button data-panel="about">✦ <span id="menuAbout">AI haqida</span></button>
      </div>
    </div>
  </div>
</header>

<main id="main"><div class="wrap" id="chat"></div></main>
<div class="settings-shade" id="settingsShade" hidden><section class="settings-dialog" role="dialog" aria-modal="true" aria-labelledby="settingsTitle"><div class="dialog-head"><h2 id="settingsTitle">Sozlamalar</h2><button class="btn" id="closeSettings" aria-label="Close">✕</button></div><div id="settingsContent"></div></section></div>

<footer>
  <div class="box">
    <textarea id="inp" rows="1"></textarea>
    <button class="send" id="sendBtn" aria-label="Send">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M12 19V5M5 12l7-7 7 7"/></svg>
    </button>
  </div>
  <div class="note" id="note"></div>
</footer>

<script>
/* ============ Logo ============ */
const logo = (size, color) => `<svg width="${size}" height="${size}" viewBox="0 0 48 48" aria-hidden="true"><defs><linearGradient id="tbgrad" x1="0" y1="0" x2="1" y2="1"><stop stop-color="${color || '#4DEBFF'}"/><stop offset="1" stop-color="#796BFF"/></linearGradient></defs><rect width="48" height="48" rx="15" fill="#10182B"/><rect x="1" y="1" width="46" height="46" rx="14" fill="none" stroke="url(#tbgrad)" stroke-width="1.5"/><path d="M24 7l4.2 11.8L40 23l-11.8 4.2L24 39l-4.2-11.8L8 23l11.8-4.2Z" fill="url(#tbgrad)"/><circle cx="24" cy="23" r="4" fill="#fff"/></svg>`;

/* ============ i18n ============ */
const STR = {
  uz: {
    placeholder: "TB.AI ga yozing…", newBtn: "Yangi", tag: "The Best AI",
    note: "TB.AI v0.0.5 — oflayn suhbat va hisoblash. Javoblar oldindan yozilgan bilimlarga tayanadi.",
    welcomeTitle: "Salom! Nima haqida gaplashamiz?",
    welcomeSub: "Savol bering, suhbatlashing yoki misol yechtiring — internetsiz.",
    suggestions: ["12*(3+4)-5", "2x+3=11", "x^2-5x+6=0", "Salom, kimsan?", "200 ning 15 foizi", "Latifa ayt"],
    answer: "Javob:",
    badChar: c => "Tushunmagan belgi: «" + c + "»",
    divZero: "Nolga bo'lib bo'lmaydi.", factorial: "Faktorial faqat 0 dan 170 gacha butun sonlar uchun.",
    unclosed: "Qavs yopilmagan.", incomplete: "Ifoda tugallanmagan.",
    noX: "Noma'lum x uchun tenglama yozing, masalan: 2x+3=11",
    unknownWord: w => "Noma'lum so'z: «" + w + "»", notUnderstood: "Ifodani tushunmadim.",
    undef: "Natija aniqlanmadi (cheksiz yoki noto'g'ri).", writeMath: "Misol yozing.",
    eqOne: "Tenglamada faqat bitta «=» bo'lishi kerak.",
    eqDeg: "Hozircha faqat chiziqli va kvadrat tenglamalarni yecha olaman.",
    eqInf: "Bu tenglik har qanday x uchun to'g'ri (cheksiz ko'p yechim).",
    eqNone: "Bu tenglamaning yechimi yo'q.",
    eqLinear: "Chiziqli tenglama:", eqQuad: "Kvadrat tenglama:", disc: "Diskriminant",
    dNeg: "D < 0, haqiqiy ildizlar yo'q. Kompleks ildizlar:",
    fallback: [
      "Buni to'liq tushunmadim. Men hozircha suhbat va matematikani bilaman — «yordam» deb yozing.",
      "Hmm, bu savolga hali javob bera olmayman. Boshqacha so'rab ko'ring yoki misol yozing.",
      "Men hozircha oddiyroq AI man, lekin o'rganyapman. Masalan, «latifa ayt» yoki «2x+3=11» deb ko'ring."
    ]
  },
  en: {
    placeholder: "Message TB.AI…", newBtn: "New", tag: "The Best AI",
    note: "TB.AI v0.0.4 — offline chat and calculations. Answers rely on built-in knowledge.",
    welcomeTitle: "Hello! What shall we talk about?",
    welcomeSub: "Ask questions, chat, or solve math problems — offline.",
    suggestions: ["12*(3+4)-5", "2x+3=11", "x^2-5x+6=0", "Hi, who are you?", "15% of 200", "Tell me a joke"],
    answer: "Answer:",
    badChar: c => "Unrecognized symbol: “" + c + "”",
    divZero: "Division by zero is not possible.", factorial: "Factorial works only for whole numbers from 0 to 170.",
    unclosed: "Missing closing parenthesis.", incomplete: "The expression is incomplete.",
    noX: "For an unknown x, write an equation, e.g. 2x+3=11",
    unknownWord: w => "Unknown word: “" + w + "”", notUnderstood: "I couldn't understand the expression.",
    undef: "The result is undefined or infinite.", writeMath: "Type a problem.",
    eqOne: "An equation must contain exactly one “=”.",
    eqDeg: "For now I can only solve linear and quadratic equations.",
    eqInf: "This is true for every x (infinitely many solutions).",
    eqNone: "This equation has no solution.",
    eqLinear: "Linear equation:", eqQuad: "Quadratic equation:", disc: "Discriminant",
    dNeg: "D < 0, no real roots. Complex roots:",
    fallback: [
      "I didn't fully get that. Right now I can chat a little and do math — type “help” to see how.",
      "Hmm, I can't answer that yet. Try rephrasing, or give me a math problem.",
      "I'm a fairly simple AI for now, but I'm learning. Try “tell me a joke” or “2x+3=11”."
    ]
  }
};
STR.ru = {
  ...STR.en,
  placeholder:"Напишите TB.AI…", newBtn:"Новый чат", tag:"Локальный AI",
  note:"TB.AI v0.0.3 — работает офлайн. Ответы могут быть неточными.",
  welcomeTitle:"Привет! О чём поговорим?", welcomeSub:"Общайтесь или решайте математические задачи — без интернета.",
  suggestions:["12*(3+4)-5","2x+3=11","x^2-5x+6=0","Привет, кто ты?","15% от 200","Расскажи анекдот"],
  answer:"Ответ:", badChar:c=>"Неизвестный символ: «"+c+"»",
  divZero:"На ноль делить нельзя.", factorial:"Факториал доступен для целых чисел от 0 до 170.",
  unclosed:"Не закрыта скобка.", incomplete:"Выражение не завершено.",
  noX:"Введите уравнение с x, например: 2x+3=11",
  unknownWord:w=>"Неизвестное слово: «"+w+"»", notUnderstood:"Не удалось разобрать выражение.",
  undef:"Результат не определён.", writeMath:"Введите пример.",
  eqOne:"В уравнении должен быть один знак «=».",
  eqDeg:"Пока поддерживаются линейные и квадратные уравнения.",
  eqInf:"Равенство верно при любом x.", eqNone:"У этого уравнения нет решений.",
  eqLinear:"Линейное уравнение:", eqQuad:"Квадратное уравнение:", disc:"Дискриминант",
  dNeg:"D < 0, действительных корней нет. Комплексные корни:",
  fallback:["Я пока не знаю, как ответить на это. Попробуйте спросить иначе.","Я работаю офлайн и пока умею не всё. Напишите «помощь».","Могу помочь с математикой и простым разговором."]
};
let lang = 'uz';
const t = (k, ...a) => { const v = STR[lang][k]; return typeof v === 'function' ? v(...a) : v; };

/* ============ Math engine ============ */
const S = { deg:false, ans:0 };
const FUNCS = {
  sqrt:Math.sqrt, cbrt:Math.cbrt, abs:Math.abs, exp:Math.exp, ln:Math.log, log:Math.log10, lg:Math.log10,
  floor:Math.floor, ceil:Math.ceil, round:Math.round,
  sin:x=>Math.sin(S.deg?x*Math.PI/180:x), cos:x=>Math.cos(S.deg?x*Math.PI/180:x), tan:x=>Math.tan(S.deg?x*Math.PI/180:x),
  asin:x=>S.deg?Math.asin(x)*180/Math.PI:Math.asin(x), acos:x=>S.deg?Math.acos(x)*180/Math.PI:Math.acos(x), atan:x=>S.deg?Math.atan(x)*180/Math.PI:Math.atan(x)
};
const err = (k, ...a) => { const e = new Error(k); e.k = k; e.a = a; e.math = true; return e; };
const soft = e => { e.soft = true; return e; };

function tokenize(s){
  const tk = []; let i = 0;
  while(i < s.length){
    const c = s[i];
    if(/\s/.test(c)){ i++; continue; }
    let m;
    if((m = /^(\d+\.?\d*|\.\d+)/.exec(s.slice(i)))){ tk.push({k:'n', v:parseFloat(m[1])}); i += m[1].length; continue; }
    if((m = /^[a-z]+/.exec(s.slice(i)))){ tk.push({k:'id', v:m[0]}); i += m[0].length; continue; }
    if('+-*/^()!%'.includes(c)){ tk.push({k:c}); i++; continue; }
    throw soft(err('badChar', c));
  }
  return tk;
}

function evaluate(src, x){
  const tk = tokenize(src); let p = 0;
  const peek = () => tk[p];
  const eat = k => { if(tk[p] && tk[p].k === k){ p++; return true; } return false; };
  function expr(){
    let v = term();
    for(;;){ if(eat('+')) v += term(); else if(eat('-')) v -= term(); else return v; }
  }
  function term(){
    let v = unary();
    for(;;){
      const k = peek();
      if(!k) return v;
      if(eat('*')) v *= unary();
      else if(eat('/')){ const d = unary(); if(d === 0) throw err('divZero'); v /= d; }
      else if(k.k === 'id' && k.v === 'mod'){ p++; const d = unary(); if(d === 0) throw err('divZero'); v = ((v % d) + d) % d; }
      else if(k.k === '(' || k.k === 'id'){ v *= unary(); }
      else return v;
    }
  }
  function unary(){ if(eat('-')) return -unary(); if(eat('+')) return unary(); return power(); }
  function power(){ const b = postfix(); if(eat('^')) return Math.pow(b, unary()); return b; }
  function postfix(){
    let v = primary();
    for(;;){
      if(eat('!')){
        if(!Number.isInteger(v) || v < 0 || v > 170) throw err('factorial');
        let r = 1; for(let i = 2; i <= v; i++) r *= i; v = r;
      } else if(eat('%')) v = v / 100;
      else return v;
    }
  }
  function primary(){
    const k = peek();
    if(!k) throw err('incomplete');
    if(k.k === 'n'){ p++; return k.v; }
    if(k.k === '('){ p++; const v = expr(); if(!eat(')')) throw err('unclosed'); return v; }
    if(k.k === 'id'){
      p++;
      if(k.v === 'pi') return Math.PI;
      if(k.v === 'e') return Math.E;
      if(k.v === 'ans') return S.ans;
      if(k.v === 'x'){ if(x === undefined) throw soft(err('noX')); return x; }
      if(FUNCS[k.v]){
        let a;
        if(peek() && peek().k === '('){ p++; a = expr(); if(!eat(')')) throw err('unclosed'); }
        else a = unary();
        return FUNCS[k.v](a);
      }
      throw soft(err('unknownWord', k.v));
    }
    throw soft(err('notUnderstood'));
  }
  const r = expr();
  if(p < tk.length) throw soft(err('notUnderstood'));
  return r;
}

function fmt(n){
  if(typeof n !== 'number' || !isFinite(n)) throw err('undef');
  if(Math.abs(n) < 1e-12) return "0";
  if(Number.isInteger(n) && Math.abs(n) < 1e21){
    let s = String(n);
    if(Math.abs(n) >= 10000) s = s.replace(/\B(?=(\d{3})+(?!\d))/g, " ");
    return s;
  }
  return String(parseFloat(n.toPrecision(12)));
}

function normalize(raw){
  let s = raw.toLowerCase().replace(/[ʻʼ’‘`´]/g, "'");
  const N = '(\\d+(?:[.,]\\d+)?)';
  const R = (re, rep) => { s = s.replace(new RegExp(re, 'g'), rep); };
  R(N + '\\s*ning\\s*' + N + '\\s*foiz\\w*', '($1*$2/100)');
  R(N + '\\s*(?:процент\\w* от|% от)\\s*' + N, '($1*$2/100)');
  R('квадратн\\w* корен\\w* из\\s*' + N, 'sqrt($1)');
  R('кубическ\\w* корен\\w* из\\s*' + N, 'cbrt($1)');
  R(N + '\\s*(?:%|percent)\\s*of\\s*' + N, '($1*$2/100)');
  R(N + '\\s*ning\\s*kvadrat\\s*ildiz\\w*', 'sqrt($1)');
  R('kvadrat\\s*ildiz\\w*\\s*' + N, 'sqrt($1)');
  R('square\\s*root\\s*(?:of\\s*)?' + N, 'sqrt($1)');
  R('cube\\s*root\\s*(?:of\\s*)?' + N, 'cbrt($1)');
  R(N + '\\s*ning\\s*kvadrat\\w*', '($1)^2');
  R(N + '\\s*squared', '($1)^2');
  R(N + '\\s*ning\\s*kub\\w*', '($1)^3');
  R(N + '\\s*cubed', '($1)^3');
  R('factorial\\s*(?:of\\s*)?' + N, '$1!');
  R(N + '\\s*factorial', '$1!');
  R('\\bequals?\\b', '=');
  R("\\b(hisobla\\w*|yech\\w*|topib|ber|nechaga|necha|nechi|bo'ladi|teng|javobi|javob|nimaga|calculate|compute|solve|find|what's|whats|what|is|the|answer|please|tell|me)\\b", ' ');
  s = s.replace(/\?/g, " ");
  s = s.replace(/ko'paytir\w*|ko'paytma\w*|karra|multiplied\s*by|\btimes\b/g, "*")
       .replace(/bo'l(?:ish|sa|insa|ib)\w*|divided\s*by|\bover\b/g, "/")
       .replace(/qo'shish|qo'shsa|qo'sh\b|plyus|\bplus\b/g, "+")
       .replace(/ayirish|ayirsa|ayir\b|\bminus\b/g, "-")
       .replace(/daraja\w*|to\s*the\s*power\s*(?:of)?/g, "^");
  s = s.replace(/×/g, "*").replace(/÷/g, "/").replace(/[−–—]/g, "-").replace(/√/g, "sqrt").replace(/π/g, "pi").replace(/\*\*/g, "^");
  s = s.replace(/(\d)\s*[x]\s*(?=\d)/g, "$1*");
  s = s.replace(/(\d)\s*:\s*(?=\d)/g, "$1/");
  s = s.replace(/(\d),(\d)/g, "$1.$2");
  return s.trim();
}

function solveEquation(low){
  const parts = low.split('=');
  if(parts.length !== 2) throw err('eqOne');
  const L = parts[0], Rr = parts[1];
  const f = x => evaluate(L, x) - evaluate(Rr, x);
  const c = f(0), pp = f(1), mm = f(-1);
  const a = (pp + mm) / 2 - c, b = (pp - mm) / 2;
  const chk = x => Math.abs(a*x*x + b*x + c - f(x)) < 1e-7 * (1 + Math.abs(f(x)));
  if(!chk(2) || !chk(3) || !chk(-4)) throw err('eqDeg');
  const z = v => Math.abs(v) < 1e-10;
  const out = [];
  if(z(a)){
    if(z(b)) return [{t:'text', v: t(z(c) ? 'eqInf' : 'eqNone')}];
    out.push({t:'step', v: t('eqLinear') + " " + fmt(b) + "·x " + (c<0?"− ":"+ ") + fmt(Math.abs(c)) + " = 0"});
    const x = -c / b; S.ans = x;
    out.push({t:'result', l:'x =', v:fmt(x)});
    return out;
  }
  out.push({t:'step', v: t('eqQuad') + " " + fmt(a) + "x² " + (b<0?"− ":"+ ") + fmt(Math.abs(b)) + "x " + (c<0?"− ":"+ ") + fmt(Math.abs(c)) + " = 0"});
  const D = b*b - 4*a*c;
  out.push({t:'step', v: t('disc') + ": D = b² − 4ac = " + fmt(D)});
  if(z(D)){
    const x = -b / (2*a); S.ans = x;
    out.push({t:'result', l:'x =', v:fmt(x)});
  } else if(D > 0){
    const r = Math.sqrt(D), x1 = (-b - r) / (2*a), x2 = (-b + r) / (2*a);
    S.ans = x2;
    out.push({t:'result', l:'x₁ =', v:fmt(Math.min(x1,x2))});
    out.push({t:'result', l:'x₂ =', v:fmt(Math.max(x1,x2))});
  } else {
    const re = -b / (2*a), im = Math.sqrt(-D) / (2*Math.abs(a));
    out.push({t:'text', v:t('dNeg')});
    out.push({t:'result', l:'x =', v: fmt(re) + " ± " + fmt(im) + "i"});
  }
  return out;
}

function tryMath(raw){
  try{
    let low = normalize(raw).replace(/=\s*$/, "").trim();
    if(!low) throw err('writeMath');
    if(low.includes('=')) return solveEquation(low);
    const v = evaluate(low);
    const r = fmt(v); S.ans = v;
    return [{t:'step', v: low.replace(/\*/g,'×').replace(/\//g,'÷')}, {t:'result', l:t('answer'), v:r}];
  }catch(e){
    if(e.soft || !e.math) return null;
    return [{t:'text', v: t(e.k, ...e.a)}];
  }
}

/* ============ Chat brain (rule-based, offline) ============ */
const MON = { uz:["yanvar","fevral","mart","aprel","may","iyun","iyul","avgust","sentabr","oktabr","noyabr","dekabr"],
              en:["January","February","March","April","May","June","July","August","September","October","November","December"] };
const DAY = { uz:["yakshanba","dushanba","seshanba","chorshanba","payshanba","juma","shanba"],
              en:["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"] };
let userName = '';
const pick = a => a[Math.floor(Math.random() * a.length)];

const R = {
  greet:{ uz:["Salom{n}! Men TB.AI man. Misol yeching yoki shunchaki gaplashing.","Assalomu alaykum{n}! Bugun nima qilamiz?"],
          en:["Hello{n}! I'm TB.AI. Give me a math problem or just chat.","Hi{n}! What shall we do today?"] },
  how:{ uz:["Zo'r, rahmat! O'zingiz-chi, qandaysiz?","Yaxshi — hisob-kitob qilib turibman. Sizda nima gap?"],
        en:["Doing great, thanks! How about you?","All good — crunching numbers. How are you?"] },
  who:{ uz:["Men TB.AI — The Best AI. Internetsiz ishlaydigan, gaplasha va matematik misollarni yecha oladigan yordamchiman (v0.0.4)."],
        en:["I'm TB.AI — The Best AI. An offline assistant that can chat and solve math problems (v0.0.4)."] },
  creator:{ uz:["Meni sizning g'oyangiz asosida yaratishgan. Men hali yosh loyihaman — v0.0.4."],
            en:["I was built from your idea, as a young project — v0.0.4."] },
  tbmean:{ uz:["TB.AI — «The Best AI», ya'ni «Eng yaxshi AI» degani. Hali yo'lning boshida, lekin harakat qilaman!"],
           en:["TB.AI stands for “The Best AI”. I'm still at the start of the road, but I'm doing my best!"] },
  weather:{ uz:["Men internetsiz ishlayman, shuning uchun ob-havoni ayta olmayman. Derazaga qarab ko'ring."],
            en:["I work offline, so I can't check the weather. A quick look out the window will do!"] },
  thanks:{ uz:["Marhamat! Yana nimadir bormi?","Arzimaydi{n}!"], en:["You're welcome!","Anytime{n}!"] },
  bye:{ uz:["Xayr{n}! Yana kelib turing.","Ko'rishguncha!"], en:["Bye{n}! Come back anytime.","See you later!"] },
  joke:{ uz:["Nega matematika kitobi xafa edi? Chunki unda juda ko'p «muammo» bor edi.",
             "Nol sakkizga dedi: «Qanday chiroyli kamar!»",
             "Parallel chiziqlarning umumiy tomonlari ko'p, afsuski, ular hech qachon uchrashmaydi."],
         en:["Why was the math book sad? It had too many problems.",
             "Zero told eight: “Nice belt!”",
             "Parallel lines have so much in common. It's a shame they'll never meet."] },
  fact:{ uz:["Al-Xorazmiy kitobi nomidagi «al-jabr» so'zidan «algebra» atamasi, uning ismidan esa «algoritm» so'zi kelib chiqqan.",
             "111 111 111 × 111 111 111 = 12 345 678 987 654 321.",
             "1 dan 100 gacha sonlar yig'indisi 5050 — buni yosh Gauss tez topgan ekan."],
         en:["The word “algebra” comes from al-Khwarizmi's book title (al-jabr), and “algorithm” comes from his name.",
             "111,111,111 × 111,111,111 = 12,345,678,987,654,321.",
             "The sum of 1 to 100 is 5050 — young Gauss reportedly found it in seconds."] },
  version:{ uz:["TB.AI — versiya 0.0.4"], en:["TB.AI — version 0.0.4"] },
  offline:{ uz:["Ha, men to'liq internetsiz ishlayman — hamma narsa qurilmangizning o'zida hisoblanadi."],
            en:["Yes, I work fully offline — everything is computed right on your device."] },
  age:{ uz:["Men juda yoshman — hozircha 0.0.2 versiyaman."], en:["I'm very young — only version 0.0.3 so far."] },
  compliment:{ uz:["Rahmat! Nomimda ham «The Best» bor-ku 😄","Xushomad uchun rahmat, harakat qilaman!"],
               en:["Thanks! It's in my name — “The Best” 😄","Thank you, I'll keep trying!"] },
  langAbility:{ uz:["Men o'zbek va ingliz tillarida gaplasha olaman."], en:["I can chat in both Uzbek and English."] },
  help:{ uz:["Men qila olaman:\n• Suhbat: salomlashish, latifa, qiziq fakt, vaqt va sana\n• Hisob: 12*(3+4)-5, 17 mod 5, 5!, 50%\n• Funksiyalar: sqrt, sin, cos, tan, log, ln, abs, exp; pi, e, ans\n• Tenglamalar: 2x+3=11, x^2-5x+6=0\n• So'z bilan: «200 ning 15 foizi», «16 ning kvadrat ildizi»\n• Til: «inglizcha gapir» deb yozing"],
         en:["Here's what I can do:\n• Chat: greetings, jokes, fun facts, time and date\n• Math: 12*(3+4)-5, 17 mod 5, 5!, 50%\n• Functions: sqrt, sin, cos, tan, log, ln, abs, exp; pi, e, ans\n• Equations: 2x+3=11, x^2-5x+6=0\n• In words: “15% of 200”, “square root of 144”\n• Language: say “speak Uzbek”"] }
};

// Russian offline response pack for common conversation topics.
const RU_REPLY = {
 greet:["Привет! Я TB.AI. Можем поговорить или решить пример.","Здравствуйте! Чем могу помочь?"],
 how:["Спасибо, всё хорошо! А у вас?","Готов помочь — что обсудим?"],
 who:["Я TB.AI — офлайн-помощник. Умею вести простой диалог и решать некоторые математические задачи."],
 creator:["TB.AI создан на основе идеи пользователя. Это небольшой офлайн-проект."],
 tbmean:["TB.AI означает The Best AI — «лучший искусственный интеллект»."],
 weather:["Я работаю без интернета, поэтому не могу проверить текущую погоду."],
 thanks:["Пожалуйста! Чем ещё помочь?","Не за что!"],
 bye:["Пока! До встречи.","До свидания!"],
 joke:["Почему учебник математики грустил? В нём было слишком много задач.","Ноль сказал восьмёрке: «Какой красивый пояс!»"],
 fact:["Слово «алгебра» связано с названием труда учёного Аль-Хорезми.","Сумма чисел от 1 до 100 равна 5050."],
 version:["TB.AI — версия 0.0.4."], offline:["Да, базовые функции работают офлайн прямо на устройстве."],
 age:["Я программа, поэтому человеческого возраста у меня нет."],
 compliment:["Спасибо! Я постараюсь быть полезнее."],
 langAbility:["Сейчас доступны узбекский, русский и английский интерфейсы."],
 help:["Я умею решать арифметические выражения, проценты, линейные и квадратные уравнения, а также поддерживаю простой офлайн-диалог."]
};
const EXTRA_REPLY = {
  uz: {
    greet:["Assalomu alaykum! 😊 Yaxshimisiz? Men TB.AI — siz bilan suhbatlashish, savollarga javob berish va misollarni yechishga yordam beradigan oflayn yordamchiman. Bugun nima haqida gaplashamiz?","Salom! Xush kelibsiz. Dars, matematika, fan, tarix yoki oddiy suhbat — istalgan mavzuda savol berib ko‘ring."],
    how:["Rahmat, yaxshi! 😊 Sizning kayfiyatingiz qanday? Bugun maktab, qiziqishlaringiz yoki boshqa biror mavzu haqida gaplashishimiz mumkin.","Hammasi joyida — yordam berishga tayyorman. Sizda nima yangilik? Biror narsani bilmoqchi bo‘lsangiz, bemalol so‘rang."],
    creator:["TB.AI — sizning g‘oyangiz asosida ishlab chiqilayotgan kichik loyiha. Ushbu HTML versiya 2026-yil 27-oktabrda 0.0.4 sifatida yangilandi. U JavaScript qoidalari va oldindan yozilgan javoblar yordamida ishlaydi; u katta neyron tarmoq modeli emas."],
    who:["Men TB.AI — The Best AI. Men ushbu sahifadagi JavaScript dasturi orqali ishlaydigan oflayn yordamchiman. Oddiy suhbat qila olaman, ayrim umumiy savollarga javob beraman va matematik ifodalarni hisoblayman. Men haqiqiy inson emasman va ba'zi savollarda adashishim mumkin. Nima haqida gaplashamiz?"],
    meaningLife:["Bu savolga odamlar turlicha javob berishadi. Ko‘pchilik uchun hayotning mazmuni — yaqinlarga g‘amxo‘rlik qilish, o‘rganish, foydali ish qilish va o‘z oldiga maqsad qo‘yish. Har kim o‘z tajribasi va qadriyatlariga ko‘ra ma'no topadi. Sizningcha-chi?"],
    school:["Bilim odamga atrofdagi dunyoni tushunish, muammolarni hal qilish va mustaqil qaror qabul qilishda yordam beradi. O‘qishda hamma narsani birdan bilish shart emas: savol berish, mashq qilish va xatolardan o‘rganish muhim. Qaysi fan sizga qiziq?"],
    science:["Ilmiy savollarni sodda qilib tushuntirishga harakat qilaman. Masalan, Quyosh — Yerga eng yaqin yulduz; Yer uning atrofida aylanadi. Gravitatsiya esa jismlarning bir-birini tortish hodisasidir. Aniqroq qaysi mavzu sizni qiziqtiryapti?"],
    history:["Tarix o‘tmishdagi odamlar, davlatlar va voqealarni o‘rganadi. Masalan, Muhammad al-Xorazmiy matematika rivojiga katta hissa qo‘shgan olim bo‘lib, algebra tarixida muhim o‘rin tutadi. Istasangiz, biror tarixiy shaxs yoki davr haqida alohida so‘rang."],
    advice:["Keling, vaziyatni kichik qadamlarga ajratamiz. Avval aynan nima bezovta qilayotganini aniqlang, keyin bajarish mumkin bo‘lgan eng kichik qadamni tanlang. Agar zerikayotgan bo‘lsangiz, sayr, sevimli mashg‘ulot yoki qisqa tanaffus yordam berishi mumkin. Xohlasangiz, nima bo‘lganini ayting — birga o‘ylab ko‘ramiz."],
    help:["Men quyidagilarda yordam bera olaman:\n• Oddiy suhbat: salomlashish, hol-ahvol, minnatdorchilik va maslahat.\n• Umumiy bilim: maktab, ilm-fan, tarix va qiziqarli faktlar.\n• Matematika: arifmetika, foizlar, darajalar, ildizlar va ayrim chiziqli/kvadrat tenglamalar.\n• Til: o‘zbekcha, ruscha va inglizcha oddiy suhbat.\n• Sana/vaqt: qurilmangizdagi sana va vaqt.\n\nEslatma: men internetdan ma'lumot qidirmayman; barcha mavzularni bilmayman. Bilmasam, buni aytishim kerak."],
    offline:["Ha, asosiy funksiyalar internet talab qilmaydi: hisob-kitoblar va ichki javoblar telefoningizdagi brauzerda bajariladi. Lekin men internetdan yangi ma'lumot qidira olmayman va katta AI modelidek istalgan savolga javob bera olmayman."],
    langAbility:["TB.AI interfeysida o‘zbek, rus va ingliz tillarini tanlashingiz mumkin. Sozlamalar uchun yuqoridagi uch nuqtani bosing. Suhbatni shu tillarda yozib ko‘ring; javob sifati til va savol turiga qarab farq qilishi mumkin."],
    version:["TB.AI v0.0.4. Bu loyiha 2026-yil 27-oktabrda yangilandi. U HTML, CSS va JavaScript yordamida yaratilgan: HTML tuzilmani, CSS ko‘rinishni, JavaScript esa suhbat qoidalari va matematik hisoblarni boshqaradi."],
    age:["Men inson emasman, shuning uchun haqiqiy yoshim yo‘q. TB.AI loyihasining ushbu 0.0.4 versiyasi 2026-yil 27-oktabrda tayyorlangan."],
    tbmean:["TB.AI — “The Best AI” iborasining qisqartmasi, ya'ni “Eng yaxshi sun'iy intellekt” degan ma'noni anglatadi. Bu loyiha hozircha kichik, oflayn yordamchi bo‘lib, asta-sekin takomillashtirilmoqda."],
    joke:["Bir o‘quvchi kalkulyatorga dedi: “Senga ishonish mumkinmi?” Kalkulyator javob berdi: “Albatta, men hisob-kitobni yaxshi ko‘raman — lekin avval sonlarni to‘g‘ri kiriting!” 😄","O‘qituvchi: “Nega uy vazifang yo‘q?” O‘quvchi: “Daftarim uyda qoldi.” O‘qituvchi: “Sen ham uyda qolishing kerak edi!” 😄"],
    fact:["Qiziqarli fakt: sakkizoyoqning uchta yuragi bor. Yana bir fakt: asalari raqsga o‘xshash harakatlar orqali boshqa asalarilarga oziqa manbasi qayerdaligini bildirishi mumkin. Qaysi mavzuda fakt eshitishni xohlaysiz — tabiat, kosmos yoki tarix?"]
  },
  ru: {
    greet:["Здравствуйте! 😊 Как у вас дела? Я TB.AI — офлайн-помощник для простого общения, ответов на некоторые вопросы и решения математических примеров. О чём поговорим сегодня?","Привет! Рад помочь. Можно спросить о школе, математике, науке, истории или просто поболтать."],
    how:["Спасибо, всё хорошо! 😊 А как ваше настроение? Можем поговорить об учёбе, интересах или любой другой теме.","Я готов помочь. Что нового у вас? Задавайте вопрос — постараюсь объяснить понятно."],
    creator:["TB.AI — небольшой проект, созданный на основе идеи пользователя. Эта HTML-версия обновлена до 0.0.4 27 октября 2026 года. Она работает с помощью правил JavaScript и заранее подготовленных ответов; это не большая нейросетевая модель."],
    who:["Я TB.AI — The Best AI. Я работаю как программа JavaScript в этой веб-странице. Я могу поддерживать простой диалог, отвечать на некоторые общие вопросы и считать математические выражения. Я не человек и могу ошибаться. О чём поговорим?"],
    meaningLife:["Люди отвечают на этот вопрос по-разному. Для многих смысл жизни связан с заботой о близких, обучением, полезными делами и личными целями. Каждый находит свой ответ через опыт и ценности. А что вы думаете об этом?"],
    school:["Знания помогают понимать мир, решать задачи и принимать самостоятельные решения. Необязательно знать всё сразу: важно задавать вопросы, практиковаться и учиться на ошибках. Какой школьный предмет вам интереснее всего?"],
    science:["Я постараюсь объяснять научные темы простыми словами. Например, Солнце — ближайшая к Земле звезда, а Земля вращается вокруг него. Гравитация — это взаимное притяжение тел. Какую тему хотите разобрать подробнее?"],
    history:["История изучает людей, государства и события прошлого. Например, учёный Мухаммад аль-Хорезми внёс большой вклад в развитие математики и занимает важное место в истории алгебры. Можете спросить о конкретной личности или эпохе."],
    advice:["Давайте разделим ситуацию на небольшие шаги. Сначала определите, что именно вас беспокоит, затем выберите один посильный шаг. Если скучно, может помочь прогулка, любимое занятие или небольшой перерыв. Если хотите, расскажите подробнее — попробуем разобраться вместе."],
    help:["Я могу помочь с:\n• Простым общением и приветствиями.\n• Общими сведениями о школе, науке и истории.\n• Математикой: арифметикой, процентами, степенями, корнями и некоторыми линейными/квадратными уравнениями.\n• Простым общением на узбекском, русском и английском.\n• Датой и временем устройства.\n\nВажно: я не ищу информацию в интернете и не знаю абсолютно всё. Если не знаю ответ, лучше сказать об этом честно."],
    offline:["Да, основные функции работают без интернета: вычисления и встроенные ответы выполняются в браузере телефона. Но я не могу искать новые сведения в сети и не отвечаю на любые вопросы так, как большая AI-модель."],
    langAbility:["В интерфейсе TB.AI можно выбрать узбекский, русский и английский языки. Нажмите на три точки вверху, чтобы открыть настройки. Качество ответа зависит от языка и темы вопроса."],
    version:["TB.AI v0.0.4. Проект обновлён 27 октября 2026 года. Он создан с помощью HTML, CSS и JavaScript: HTML задаёт структуру, CSS отвечает за оформление, а JavaScript управляет правилами диалога и математическими вычислениями."],
    age:["Я программа, поэтому у меня нет человеческого возраста. Версия проекта TB.AI 0.0.4 подготовлена 27 октября 2026 года."],
    tbmean:["TB.AI — сокращение от “The Best AI”, то есть «Лучший искусственный интеллект». Пока это небольшой офлайн-помощник, который постепенно развивается."],
    joke:["Учитель спрашивает: «Почему ты не сделал домашнее задание?» Ученик: «Тетрадь осталась дома». Учитель: «Тебе тоже следовало остаться дома!» 😄","Калькулятор никогда не спорит — он просто показывает результат. Но иногда ему тоже нужен правильный ввод! 😄"],
    fact:["Интересный факт: у осьминога три сердца. А пчёлы могут движениями, похожими на танец, сообщать другим пчёлам, где находится источник пищи. Хотите факт о природе, космосе или истории?"]
  },
  en: {
    greet:["Hello! 😊 How are you? I'm TB.AI, an offline helper for simple conversation, some general questions, and math problems. What would you like to talk about today?","Hi! Welcome. Ask me about school, math, science, history, or just start a casual chat."],
    how:["Thanks, I'm ready to help! 😊 How are you feeling today? We can talk about school, your interests, or another topic.","I'm here to help. What's new with you? Ask away and I'll try to explain clearly."],
    creator:["TB.AI is a small project developed from the user's idea. This HTML version was updated to 0.0.5 on October 27, 2026. It uses JavaScript rules and prepared responses; it is not a large neural-network model."],
    who:["I'm TB.AI — The Best AI. I run as a JavaScript program inside this webpage. I can have simple conversations, answer some general questions, and calculate math expressions. I'm not a person and I can make mistakes. What shall we talk about?"],
    meaningLife:["People answer this in different ways. For many, meaning comes from caring for others, learning, doing useful things, and setting personal goals. Everyone develops their own view through experience and values. What do you think?"],
    school:["Knowledge helps us understand the world, solve problems, and make independent decisions. You don't need to know everything at once: asking questions, practising, and learning from mistakes all matter. Which subject do you enjoy most?"],
    science:["I'll try to explain science simply. For example, the Sun is the closest star to Earth, and Earth travels around it. Gravity is the attraction between objects. Which topic would you like to explore further?"],
    history:["History studies people, societies, and events from the past. For example, the scholar Muhammad al-Khwarizmi made important contributions to mathematics and the history of algebra. Ask me about a particular person or period."],
    advice:["Let's break the situation into small steps. First, identify what's bothering you, then choose one manageable next step. If you're bored, a walk, a hobby, or a short break may help. If you'd like, tell me more and we can think it through together."],
    help:["I can help with:\n• Simple conversation and greetings.\n• General school, science, and history facts.\n• Math: arithmetic, percentages, powers, roots, and some linear/quadratic equations.\n• Simple conversation in Uzbek, Russian, and English.\n• Your device's date and time.\n\nNote: I don't search the internet and I don't know everything. If I don't know something, I should say so."],
    offline:["Yes, basic features work offline: calculations and built-in responses run in your phone's browser. But I can't search the web for new information or answer every question like a large AI model."],
    langAbility:["TB.AI has Uzbek, Russian, and English interface options. Tap the three dots at the top to open settings. Answer quality may vary by language and topic."],
    version:["TB.AI v0.0.4. This project was updated on October 27, 2026. It was built with HTML, CSS, and JavaScript: HTML defines structure, CSS handles appearance, and JavaScript runs the conversation rules and math calculations."],
    age:["I'm software, so I don't have a human age. The TB.AI 0.0.4 project version was prepared on October 27, 2026."],
    tbmean:["TB.AI stands for “The Best AI”. For now, it's a small offline assistant that is being improved step by step."],
    joke:["Why did the student bring a ladder to class? Because they wanted to go to high school! 😄","A calculator never argues; it just gives a result. But it still needs the right numbers entered! 😄"],
    fact:["Fun fact: an octopus has three hearts. Honeybees can also use dance-like movements to tell other bees where food is located. Would you like a fact about nature, space, or history?"]
  }
};

const INTENTS = [
  ['toEn', /inglizcha\s*(gapir|so'zlash|yoz)|ingliz tiliga/, /^(please\s+)?(speak|switch to|talk|reply)\s+(in\s+)?english/],
  ['toRu', /ruscha\s*(gapir|so'zlash|yoz)|rus tiliga/, /^(please\s+)?(speak|switch to|talk|reply)\s+(in\\s+)?russian/, /по-русски|на русском/],
  ['toUz', /o'zbekcha\s*(gapir|so'zlash|yoz)|o'zbek tiliga/, /^(please\s+)?(speak|switch to|talk|reply)\s+(in\s+)?uzbek/],
  ['askname', /ismim nima|meni ismim/, /what('s| is) my name/, /как меня зовут|моё имя/],
  ['setname', /mening ismim\s+(?!nima)([^\s,.!?]+)/, /(my name is|call me)\s+(?!what)([a-z']+)/],
  ['greet', /^(salom|assalom|hayrli (tong|kun|kech)|alaykum)/, /^(hi|hello|hey|yo|good (morning|afternoon|evening))\b/, /^(привет|здравствуй|здравствуйте|доброе утро|добрый день|добрый вечер)\b/],
  ['how', /yaxshimisan|yaxshimisiz|qalaysan|qalaysiz|ahvol|nima gap|nima yangilik/, /how are you|how's it going|what's up|whats up|how do you do/, /как дела|как ты|как поживаешь/],
  ['tbmean', /tb\.?\s*(ai)?\s*nima|tb degani/, /(what does|what is|what's) tb|tb stand|meaning of tb/],
  ['who', /kimsan|kimsiz|sen kim|isming nima|ismingiz nima|isming kim/, /who are you|what are you|your name/, /кто ты|как тебя зовут/],
  ['creator', /seni kim|kim yaratgan|kim yaratdi|kim tuzgan|qachon yaratilgan/, /who (made|created|built|developed) you|your (creator|developer)|when were you created/, /кто тебя создал|когда ты создан|кто разработал/],
  ['time', /soat nech|vaqt nech|hozir vaqt/, /what time|current time|time is it|time now/, /который час|сколько времени/],
  ['date', /bugun (qaysi|nech)|sana nech|bugungi sana|qaysi kun|nechanchi/, /what('s| is) (the )?date|today's date|what day|which day/, /какое сегодня число|какой сегодня день|какая дата/],
  ['weather', /ob-?havo|havo qanday/, /weather|\brain\b/],
  ['thanks', /rahmat|tashakkur|sag'?ol|raxmat/, /thank|thx|appreciate/, /спасибо|благодарю/],
  ['bye', /xayr|ko'rishguncha|salomat bo'l/, /^bye|goodbye|see you|good night/, /пока|до свидания|увидимся/],
  ['joke', /latifa|hazil|kuldir/, /joke|make me laugh|something funny/, /анекдот|рассмеши|шутку/],
  ['fact', /qiziq fakt|qiziqarli|fakt ayt/, /fun fact|interesting fact|tell me a fact|\bfact\b/],
  ['rand', /tasodifiy son/, /random number/],
  ['version', /versiya/, /version/, /версия/],
  ['offline', /internet|oflayn|offline|onlayn/, /internet|offline|online/, /интернет|офлайн|онлайн/],
  ['age', /yoshing|necha yoshdasan|yoshingiz|qachon yaratilgansan/, /how old are you|your age|when were you made/, /сколько тебе лет/],
  ['compliment', /zo'rsan|ajoyibsan|a'lo\b|barakalla|dahosan|aqllisan/, /you('re| are) (great|awesome|smart|amazing|the best|good|cool)|good (job|bot)|well done/],
  ['langAbility', /inglizcha bilasan|ingliz tilini bilasan|qaysi til/, /do you speak|which language|what language/],
  ['help', /yordam|nima qila olasan|nimalar qila|imkoniyat/, /\bhelp\b|what can you do|capabilities|features/, /что ты умеешь|помощь|что можешь/],
  ['meaningLife', /hayot nima|hayotning ma'nosi|do'stlik nima/, /what is life|meaning of life|what is friendship/, /что такое жизнь|смысл жизни|что такое дружба/],
  ['school', /o'qish haqida|maktab nima|bilim nima|ilm nima/, /why is learning important|what is knowledge|school/, /зачем учиться|что такое знания|школа/],
  ['science', /koinot nima|quyosh nima|yer nima|gravitatsiya nima|sun'iy intellekt nima/, /what is the universe|what is the sun|what is earth|what is gravity|what is artificial intelligence/, /что такое вселенная|что такое солнце|что такое земля|гравитация|искусственный интеллект/],
  ['history', /al-xorazmiy|al xorazmiy|amir temur|navoiy kim|tarix nima/, /who was al-khwarizmi|who was amir timur|who was navoi|what is history/, /кто такой аль-хорезми|кто такой амир темур|кто такой навои|что такое история/],
  ['advice', /maslahat ber|nima qilsam bo'ladi|zerikdim|kayfiyatim yo'q/, /give me advice|what should i do|i'm bored|i am bored|i feel sad/, /дай совет|что мне делать|мне скучно|мне грустно/],
  ['thanks', /rahmat|tashakkur|sag'?ol|raxmat/, /thank|thx|appreciate/, /спасибо|благодарю/]
];

function reply(id, L, m){
  const d = new Date(), pad = n => String(n).padStart(2, '0');
  const nm = userName ? ', ' + userName : '';
  switch(id){
    case 'time': return L === 'uz' ? `Hozir soat ${pad(d.getHours())}:${pad(d.getMinutes())}.` : `It's ${pad(d.getHours())}:${pad(d.getMinutes())} right now.`;
    case 'date': return L === 'uz' ? `Bugun ${d.getFullYear()}-yil ${d.getDate()}-${MON.uz[d.getMonth()]}, ${DAY.uz[d.getDay()]}.`
                                  : `Today is ${DAY.en[d.getDay()]}, ${MON.en[d.getMonth()]} ${d.getDate()}, ${d.getFullYear()}.`;
    case 'rand': { const n = 1 + Math.floor(Math.random() * 100); return L === 'uz' ? `Tasodifiy son: ${n}` : `Random number: ${n}`; }
    case 'setname': {
      const raw = m[m.length - 1]; userName = raw.charAt(0).toUpperCase() + raw.slice(1);
      try{ localStorage.setItem('tbai_name', userName); }catch(e){}
      return L === 'uz' ? `Tanishganimdan xursandman, ${userName}!` : `Nice to meet you, ${userName}!`;
    }
    case 'askname': return userName ? (L === 'uz' ? `Sizning ismingiz ${userName}.` : `Your name is ${userName}.`)
                                    : (L === 'uz' ? "Hali ismingizni aytmadingiz. «Mening ismim ...» deb yozing." : "You haven't told me yet. Say “My name is ...”.");
    case 'toEn': setLang('en'); return "Sure — switching to English.";
    case 'toUz': setLang('uz'); return "Albatta — o'zbek tiliga o'tdim.";
    case 'toRu': setLang('ru'); return "Хорошо, теперь говорим по-русски.";
  }
  if(L === 'ru' && RU_REPLY[id]) return pick(RU_REPLY[id]);
  return pick((R[id] && R[id][L]) || STR[L].fallback).replace('{n}', nm);
}

function chat(raw){
  const s = raw.toLowerCase().replace(/[ʻʼ’‘`´]/g, "'").trim();
  const hits = [];
  for(const [id, uz, en, ru] of INTENTS){
    let m;
    if((m = uz.exec(s))) hits.push([id, 'uz', m]);
    else if((m = en.exec(s))) hits.push([id, 'en', m]);
    else if(ru && (m = ru.exec(s))) hits.push([id, 'ru', m]);
  }
  if(hits.length){
    const sw = hits.find(h => ['toEn','toUz','toRu'].includes(h[0]));
    if(sw) return [{t:'text', v: reply(sw[0], sw[1], sw[2])}];
    const use = hits.slice(0, 2);
    return use.map(h => ({t:'text', v: (EXTRA_REPLY[h[1]] && EXTRA_REPLY[h[1]][h[0]]) ? pick(EXTRA_REPLY[h[1]][h[0]]) : reply(h[0], h[1], h[2])}));
  }
  const detected = /[а-яё]/i.test(s) ? 'ru' : ( /\b(the|you|what|how|can|do|is|are|me|my|please|why|who|i|hello|hi)\b/.test(s) ? 'en' : lang );
  const knowledge = {
    uz: [ [/\b(rahmat|raxmat)\b/,"Arzimaydi! 😊 Yana savolingiz bo‘lsa, bemalol yozing."], [/\b(salom|assalom)\b/,"Assalomu alaykum! 😊 Qalaysiz? Bugun nima haqida suhbatlashamiz?"], [/isming nima|kimsan/,EXTRA_REPLY.uz.who[0]], [/nima qila olasan|yordam/,EXTRA_REPLY.uz.help[0]], [/ai nima|sun'iy intellekt nima/,"Sun’iy intellekt — kompyuter tizimlarining matnni tushunish, naqshlarni aniqlash yoki muammolarni yechish kabi vazifalarni bajarishiga oid texnologiyalar sohasi. Men esa hozircha qoidalar va tayyor javoblarga asoslangan kichik oflayn dasturman."] ],
    ru: [ [/\bпривет\b|здравствуй/,EXTRA_REPLY.ru.greet[0]], [/спасибо/,"Пожалуйста! 😊 Если есть ещё вопрос, пишите."], [/кто ты|как тебя зовут/,EXTRA_REPLY.ru.who[0]], [/что ты умеешь|помощь/,EXTRA_REPLY.ru.help[0]], [/что такое искусственный интеллект/,"Искусственный интеллект — область технологий, где компьютерные системы выполняют задачи вроде анализа текста, распознавания закономерностей и решения проблем. Я пока небольшой офлайн-скрипт с правилами и готовыми ответами."] ],
    en: [ [/\b(hi|hello)\b/,EXTRA_REPLY.en.greet[0]], [/thank you|thanks/,"You're welcome! 😊 Feel free to ask another question."], [/who are you|what are you/,EXTRA_REPLY.en.who[0]], [/what can you do|help/,EXTRA_REPLY.en.help[0]], [/what is artificial intelligence/,"Artificial intelligence is a field of technology focused on systems that perform tasks such as analysing language, finding patterns, or solving problems. I'm currently a small offline script using rules and prepared answers."] ]
  };
  for(const [re, val] of (knowledge[detected] || [])) if(re.test(s)) return [{t:'text', v:val}];
  return [{t:'text', v: pick(STR[detected].fallback)}];
}

function answer(raw){
  if(/\d|π|√|\bpi\b/i.test(raw)){
    const r = tryMath(raw);
    if(r) return r;
  }
  return chat(raw);
}

/* ============ UI ============ */
const $ = s => document.querySelector(s);
const chatEl = $('#chat'), main = $('#main'), inp = $('#inp');
const KEY = 'tbai_v004';
let history = [];
const AV = logo(28);

function save(){ try{ localStorage.setItem(KEY, JSON.stringify(history.slice(-60))); }catch(e){} }
function loadAll(){
  try{ history = JSON.parse(localStorage.getItem(KEY) || '[]'); }catch(e){ history = []; }
  try{
    S.deg = localStorage.getItem(KEY + '_deg') === '1';
    userName = localStorage.getItem('tbai_name') || '';
    const l = localStorage.getItem(KEY + '_lang'); if(l === 'en' || l === 'uz' || l === 'ru') lang = l;
  }catch(e){}
  $('#degBtn').textContent = S.deg ? 'DEG' : 'RAD';
}

function setLang(l){
  lang = l;
  try{ localStorage.setItem(KEY + '_lang', l); }catch(e){}
  applyLang();
}
function applyLang(){
  document.documentElement.lang = lang;
  inp.placeholder = t('placeholder');
  $('#newBtn').textContent = t('newBtn');
  $('#tag').textContent = t('tag');
  $('#note').textContent = t('note');
  const ml = (menuLabels && menuLabels[lang]) || {languages:'Languages',questions:'Questions',about:'About AI'};
  if($('#menuLang')) $('#menuLang').textContent = ml.languages;
  if($('#menuQuestions')) $('#menuQuestions').textContent = ml.questions;
  if($('#menuAbout')) $('#menuAbout').textContent = ml.about;
  const w = $('#welcome'); if(w || !history.length) render();
}

function welcome(){
  const d = document.createElement('div'); d.className = 'welcome'; d.id = 'welcome';
  d.innerHTML = '<div class="lg">' + logo(60) + '</div><h1 class="serif"></h1><p></p><div class="chips"></div>';
  d.querySelector('h1').textContent = t('welcomeTitle');
  d.querySelector('p').textContent = t('welcomeSub');
  const chips = d.querySelector('.chips');
  t('suggestions').forEach(q => { const b = document.createElement('button'); b.className = 'chip'; b.textContent = q; b.onclick = () => submit(q); chips.appendChild(b); });
  chatEl.appendChild(d);
}

function renderMsg(m){
  const w = document.createElement('div'); w.className = 'msg ' + m.role;
  if(m.role === 'user'){
    const b = document.createElement('div'); b.className = 'bubble'; b.textContent = m.text; w.appendChild(b);
  } else {
    const av = document.createElement('div'); av.className = 'ai-av'; av.innerHTML = AV; w.appendChild(av);
    const body = document.createElement('div'); body.className = 'ai-body';
    m.lines.forEach(l => {
      const el = document.createElement('div');
      if(l.t === 'result'){
        el.className = 'line';
        const r = document.createElement('span'); r.className = 'result';
        const sm = document.createElement('small'); sm.textContent = l.l;
        r.appendChild(sm); r.appendChild(document.createTextNode(l.v)); el.appendChild(r);
      } else {
        el.className = 'line' + (l.t === 'step' ? ' step' : '');
        el.textContent = l.v;
      }
      body.appendChild(el);
    });
    w.appendChild(body);
  }
  chatEl.appendChild(w);
  main.scrollTop = main.scrollHeight;
}

function render(){
  chatEl.innerHTML = '';
  if(!history.length) welcome(); else history.forEach(renderMsg);
}

function submit(text){
  text = (text || '').trim(); if(!text) return;
  const w = $('#welcome'); if(w) w.remove();
  const um = {role:'user', text}; history.push(um); renderMsg(um);
  inp.value = ''; autosize();
  const typing = document.createElement('div'); typing.className = 'msg';
  typing.innerHTML = '<div class="ai-av">' + AV + '</div><div class="ai-body"><div class="dots"><span></span><span></span><span></span></div></div>';
  chatEl.appendChild(typing); main.scrollTop = main.scrollHeight;
  setTimeout(() => {
    typing.remove();
    const am = {role:'ai', lines: answer(text)};
    history.push(am); renderMsg(am); save();
  }, 350 + Math.random() * 400);
}

function autosize(){ inp.style.height = 'auto'; inp.style.height = Math.min(inp.scrollHeight, 140) + 'px'; }

inp.addEventListener('input', autosize);
inp.addEventListener('keydown', e => { if(e.key === 'Enter' && !e.shiftKey){ e.preventDefault(); submit(inp.value); } });
$('#sendBtn').onclick = () => submit(inp.value);
$('#newBtn').onclick = () => { history = []; save(); render(); inp.focus(); };
$('#degBtn').onclick = () => {
  S.deg = !S.deg; $('#degBtn').textContent = S.deg ? 'DEG' : 'RAD';
  try{ localStorage.setItem(KEY + '_deg', S.deg ? '1' : '0'); }catch(e){}
};

const menuLabels = {
 uz:{languages:'Tillar',questions:'Qanday savollarga javob beradi?',about:'AI haqida',title:'Sozlamalar',choose:'Tilni tanlang',questionTitle:'Savol namunalari va imkoniyatlar',aboutTitle:'TB.AI haqida',close:'Yopish'},
 ru:{languages:'Языки',questions:'На какие вопросы отвечает?',about:'Об ИИ',title:'Настройки',choose:'Выберите язык',questionTitle:'Примеры вопросов и возможности',aboutTitle:'О TB.AI',close:'Закрыть'},
 en:{languages:'Languages',questions:'What can it answer?',about:'About AI',title:'Settings',choose:'Choose a language',questionTitle:'Example questions and abilities',aboutTitle:'About TB.AI',close:'Close'}
};
function openSettingsPanel(panel){
  const labels=menuLabels[lang]||menuLabels.uz, content=$('#settingsContent');
  $('#settingsTitle').textContent=labels.title; content.innerHTML='';
  if(panel==='languages'){
    const p=document.createElement('p');p.textContent=labels.choose;content.appendChild(p);
    const row=document.createElement('div');row.className='lang-options';
    [['uz','🇺🇿 O‘zbekcha'],['ru','🇷🇺 Русский'],['en','🇬🇧 English']].forEach(([code,name])=>{const b=document.createElement('button');b.textContent=name;b.className=lang===code?'active':'';b.onclick=()=>{setLang(code);$('#settingsShade').hidden=true;$('#settingsMenu').hidden=true;};row.appendChild(b)});content.appendChild(row);
  } else if(panel==='questions'){
    const h=document.createElement('h3');h.textContent=labels.questionTitle;content.appendChild(h);
    const data={uz:[['Salom','Assalomu alaykum! Qalaysiz?'],['Qalaysan?','Rahmat, yaxshi! Siz-chi?'],['Kimsan?','TB.AI — oflayn suhbat va hisoblash yordamchisi.'],['Nima qila olasan?','Oddiy suhbat, umumiy bilimlar va matematika.'],['200 ning 15 foizi','30'],['2x + 3 = 11','x = 4'],['Quyosh nima?','Yerga eng yaqin yulduz.'],['Kim yaratgan?','Foydalanuvchi g‘oyasi asosidagi HTML/CSS/JavaScript loyiha.'],['Qachon yangilangan?','v0.0.4 — 2026-yil 27-oktabr.']],ru:[['Привет','Здравствуйте! Как дела?'],['Как дела?','Спасибо, хорошо! А у вас?'],['Кто ты?','TB.AI — офлайн-помощник для простого общения и вычислений.'],['Что ты умеешь?','Простой диалог, общие знания и математика.'],['15% от 200','30'],['2x + 3 = 11','x = 4'],['Что такое Солнце?','Ближайшая к Земле звезда.'],['Кто создал?','HTML/CSS/JavaScript-проект на основе идеи пользователя.'],['Какая версия?','v0.0.4 — обновление от 27 октября 2026 года.']],en:[['Hello','Hello! How are you?'],['How are you?','Thanks, I’m ready to help!'],['Who are you?','TB.AI — an offline assistant for simple chat and calculations.'],['What can you do?','Simple conversation, general facts, and math.'],['15% of 200','30'],['2x + 3 = 11','x = 4'],['What is the Sun?','The closest star to Earth.'],['Who created you?','An HTML/CSS/JavaScript project based on the user’s idea.'],['What version?','v0.0.4 — updated October 27, 2026.']]};
    const list=document.createElement('div');list.className='qa-list';data[lang].forEach(([q,a])=>{const r=document.createElement('div');r.className='qa-row';const b=document.createElement('b');b.textContent=q;const sp=document.createElement('span');sp.textContent=a;r.append(b,sp);r.onclick=()=>{ $('#settingsShade').hidden=true; submit(q); };r.style.cursor='pointer';list.appendChild(r)});content.appendChild(list);
    const note=document.createElement('p');note.style.marginTop='12px';note.textContent=lang==='uz'?'Namunani bosib, uni suhbatda sinab ko‘ring. Bu ro‘yxat barcha mumkin bo‘lgan savollarni anglatmaydi.':lang==='ru'?'Нажмите на пример, чтобы проверить его в чате. Список не означает, что помощник знает всё.':'Tap an example to try it in chat. This list does not mean the assistant knows everything.';content.appendChild(note);
  } else {
    const h=document.createElement('h3');h.textContent=labels.aboutTitle;content.appendChild(h);
    const p=document.createElement('p');p.textContent=EXTRA_REPLY[lang].version[0];content.appendChild(p);
    const ul=document.createElement('ul');const lines=lang==='uz'?['Yaratilgan texnologiyalar: HTML, CSS va JavaScript.','Ishlash usuli: brauzer ichidagi qoidalar, tayyor javoblar va matematik hisoblash.','Versiya: 0.0.4.','Cheklov: katta neyron tarmoq emas; internetdan qidirmaydi va hamma savolga javob bera olmaydi.']:lang==='ru'?['Технологии: HTML, CSS и JavaScript.','Принцип работы: правила, готовые ответы и математические вычисления в браузере.','Версия: 0.0.4.','Ограничение: это не большая нейросеть; она не ищет в интернете и не знает ответ на любой вопрос.']:['Technologies: HTML, CSS, and JavaScript.','How it works: browser-based rules, prepared responses, and math calculations.','Version: 0.0.4.','Limitation: it is not a large neural network, does not search the web, and cannot answer every question.'];lines.forEach(x=>{const li=document.createElement('li');li.textContent=x;ul.appendChild(li)});content.appendChild(ul);
  }
  $('#settingsMenu').hidden=true;$('#settingsShade').hidden=false;
}
$('#settingsBtn').onclick=()=>{$('#settingsMenu').hidden=!$('#settingsMenu').hidden};
$('#settingsMenu').querySelectorAll('button[data-panel]').forEach(b=>b.onclick=()=>openSettingsPanel(b.dataset.panel));
$('#closeSettings').onclick=()=>$('#settingsShade').hidden=true;
$('#settingsShade').addEventListener('click',e=>{if(e.target.id==='settingsShade')$('#settingsShade').hidden=true});
document.addEventListener('click',e=>{if(!e.target.closest('.settings-wrap'))$('#settingsMenu').hidden=true});
$('#hLogo').innerHTML = logo(32);
$('#fav').href = 'data:image/svg+xml,' + encodeURIComponent(logo(64, '#C96442'));
loadAll(); applyLang(); render();
</script>
</body>
</html>


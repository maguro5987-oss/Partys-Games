<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<title>パーティーBOX</title>
<link href="https://fonts.googleapis.com/css2?family=M+PLUS+Rounded+1c:wght@500;800&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent}
body{font-family:'M PLUS Rounded 1c',sans-serif;background:linear-gradient(160deg,#ffe3f1,#e0f4ff 60%,#fff6d6);background-attachment:fixed;min-height:100vh;color:#433;user-select:none;-webkit-user-select:none}
#app{max-width:520px;margin:0 auto;padding:12px 12px 40px}
.hd{display:flex;align-items:center;gap:10px;margin-bottom:12px}
.hd h2{flex:1;font-size:20px;font-weight:800}
.bk{border:none;background:#fff;border-radius:50%;width:42px;height:42px;font-size:20px;box-shadow:0 3px 0 #0002;font-weight:800;color:#ff5fa2}
.title{text-align:center;font-size:32px;font-weight:800;color:#ff5fa2;text-shadow:3px 3px 0 #fff,5px 5px 0 #ffd23f;margin:16px 0 4px}
.sub{text-align:center;font-size:13px;margin-bottom:18px;color:#866}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.card{background:#fff;border-radius:20px;padding:14px 8px;text-align:center;box-shadow:0 5px 0 var(--c);border:3px solid var(--c);cursor:pointer}
.card:active{transform:translateY(4px);box-shadow:0 1px 0 var(--c)}
.card .e{font-size:38px}.card b{display:block;font-size:15px;margin-top:4px}.card small{font-size:11px;color:#977}
.box{background:#fff;border-radius:22px;padding:18px;box-shadow:0 6px 0 #0001;text-align:center;margin-bottom:14px}
.btn{display:inline-block;border:none;font-family:inherit;font-weight:800;font-size:18px;padding:14px 24px;border-radius:999px;background:#ff5fa2;color:#fff;box-shadow:0 5px 0 #d43c7f;margin:6px;cursor:pointer}
.btn:active{transform:translateY(4px);box-shadow:0 1px 0 #d43c7f}
.btn.b{background:#3fa9ff;box-shadow:0 5px 0 #1f7fd0}.btn.y{background:#ffc928;color:#543;box-shadow:0 5px 0 #d9a300}.btn.g{background:#3ccf8e;box-shadow:0 5px 0 #23a46c}
.btn.s{font-size:15px;padding:9px 16px}.btn:disabled{opacity:.35;pointer-events:none}
.big{font-size:42px;font-weight:800;margin:12px 0;word-break:break-all}
.mid{font-size:22px;font-weight:800;margin:8px 0}
.note{font-size:13px;color:#866;margin:6px 0;line-height:1.7}
.num{display:flex;align-items:center;justify-content:center;gap:14px;margin:6px 0 12px}
.num span{font-size:36px;font-weight:800;min-width:60px}
.bd{display:grid;gap:2px;margin:0 auto 10px;width:100%;touch-action:manipulation}
.c{aspect-ratio:1;display:flex;align-items:center;justify-content:center;font-weight:800;cursor:pointer;position:relative}
.gm{background:linear-gradient(#0007,#0007) center/100% 1px no-repeat,linear-gradient(#0007,#0007) center/1px 100% no-repeat}
.st{display:block;width:86%;height:86%;border-radius:50%}
.bk1{background:radial-gradient(circle at 35% 35%,#777,#111)}.wh1{background:radial-gradient(circle at 35% 35%,#fff,#ccc)}
.ls{box-shadow:0 0 0 3px #ff5fa2}
.dot{display:block;width:24%;height:24%;border-radius:50%;background:#fff9}
.ox{background:#fff;border-radius:16px;box-shadow:0 4px 0 #0001;font-size:60px}
.mc{background:#ffc928;border-radius:14px;font-size:34px;border:3px solid transparent;box-shadow:0 4px 0 #d9a300}
.mc.up{background:#fff;box-shadow:0 4px 0 #0001}
.duel{display:flex;flex-direction:column;height:calc(100vh - 90px);height:calc(100dvh - 90px);gap:8px}
.half{flex:1;border-radius:22px;display:flex;align-items:center;justify-content:center;text-align:center;color:#fff;font-weight:800;font-size:20px;touch-action:none;padding:10px}
.top{transform:rotate(180deg)}
.inp{width:100%;font-size:20px;padding:10px;border:3px solid #ffb3d1;border-radius:14px;font-family:inherit;margin:8px 0;text-align:center;outline:none}
textarea.inp{font-size:16px;text-align:left}
.clr{width:34px;height:34px;border-radius:50%;border:3px solid #ddd;margin:6px 3px;vertical-align:middle}
.shake{animation:sh .25s infinite}
.hbs{display:flex;justify-content:center;gap:8px;margin:10px 0}
.hbs span{width:48px;height:58px;border-radius:12px;border:3px solid #ffb3d1;background:#fff;font-size:32px;font-weight:800;display:flex;align-items:center;justify-content:center}
.hbk{display:grid;grid-template-columns:repeat(6,1fr);gap:6px;max-width:380px;margin:8px auto}
.hbk .btn{margin:0;padding:10px 0;font-size:20px}
.hbr{display:flex;align-items:center;justify-content:space-between;gap:8px;padding:7px 10px;border-bottom:2px dashed #ffe0ec;font-weight:800}
.hbr b{font-size:22px;letter-spacing:4px}
.hbr em{font-style:normal;color:#ff5fa2}.hbr i{font-style:normal;color:#3fa9ff}
@keyframes sh{0%,100%{transform:rotate(-6deg)}50%{transform:rotate(6deg) scale(1.05)}}
</style>
</head>
<body>
<div id="app"></div>
<script>
const $=s=>document.querySelector(s);
const app=$('#app');
let G={},tm=[],AC,RL=null;
const NP={};
function T(f,ms){tm.push(setTimeout(f,ms))}
function I(f,ms){const id=setInterval(f,ms);tm.push(id);return id}
function clr(){tm.forEach(i=>{clearTimeout(i);clearInterval(i)});tm=[]}
const sh=a=>{a=[...a];for(let i=a.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[a[i],a[j]]=[a[j],a[i]]}return a};
const rp=a=>a[Math.floor(Math.random()*a.length)];
const esc=s=>s.replace(/&/g,'&amp;').replace(/</g,'&lt;');
const rng=n=>[...Array(n).keys()];
function beep(f=880,d=.15){try{AC=AC||new(window.AudioContext||window.webkitAudioContext)();const o=AC.createOscillator(),g=AC.createGain();o.frequency.value=f;o.connect(g);g.connect(AC.destination);g.gain.setValueAtTime(.2,AC.currentTime);g.gain.exponentialRampToValueAtTime(.001,AC.currentTime+d);o.start();o.stop(AC.currentTime+d)}catch(e){}}
function vib(p){try{navigator.vibrate&&navigator.vibrate(p)}catch(e){}}
function scr(t,b){app.innerHTML=`<div class="hd"><button class="bk" onclick="home()">←</button><h2>${t}</h2></div>${b}`;scrollTo(0,0)}
function rule(t){return `<div class="box" style="text-align:left"><div class="mid" style="font-size:16px">📖 ルール</div><p class="note">${t}</p></div>`}
function np(id,label,min,max,def){NP[id]={v:def,min,max};return `<div class="mid" style="font-size:18px">${label}</div><div class="num"><button class="btn b s" onclick="npc('${id}',-1)">－</button><span id="np_${id}">${def}</span><button class="btn b s" onclick="npc('${id}',1)">＋</button></div>`}
function npc(id,d){const o=NP[id];o.v=Math.min(o.max,Math.max(o.min,o.v+d));$('#np_'+id).textContent=o.v}
function fmt(s){return Math.floor(s/60)+':'+String(s%60).padStart(2,'0')}
function timer(sec,id,end){let s=sec;const f=()=>{const e=$('#'+id);if(e)e.textContent=fmt(s)};f();const iv=I(()=>{s--;f();if(s<=0){clearInterval(iv);end&&end()}},1000);return iv}
function again(fn,label='もう一度'){return `<button class="btn" onclick="${fn}()">${label}</button><button class="btn s y" onclick="home()">ホームへ</button>`}
function win(b,W,H,i,k){const x=i%W,y=Math.floor(i/W),v=b[i];for(const[dx,dy]of[[1,0],[0,1],[1,1],[1,-1]]){let c=1;for(const s of[1,-1]){let nx=x+dx*s,ny=y+dy*s;while(nx>=0&&nx<W&&ny>=0&&ny<H&&b[ny*W+nx]==v){c++;nx+=dx*s;ny+=dy*s}}if(c>=k)return true}return false}

/* ===== ホーム ===== */
const COL=['#ffb3d1','#9fd4ff','#ffe08a','#a6ebc9','#d6b8ff','#ffc7a3'];
const GAMES=[
['🐺','ワードウルフ','3〜10人',wolf],['⚫','五目並べ','2人・14×14',gomoku],['✨','消える〇✕','2人',kieru],
['🚫','NGワード','2〜10人',ng],['🤝','全員一致ゲーム','みんなで',icchi],['🔴','四目並べ','2人',c4],
['⚪','リバーシ','2人',rv],['⚡','反射神経バトル','2人',reflex],['👆','連打バトル','2人',renda],
['💣','ばくだんゲーム','みんなで',bomb],['🎨','お絵かきクイズ','みんなで',oekaki],['🎯','ドボンナンバー','みんなで',dobon],
['🔢','30言ったら負け','1〜2人',s30],['🙆','ジェスチャー','みんなで',gesture],['🎰','ルーレット','みんなで',rlt],
['⏱','ピッタリ10秒','1〜10人',stop10],['🃏','神経衰弱','2人',memory],['🔍','ヒット&ブロー','1〜2人',hb]];
function home(){clr();G={};app.innerHTML=`<div class="title">🎉 パーティーBOX</div><div class="sub">スマホ1台でみんなであそぼう！</div><div class="grid">${GAMES.map((g,i)=>`<div class="card" style="--c:${COL[i%6]}" onclick="GAMES[${i}][3]()"><div class="e">${g[0]}</div><b>${g[1]}</b><small>${g[2]}</small></div>`).join('')}</div>`;scrollTo(0,0)}

/* ===== ワードウルフ ===== */
const WW=[['りんご','なし'],['犬','猫'],['海','プール'],['ラーメン','うどん'],['コーヒー','紅茶'],['サッカー','バスケ'],['夏','冬'],['映画館','水族館'],['ピアノ','ギター'],['カレー','シチュー'],['電車','バス'],['寿司','焼肉'],['スマホ','パソコン'],['温泉','サウナ'],['チョコ','クッキー'],['雪','雨'],['先生','医者'],['遊園地','動物園'],['パン','ごはん'],['桜','ひまわり'],['YouTube','テレビ'],['ハンバーガー','ピザ'],['図書館','本屋'],['誕生日','クリスマス']];
function wolf(){scr('🐺 ワードウルフ',`<div class="box">${np('n','人数',3,10,4)}${np('m','話し合い（分）',1,10,3)}<button class="btn" onclick="wolfGo()">スタート</button></div>${rule('みんなにお題が配られるけど、1人だけ違うお題（ウルフ）！自分がウルフかどうかは分からないよ。話し合ってウルフを見つけよう。ウルフはバレないように話を合わせてね。')}`)}
function wolfGo(){clr();const p=sh(rp(WW));G={n:NP.n.v,m:NP.m.v,w:Math.floor(Math.random()*NP.n.v),a:p[0],b:p[1],i:0};wolfPass()}
function wolfPass(){if(G.i>=G.n)return wolfTalk();scr('🐺 ワードウルフ',`<div class="box"><div class="big">プレイヤー${G.i+1}</div><p class="note">スマホを受け取ったら、他の人に見えないようにしてタップ</p><button class="btn b" onclick="wolfSee()">お題を見る</button></div>`)}
function wolfSee(){scr('🐺 ワードウルフ',`<div class="box"><div class="note">プレイヤー${G.i+1}のお題</div><div class="big">${G.i==G.w?G.b:G.a}</div><button class="btn" onclick="G.i++;wolfPass()">覚えた！次の人へ</button></div>`)}
function wolfTalk(){clr();scr('🐺 ワードウルフ',`<div class="box"><div class="mid">話し合いタイム</div><div class="big" id="tm"></div><p class="note">お題について話して、ウルフを見つけよう！</p><button class="btn y" onclick="wolfVote()">投票へ進む</button></div>`);timer(G.m*60,'tm',()=>{beep();vib(300);wolfVote()})}
function wolfVote(){clr();scr('🐺 ワードウルフ',`<div class="box"><div class="mid">せーので指をさして投票！</div><p class="note">一番票を集めた人をタップ</p>${rng(G.n).map(i=>`<button class="btn b s" onclick="wolfRes(${i})">プレイヤー${i+1}</button>`).join('')}</div>`)}
function wolfRes(v){const ok=v==G.w;beep(ok?1000:300,.4);scr('🐺 ワードウルフ',`<div class="box"><div class="big">${ok?'🎉 市民の勝ち！':'🐺 ウルフの勝ち！'}</div><div class="mid">ウルフはプレイヤー${G.w+1}</div><p class="note">市民のお題：<b>${G.a}</b><br>ウルフのお題：<b>${G.b}</b></p>${ok?'<p class="note">※ウルフが市民のお題を当てたら逆転勝利！</p>':''}${again('wolfGo')}</div>`)}

/* ===== 五目並べ ===== */
function gomoku(){G={b:Array(196).fill(0),t:1,end:0,last:-1};gmR()}
function gmR(){const s=G.end==3?'引き分け':G.end?(G.end==1?'⚫ 黒':'⚪ 白')+' の勝ち！🎉':(G.t==1?'⚫ 黒':'⚪ 白')+' の番';scr('⚫ 五目並べ',`<div class="box" style="padding:10px"><div class="mid">${s}</div><p class="note">縦・横・ななめに5つ並べたら勝ち！</p></div><div class="bd" style="grid-template-columns:repeat(14,1fr);gap:0;background:#e8b86a;padding:4px;border-radius:12px">${G.b.map((v,i)=>`<div class="c gm" onclick="gmP(${i})">${v?`<i class="st ${v==1?'bk1':'wh1'} ${i==G.last?'ls':''}"></i>`:''}</div>`).join('')}</div><div style="text-align:center"><button class="btn s y" onclick="gomoku()">最初から</button></div>`)}
function gmP(i){if(G.end||G.b[i])return;G.b[i]=G.t;G.last=i;beep(600,.05);if(win(G.b,14,14,i,5)){G.end=G.t;beep(1000,.4)}else if(!G.b.includes(0))G.end=3;else G.t=3-G.t;gmR()}

/* ===== 消える〇✕ ===== */
function kieru(){G={b:Array(9).fill(0),q:{1:[],2:[]},t:1,end:0};kiR()}
function kiR(){const old=G.q[G.t].length==3?G.q[G.t][0]:-1;scr('✨ 消える〇✕',`<div class="box"><div class="mid">${G.end?(G.end==1?'〇':'✕')+' の勝ち！🎉':(G.t==1?'〇':'✕')+' の番'}</div><p class="note">自分のコマは3つまで！4つ目を置くと一番古いコマが消えるよ。<br>うすくなっているコマが次に消えるコマ。</p></div><div class="bd" style="grid-template-columns:repeat(3,1fr);gap:10px;max-width:340px">${G.b.map((v,i)=>`<div class="c ox" style="color:${v==1?'#ff5fa2':'#3fa9ff'};opacity:${i==old&&!G.end?.3:1}" onclick="kiP(${i})">${v==1?'〇':v==2?'✕':''}</div>`).join('')}</div><div style="text-align:center"><button class="btn s y" onclick="kieru()">最初から</button></div>`)}
function kiP(i){if(G.end||G.b[i])return;const q=G.q[G.t];if(q.length==3)G.b[q.shift()]=0;q.push(i);G.b[i]=G.t;beep(700,.05);if(win(G.b,3,3,i,3)){G.end=G.t;beep(1000,.4)}else G.t=3-G.t;kiR()}

/* ===== NGワード ===== */
const NGW=['すごい','えー','でも','私','なんで','ほんと','やばい','ありがとう','うん','かわいい','ごめん','いいね','たしかに','なるほど','まじ','好き','食べる','行く','今日','お金','あれ','ちょっと','楽しい','いや','だから','はい','わかる','おいしい','時間','明日'];
function ng(){scr('🚫 NGワード',`<div class="box">${np('n','人数',2,10,4)}${np('m','制限時間（分）',1,10,3)}<button class="btn" onclick="ngGo()">スタート</button></div>${rule('一人ひとりにNGワードが決まるよ。でも自分のNGワードだけは知らない！会話をして、他の人にNGワードを言わせよう。言ってしまったらアウト。最後まで残った人の勝ち！')}`)}
function ngGo(){clr();G={n:NP.n.v,m:NP.m.v,w:sh(NGW).slice(0,NP.n.v),i:0,out:[]};ngPass()}
function ngPass(){if(G.i>=G.n)return ngPlay();scr('🚫 NGワード',`<div class="box"><div class="mid">プレイヤー${G.i+1} のNGワード</div><p class="note" style="font-size:16px">⚠️ プレイヤー${G.i+1}は見ないで！<br>他の人だけで確認してね</p><button class="btn b" onclick="ngSee()">見る</button></div>`)}
function ngSee(){scr('🚫 NGワード',`<div class="box"><div class="note">プレイヤー${G.i+1}のNGワード</div><div class="big">${G.w[G.i]}</div><button class="btn" onclick="G.i++;ngPass()">覚えた！隠す</button></div>`)}
function ngPlay(){clr();scr('🚫 NGワード',`<div class="box"><div class="mid">トークタイム</div><div class="big" id="tm"></div><p class="note">NGワードを言った人をタップしてアウトに！</p><div id="pl"></div><button class="btn s y" onclick="ngEnd()">終了する</button></div>`);ngPl();timer(G.m*60,'tm',()=>{beep();vib(300);ngEnd()})}
function ngPl(){$('#pl').innerHTML=rng(G.n).map(i=>{const o=G.out.includes(i);return `<button class="btn s ${o?'':'g'}" ${o?'disabled':''} onclick="ngOut(${i})">P${i+1}${o?' 💀':''}</button>`}).join('')}
function ngOut(i){if(G.out.includes(i))return;G.out.push(i);beep(300,.3);vib(200);if(G.n-G.out.length<=1)ngEnd();else ngPl()}
function ngEnd(){clr();const al=rng(G.n).filter(i=>!G.out.includes(i));scr('🚫 NGワード',`<div class="box"><div class="mid">🏆 勝者：${al.map(i=>'P'+(i+1)).join('、')||'なし'}</div>${G.w.map((w,i)=>`<p class="note" style="font-size:16px">P${i+1}：<b>${w}</b>${G.out.includes(i)?' 💀':''}</p>`).join('')}${again('ngGo')}</div>`)}

/* ===== 全員一致 ===== */
const IT=['赤い食べ物といえば？','夏といえば？','コンビニで買うものといえば？','動物園の人気者といえば？','朝ごはんといえば？','おにぎりの具といえば？','黄色いものといえば？','ラーメンの味といえば？','旅行に行きたい国は？','学校の行事といえば？','丸いものといえば？','冬のスポーツといえば？','果物の王様といえば？','空を飛ぶものといえば？','アイスの味といえば？','カレーの具といえば？','お寿司のネタといえば？','誕生日にほしいものは？','虫といえば？','ピザのトッピングといえば？','雨の日に必要なものは？','お祭りの屋台といえば？','緑の野菜といえば？','鍋の具といえば？','おでんの具といえば？','甘いものといえば？','休みの日にすることは？','白いものといえば？','好きな季節は？','ハロウィンの仮装といえば？'];
function icchi(){scr('🤝 全員一致ゲーム',`<div class="box">${np('r','ラウンド数',3,15,10)}<button class="btn" onclick="icGo()">スタート</button></div>${rule('お題に対して、せーので全員が同時に答えを言おう！全員の答えがそろったら1ポイント。みんなの心をひとつにしよう！')}`)}
function icGo(){G={r:NP.r.v,i:0,s:0,t:sh(IT)};icR()}
function icR(){if(G.i>=G.r)return icEnd();scr('🤝 全員一致ゲーム',`<div class="box"><div class="note">ラウンド ${G.i+1} / ${G.r}　　ポイント ${G.s}</div><div class="mid" style="font-size:28px;margin:24px 0">${G.t[G.i%G.t.length]}</div><p class="note">「せーの！」で一斉に答えてね</p><button class="btn g" onclick="G.s++;G.i++;beep(1000);icR()">全員一致！</button><button class="btn b" onclick="G.i++;beep(300);icR()">バラバラ…</button></div>`)}
function icEnd(){scr('🤝 全員一致ゲーム',`<div class="box"><div class="note">結果</div><div class="big">${G.s} / ${G.r}</div><div class="mid">${G.s==G.r?'完全シンクロ！💯':G.s>=G.r*.7?'仲良し！✨':G.s>=G.r*.4?'まあまあ！😊':'バラバラ…😂'}</div>${again('icGo')}</div>`)}

/* ===== 四目並べ ===== */
function c4(){G={b:Array(42).fill(0),t:1,end:0};c4R()}
function c4R(){const s=G.end==3?'引き分け':G.end?(G.end==1?'🔴 赤':'🟡 黄')+' の勝ち！🎉':(G.t==1?'🔴 赤':'🟡 黄')+' の番';scr('🔴 四目並べ',`<div class="box" style="padding:10px"><div class="mid">${s}</div><p class="note">列をタップしてコマを落とそう。4つ並べたら勝ち！</p></div><div class="bd" style="grid-template-columns:repeat(7,1fr);background:#3fa9ff;padding:6px;border-radius:14px;gap:4px">${G.b.map((v,i)=>`<div class="c" onclick="c4P(${i%7})"><i class="st" style="background:${v==1?'#ff5fa2':v==2?'#ffc928':'#fff'}"></i></div>`).join('')}</div><div style="text-align:center"><button class="btn s y" onclick="c4()">最初から</button></div>`)}
function c4P(x){if(G.end)return;for(let y=5;y>=0;y--){const i=y*7+x;if(!G.b[i]){G.b[i]=G.t;beep(600,.05);if(win(G.b,7,6,i,4)){G.end=G.t;beep(1000,.4)}else if(!G.b.includes(0))G.end=3;else G.t=3-G.t;return c4R()}}}

/* ===== リバーシ ===== */
function rv(){const b=Array(64).fill(0);b[27]=b[36]=2;b[28]=b[35]=1;G={b,t:1,end:0,msg:''};rvR()}
function rvF(b,i,t){if(b[i])return[];const x=i%8,y=Math.floor(i/8),r=[];for(const[dx,dy]of[[1,0],[-1,0],[0,1],[0,-1],[1,1],[1,-1],[-1,1],[-1,-1]]){let nx=x+dx,ny=y+dy;const tmp=[];while(nx>=0&&nx<8&&ny>=0&&ny<8&&b[ny*8+nx]==3-t){tmp.push(ny*8+nx);nx+=dx;ny+=dy}if(tmp.length&&nx>=0&&nx<8&&ny>=0&&ny<8&&b[ny*8+nx]==t)r.push(...tmp)}return r}
function rvM(t){const m=[];for(let i=0;i<64;i++)if(rvF(G.b,i,t).length)m.push(i);return m}
function rvR(){const m=G.end?[]:rvM(G.t),c1=G.b.filter(v=>v==1).length,c2=G.b.filter(v=>v==2).length;const s=G.end?(c1>c2?'⚫ 黒の勝ち！🎉':c2>c1?'⚪ 白の勝ち！🎉':'引き分け！'):(G.t==1?'⚫ 黒':'⚪ 白')+' の番';scr('⚪ リバーシ',`<div class="box" style="padding:10px"><div class="mid">${s}</div><p class="note">⚫ ${c1} − ${c2} ⚪　${G.msg}</p></div><div class="bd" style="grid-template-columns:repeat(8,1fr);background:#2e9e5b;padding:4px;border-radius:12px">${G.b.map((v,i)=>`<div class="c" style="border:1px solid #0002" onclick="rvP(${i})">${v?`<i class="st ${v==1?'bk1':'wh1'}"></i>`:m.includes(i)?'<i class="dot"></i>':''}</div>`).join('')}</div><div style="text-align:center"><button class="btn s y" onclick="rv()">最初から</button></div>`)}
function rvP(i){if(G.end)return;const f=rvF(G.b,i,G.t);if(!f.length)return;G.b[i]=G.t;f.forEach(j=>G.b[j]=G.t);beep(600,.05);G.msg='';G.t=3-G.t;if(!rvM(G.t).length){if(rvM(3-G.t).length){G.msg=`（${G.t==1?'黒':'白'}は置ける場所がないのでパス）`;G.t=3-G.t}else{G.end=1;beep(1000,.4)}}rvR()}

/* ===== 2人対戦レイアウト ===== */
function duel(t){scr(t,`<div class="duel"><div class="half top" id="h0" style="background:#ff8fbf"><div id="t0"></div></div><div class="half" id="h1" style="background:#7cc4ff"><div id="t1"></div></div></div>`)}
function bindDuel(fn){for(const p of[0,1])$('#h'+p).addEventListener('pointerdown',e=>{e.preventDefault();fn(p)})}
function dMsg(m){for(const p of[0,1])$('#t'+p).innerHTML=m}
function setBg(c){$('#h0').style.background=c||'#ff8fbf';$('#h1').style.background=c||'#7cc4ff'}

/* ===== 反射神経 ===== */
function reflex(){clr();G={s:[0,0],st:'idle'};duel('⚡ 反射神経バトル');bindDuel(rfTap);rfMsg('タップでスタート<br><small>緑になったら早くタップ！3点先取</small>')}
function rfMsg(m){for(const p of[0,1])$('#t'+p).innerHTML=`<div class="big">${G.s[p]}点</div><div>${m}</div>`}
function rfTap(p){if(G.st=='idle'){G.st='wait';setBg('#bbb');rfMsg('まだだよ…');T(()=>{if(G.st!='wait')return;G.st='go';setBg('#3ccf8e');beep();rfMsg('今だ！！')},2000+Math.random()*3000)}else if(G.st=='wait'){clr();rfPt(1-p,`P${p+1}のおてつき！`)}else if(G.st=='go')rfPt(p,`P${p+1}の勝ち！`)}
function rfPt(p,m){G.s[p]++;G.st='lock';setBg('');if(G.s[p]>=3){beep(1000,.4);rfMsg(`${m}<br>🏆 P${p+1} 優勝！`);T(()=>{G.s=[0,0];G.st='idle';rfMsg('タップで再戦')},2500)}else{rfMsg(m+'<br>タップで次へ');T(()=>{G.st='idle'},800)}}

/* ===== 連打 ===== */
function renda(){clr();G={c:[0,0],st:'idle'};duel('👆 連打バトル');bindDuel(rdTap);dMsg('タップで準備<br><small>10秒間でたくさんタップした方の勝ち！</small>')}
function rdTap(p){if(G.st=='idle'){G.st='cd';let n=3;dMsg(`<div class="big">${n}</div>`);beep(600);const iv=I(()=>{n--;if(n>0){dMsg(`<div class="big">${n}</div>`);beep(600)}else{clearInterval(iv);G.st='go';G.c=[0,0];beep(1000);dMsg('<div class="big">連打！！</div>');let t=10;const iv2=I(()=>{t--;if(t<=0){clearInterval(iv2);G.st='lock';beep(400,.4);const w=G.c[0]==G.c[1]?'引き分け！':G.c[0]>G.c[1]?'P1の勝ち！🎉':'P2の勝ち！🎉';for(const q of[0,1])$('#t'+q).innerHTML=`<div class="big">${G.c[q]}回</div><div>${w}</div><small>少し待ってタップで再戦</small>`;T(()=>{G.st='idle'},1500)}},1000)}},1000)}else if(G.st=='go'){G.c[p]++;$('#t'+p).innerHTML=`<div class="big">${G.c[p]}</div>`}}

/* ===== ばくだん ===== */
const BT=['果物の名前','動物の名前','国の名前','赤いもの','「あ」で始まる言葉','スポーツ','野菜','お菓子','乗り物','日本の都道府県','色の名前','楽器','海にいる生き物','職業','学校にあるもの','キッチンにあるもの'];
function bomb(){clr();G={t:rp(BT),c:0};scr('💣 ばくだんゲーム',`<div class="box"><div class="note">お題</div><div class="mid" style="font-size:28px">${G.t}</div><button class="btn" onclick="bombGo()">スタート</button><button class="btn s y" onclick="bomb()">お題チェンジ</button></div>${rule('お題に合う言葉を言ったら「言った！」を押して、隣の人にスマホを渡そう。いつ爆発するかは誰にも分からない…！爆発したときに持っていた人の負け！')}`)}
function bombGo(){clr();G.c=0;scr('💣 ばくだんゲーム',`<div class="box"><div class="note">お題：${G.t}</div><div style="font-size:110px" class="shake">💣</div><div class="mid" id="bc">0回</div><button class="btn g" style="font-size:24px;padding:22px 40px" onclick="G.c++;$('#bc').textContent=G.c+'回';beep(1200,.05)">言った！次へ</button></div>`);I(()=>beep(500,.03),700);T(()=>{clr();beep(120,.8);vib([300,100,300]);scr('💣 ばくだんゲーム',`<div class="box"><div style="font-size:110px">💥</div><div class="big">ドカーン！</div><div class="mid">持っていた人の負け！</div><p class="note">${G.c}回つながったよ</p>${again('bomb')}</div>`)},15000+Math.random()*30000)}

/* ===== お絵かき ===== */
const OT=['ねこ','ラーメン','東京タワー','ひまわり','新幹線','雪だるま','ペンギン','カレーライス','スマホ','おにぎり','富士山','サッカー','傘','キリン','たこ焼き','ロケット','虹','パンダ','自転車','うさぎ','花火','ケーキ','ゾウ','メガネ'];
function oekaki(){clr();G={t:rp(OT)};scr('🎨 お絵かきクイズ',`<div class="box"><p class="note">描く人だけが見てね！</p><div id="ot"><button class="btn b" onclick="$('#ot').innerHTML='<div class=big>'+G.t+'</div>'">お題を見る</button></div><button class="btn" onclick="okDraw()">描きはじめる（60秒）</button><br><button class="btn s y" onclick="oekaki()">お題チェンジ</button></div>${rule('描く人はお題を見て絵を描こう。文字は禁止！他の人は何の絵か当ててね。60秒以内に正解できたら成功！')}`)}
function okDraw(){clr();scr('🎨 お絵かきクイズ',`<div class="box" style="padding:10px"><div class="mid" id="tm"></div><canvas id="cv" style="width:100%;aspect-ratio:1;background:#fff;border:3px dashed #ffb3d1;border-radius:14px;touch-action:none;display:block"></canvas><div>${['#433','#ff5fa2','#3fa9ff','#3ccf8e','#ffc928','#fff'].map(c=>`<button class="clr" style="background:${c}" onclick="G.col='${c}';G.w=${c=='#fff'?26:6}"></button>`).join('')}<button class="btn s y" onclick="G.x.clearRect(0,0,9999,9999)">全消し</button></div><button class="btn g" onclick="okEnd(1)">正解が出た！</button></div>`);
const cv=$('#cv'),w=cv.getBoundingClientRect().width;cv.width=cv.height=w*2;const x=cv.getContext('2d');x.scale(2,2);x.lineCap=x.lineJoin='round';G.x=x;G.col='#433';G.w=6;let d=0,lx=0,ly=0;
const pos=e=>{const b=cv.getBoundingClientRect();return[(e.clientX-b.left)*w/b.width,(e.clientY-b.top)*w/b.height]};
const line=(a,b)=>{x.strokeStyle=G.col;x.lineWidth=G.w;x.beginPath();x.moveTo(lx,ly);x.lineTo(a,b);x.stroke();lx=a;ly=b};
cv.onpointerdown=e=>{d=1;try{cv.setPointerCapture(e.pointerId)}catch(_){}[lx,ly]=pos(e);line(lx+.1,ly+.1)};
cv.onpointermove=e=>{if(d){const[a,b]=pos(e);line(a,b)}};
cv.onpointerup=cv.onpointercancel=()=>{d=0};
timer(60,'tm',()=>{beep(300,.5);vib(300);okEnd(0)})}
function okEnd(ok){clr();if(ok)beep(1000,.4);scr('🎨 お絵かきクイズ',`<div class="box"><div class="big">${ok?'🎉 正解！':'⏰ タイムアップ！'}</div><div class="note">お題は</div><div class="big">${G.t}</div>${again('oekaki','次のお題')}</div>`)}

/* ===== ドボンナンバー ===== */
function dobon(){G={s:1+Math.floor(Math.random()*100),lo:1,hi:100};dbR('')}
function dbR(m){scr('🎯 ドボンナンバー',`<div class="box"><p class="note">1〜100の中に1つだけ爆弾の数字があるよ！順番に数字を入れて、爆弾を当てちゃった人の負け！</p><div class="big">${G.lo} 〜 ${G.hi}</div><div class="mid" style="color:#ff5fa2;font-size:18px">${m}</div><input id="di" type="number" inputmode="numeric" class="inp" placeholder="数字を入力"><br><button class="btn" onclick="dbP()">決定</button></div>`)}
function dbP(){const v=parseInt($('#di').value,10);if(isNaN(v)||v<G.lo||v>G.hi)return dbR(`${G.lo}〜${G.hi}の数字を入れてね`);if(v==G.s){beep(120,.8);vib([300,100,300]);return scr('🎯 ドボンナンバー',`<div class="box"><div style="font-size:100px">💥</div><div class="big">${v} はドボン！</div><div class="mid">入れた人の負け！</div>${again('dobon')}</div>`)}if(v<G.s)G.lo=v+1;else G.hi=v-1;beep();dbR(`${v} はセーフ！次の人へ`)}

/* ===== 30言ったら負け ===== */
function s30(){scr('🔢 30言ったら負け',`<div class="box"><button class="btn" onclick="s30Go(1)">CPUと対戦</button><button class="btn b" onclick="s30Go(0)">2人で対戦</button></div>${rule('1から順番に数字を言っていくよ。1回で1〜3個まで進められる。30を言ってしまった人の負け！')}`)}
function s30Go(cpu){clr();G={n:0,t:0,cpu,log:'スタート！'};s30R()}
function s30W(){return G.cpu?(G.t?'CPU':'あなた'):'P'+(G.t+1)}
function s30R(){const lock=G.cpu&&G.t==1;scr('🔢 30言ったら負け',`<div class="box"><div class="note">${G.log}</div><div class="big" style="font-size:72px">${G.n}</div><div class="mid">${s30W()} の番${lock?'（考え中…）':''}</div>${[1,2,3].map(k=>`<button class="btn ${k==2?'b':k==3?'g':''}" ${lock||G.n+k>30?'disabled':''} onclick="s30M(${k})">〜${G.n+k}</button>`).join('')}</div>`);if(lock){let k=((1-G.n)%4+4)%4;if(!k)k=1+Math.floor(Math.random()*3);k=Math.min(k,30-G.n);T(()=>s30M(k),900)}}
function s30M(k){const sd=[];for(let j=0;j<k&&G.n<30;j++)sd.push(++G.n);G.log=`${s30W()}：${sd.join('、')}`;beep(700,.05);if(G.n>=30){beep(200,.5);return scr('🔢 30言ったら負け',`<div class="box"><div style="font-size:80px">😵</div><div class="big">${s30W()}の負け！</div><p class="note">${G.log}</p>${again('s30')}</div>`)}G.t=1-G.t;s30R()}

/* ===== ジェスチャー ===== */
const GT=['ゴリラ','サッカー','歯みがき','料理','ピアノ','ボウリング','スキー','カメラマン','忍者','水泳','寝坊','電話','ラーメンを食べる','釣り','ウサギ','テニス','掃除機','ギター','ゾンビ','ドラム','バレエ','相撲','車の運転','魔法使い','雪合戦','バスケ','傘をさす','空手','カニ','ゴルフ'];
function gesture(){scr('🙆 ジェスチャー',`<div class="box"><button class="btn" onclick="gsGo()">スタート（60秒）</button></div>${rule('演じる人だけ画面を見て、お題をジェスチャーで表現しよう。声を出すのは禁止！当たったら「正解」、難しかったら「パス」。60秒で何問当てられるかな？')}`)}
function gsGo(){clr();G={t:sh(GT),i:0,s:0};scr('🙆 ジェスチャー',`<div class="box"><div class="big" id="tm"></div><div class="note">正解数 <b id="gs">0</b></div><div class="big" id="gw" style="font-size:38px;margin:24px 0">${G.t[0]}</div><button class="btn g" onclick="gsN(1)">⭕ 正解</button><button class="btn b" onclick="gsN(0)">パス</button></div>`);timer(60,'tm',()=>{beep(300,.5);vib(300);gsEnd()})}
function gsN(ok){if(ok){G.s++;beep(1000,.1)}else beep(400,.1);G.i++;$('#gs').textContent=G.s;$('#gw').textContent=G.t[G.i%G.t.length]}
function gsEnd(){clr();scr('🙆 ジェスチャー',`<div class="box"><div class="mid">タイムアップ！</div><div class="big">${G.s}問 正解</div>${again('gsGo')}</div>`)}

/* ===== ルーレット ===== */
function rlt(){clr();const def=RL??'モノマネをする\n変顔をする\n好きなタイプを言う\n10秒間ダンス\n語尾に「ニャン」をつける\nセーフ！';scr('🎰 ルーレット',`<div class="box"><p class="note">1行に1つずつ入力してね（名前・罰ゲームなど）</p><textarea id="rl" class="inp" rows="6">${esc(def)}</textarea><div class="big" id="rr" style="font-size:30px;min-height:60px">？</div><button class="btn" id="rb" onclick="rlGo()">まわす！</button></div>`)}
function rlGo(){const a=$('#rl').value.split('\n').map(s=>s.trim()).filter(Boolean);if(a.length<2){$('#rr').textContent='2つ以上入れてね';return}RL=$('#rl').value;$('#rb').disabled=true;let d=40,k=Math.floor(Math.random()*a.length);const step=()=>{const e=$('#rr');if(!e)return;e.textContent=a[k%a.length];beep(700,.03);d*=1.12;if(d<450){k++;T(step,d)}else{e.textContent='🎉 '+a[k%a.length];$('#rb').disabled=false;beep(1000,.3)}};step()}

/* ===== ピッタリ10秒 ===== */
function stop10(){scr('⏱ ピッタリ10秒',`<div class="box">${np('n','人数',1,10,3)}<button class="btn" onclick="stGo()">スタート</button></div>${rule('スタートを押して、ピッタリ10秒だと思ったらストップ！3秒たつと時間が見えなくなるよ。10.00秒に一番近い人の勝ち！')}`)}
function stGo(){clr();G={n:NP.n.v,i:0,r:[]};stR()}
function stR(){if(G.i>=G.n)return stEnd();G.run=0;scr('⏱ ピッタリ10秒',`<div class="box"><div class="mid">プレイヤー${G.i+1}</div><div class="big" id="sw" style="font-size:64px">0.00</div><button class="btn" id="sb" style="font-size:26px;padding:24px 48px" onclick="stT()">スタート</button></div>`)}
function stT(){if(G.run==0){G.run=1;G.t0=performance.now();$('#sb').textContent='ストップ';G.iv=I(()=>{const t=(performance.now()-G.t0)/1000;$('#sw').textContent=t<3?t.toFixed(2):'?.??'},30)}else if(G.run==1){const t=(performance.now()-G.t0)/1000;clearInterval(G.iv);G.run=3;G.r.push([G.i,t]);$('#sw').textContent=t.toFixed(2);$('#sb').textContent=G.i+1<G.n?'次の人へ':'結果発表';beep();T(()=>{G.run=2},600)}else if(G.run==2){G.i++;stR()}}
function stEnd(){const s=[...G.r].sort((a,b)=>Math.abs(a[1]-10)-Math.abs(b[1]-10));scr('⏱ ピッタリ10秒',`<div class="box"><div class="mid">結果発表</div>${s.map((r,k)=>{const df=r[1]-10;return `<p class="mid" style="font-size:18px">${['🥇','🥈','🥉'][k]||(k+1)+'位'} P${r[0]+1}：${r[1].toFixed(2)}秒 <small style="color:#866">(${df>=0?'+':''}${df.toFixed(2)})</small></p>`}).join('')}${again('stGo')}</div>`)}

/* ===== 神経衰弱 ===== */
const EM=['🍎','🐶','🌸','⚽','🍩','🚀','🐸','🎸'];
function memory(){clr();G={c:sh([...EM,...EM]),o:[],m:{},t:0,s:[0,0],lock:0};mmR()}
function mmR(){const done=Object.keys(G.m).length==16;const s=done?(G.s[0]==G.s[1]?'引き分け！':`P${G.s[0]>G.s[1]?1:2} の勝ち！🎉`):`<span style="color:${G.t?'#3fa9ff':'#ff5fa2'}">P${G.t+1}</span> の番`;scr('🃏 神経衰弱',`<div class="box" style="padding:10px"><div class="mid">${s}</div><p class="note"><span style="color:#ff5fa2">P1：${G.s[0]}組</span>　<span style="color:#3fa9ff">P2：${G.s[1]}組</span></p></div><div class="bd" style="grid-template-columns:repeat(4,1fr);gap:8px;max-width:400px">${G.c.map((e,i)=>{const mt=G.m[i]!==undefined,up=mt||G.o.includes(i);return `<div class="c mc ${up?'up':''}" style="${mt?`border-color:${G.m[i]?'#3fa9ff':'#ff5fa2'}`:''}" onclick="mmP(${i})">${up?e:'❓'}</div>`}).join('')}</div><div style="text-align:center"><button class="btn s y" onclick="memory()">最初から</button></div>`)}
function mmP(i){if(G.lock||G.o.includes(i)||G.m[i]!==undefined)return;G.o.push(i);beep(700,.04);mmR();if(G.o.length==2){const[a,b]=G.o;if(G.c[a]==G.c[b]){G.m[a]=G.m[b]=G.t;G.s[G.t]++;G.o=[];beep(1000,.15);mmR()}else{G.lock=1;T(()=>{G.o=[];G.lock=0;G.t=1-G.t;mmR()},1000)}}}

/* ===== ヒット&ブロー ===== */
function hb(){clr();scr('🔍 ヒット&ブロー',`<div class="box">${np('d','けた数',3,5,3)}<button class="btn" onclick="hbGo(1)">ひとりで挑戦</button><button class="btn b" onclick="hbGo(0)">2人で対戦</button></div>${rule('かくされた数字を当てよう！数字は0〜9で、同じ数字は2回使わないよ。<br>数字も場所も合っていたら<b>ヒット</b>、数字は合っているけど場所がちがったら<b>ブロー</b>。<br>例）答えが 123 のときに 135 と言うと「1ヒット 1ブロー」。<br>2人対戦では、おたがいに秘密の数字を決めて交代で当て合うよ。先に当てた人の勝ち！（先攻が当てたら、後攻にもラストチャンス。後攻も当てたら引き分け）')}`)}
function hbGo(solo){clr();G={d:NP.d.v,solo,sec:[],h:[[],[]],t:0,v:'',log:'',last:0};if(solo){G.sec=[sh(rng(10)).slice(0,G.d).join('')];hbR()}else hbPass(0)}
function hbPass(p){G.ph='wait';scr('🔍 ヒット&ブロー',`<div class="box"><div class="big">プレイヤー${p+1}</div><p class="note">相手に見えないようにして、<br>秘密の${G.d}けたの数字を決めてね</p><button class="btn b" onclick="hbSet(${p})">数字を決める</button></div>`)}
function hbSet(p){G.ph='set';G.p=p;G.v='';scr('🔍 ヒット&ブロー',`<div class="box"><div class="mid">P${p+1} の秘密の数字</div><p class="note">⚠️ 相手は見ないで！</p><div id="hbk">${hbPad()}</div></div>`)}
function hbReady(){scr('🔍 ヒット&ブロー',`<div class="box"><div class="mid">準備OK！</div><p class="note">P1からスタート。交代で相手の数字を当てよう！</p><button class="btn" onclick="hbR()">はじめる</button></div>`)}
function hbPad(){const u=[...G.v],full=u.length>=G.d;return `<div class="hbs">${rng(G.d).map(i=>`<span>${u[i]??''}</span>`).join('')}</div><div class="hbk">${['1','2','3','4','5','C','6','7','8','9','0','⌫'].map(k=>{const f=k=='C'||k=='⌫';return `<button class="btn s ${f?'y':'b'}" ${f?(u.length?'':'disabled'):(full||u.includes(k)?'disabled':'')} onclick="hbK('${k}')">${k}</button>`}).join('')}</div><button class="btn g" ${full?'':'disabled'} onclick="hbOK()">${G.ph=='set'?'これに決定':'コール！'}</button>`}
function hbK(k){if(k=='⌫')G.v=G.v.slice(0,-1);else if(k=='C')G.v='';else if(G.v.length<G.d&&!G.v.includes(k))G.v+=k;beep(700,.03);$('#hbk').innerHTML=hbPad()}
function hbR(){G.ph='play';G.v='';const p=G.t,h=G.h[p],c=p?'#3fa9ff':'#ff5fa2';scr('🔍 ヒット&ブロー',`<div class="box" style="padding:12px">${G.solo?`<div class="mid">${G.d}けたの数字を当てよう！</div>`:`<div class="mid"><span style="color:${c}">P${p+1}</span> の番</div><p class="note">P${2-p} の数字を当てよう</p>`}${G.log?`<p class="note" style="color:#ff5fa2;font-weight:800">${G.log}</p>`:''}<div id="hbk">${hbPad()}</div></div><div class="box" style="padding:12px;text-align:left"><div class="note" style="text-align:center">${G.solo?'':`P${p+1} の`}これまでの記録（${h.length}回）</div>${h.length?h.map((r,i)=>`<div class="hbr"><small>${i+1}回目</small><b>${r[0]}</b><span><em>${r[1]}ヒット</em> <i>${r[2]}ブロー</i></span></div>`).reverse().join(''):'<p class="note" style="text-align:center">まだないよ</p>'}</div>${G.solo?'<div style="text-align:center"><button class="btn s y" onclick="hbEnd(-1)">あきらめる</button></div>':''}`)}
function hbOK(){if(G.v.length<G.d)return;if(G.ph=='set'){G.sec[G.p]=G.v;G.v='';beep(900,.1);return G.p==0?hbPass(1):hbReady()}if(G.ph!='play')return;const g=G.v,s=G.solo?G.sec[0]:G.sec[1-G.t];let hit=0,blow=0;[...g].forEach((ch,i)=>{if(s[i]==ch)hit++;else if(s.includes(ch))blow++});G.h[G.t].push([g,hit,blow]);const ok=hit==G.d;if(!G.solo&&G.last){if(ok){beep(1000,.4);vib(200)}else beep(300,.3);return hbEnd(ok?2:0)}if(ok){if(!G.solo&&G.t==0){G.last=1;G.t=1;beep(1000,.3);G.log=`P1が ${g} で正解！P2のラストチャンス！`;return hbR()}beep(1000,.4);vib(200);return hbEnd(G.t)}beep(hit||blow?800:400,.1);G.log=`${G.solo?'':`P${G.t+1}：`}${g} → ${hit}ヒット ${blow}ブロー`;if(!G.solo)G.t=1-G.t;hbR()}
function hbEnd(w){clr();G.ph='end';const n=w==2?G.h[0].length:w>=0?G.h[w].length:0;const t=w<0?'😢 ざんねん！':w==2?'🤝 引き分け！':G.solo?'🎉 正解！':`🎉 P${w+1} の勝ち！`;scr('🔍 ヒット&ブロー',`<div class="box"><div class="big">${t}</div>${w>=0?`<div class="mid">${n}回目で当てたよ！</div>`:''}${G.solo&&w>=0?`<div class="mid">${n<=G.d+2?'天才！🧠':n<=G.d+5?'すごい！✨':'よくがんばった！😊'}</div>`:''}<p class="note" style="font-size:16px">${G.solo?`答え：<b>${G.sec[0]}</b>`:`P1の数字：<b>${G.sec[0]}</b>　P2の数字：<b>${G.sec[1]}</b>`}</p>${again('hb')}</div>`)}

home();
</script>
</body>
</html>

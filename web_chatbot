<style>
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@700&display=swap');
:root{--a:#3A59FF;--s:#0f172a;--d:#1a2640;--t:#e2e8f0}
#sw{position:fixed;bottom:24px;right:24px;z-index:9999;font-family:system-ui,sans-serif}
#sb{width:52px;height:52px;border-radius:16px;background:var(--a);border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;box-shadow:0 4px 20px #3A59FF44;transition:transform .18s;position:relative}
#sb:hover{transform:translateY(-2px)}
#sb svg{width:22px;height:22px;fill:#fff}
#sp{position:absolute;top:-3px;right:-3px;width:10px;height:10px;background:#22d3a5;border-radius:50%;border:2px solid #060b15;animation:p 2s infinite}
@keyframes p{50%{transform:scale(1.5);opacity:.6}}
#bx{position:absolute;bottom:64px;right:0;width:316px;background:var(--s);border-radius:18px;overflow:hidden;box-shadow:0 16px 48px #00000066,0 0 0 1px #fff1;transform:translateY(8px);opacity:0;pointer-events:none;transition:transform .2s,opacity .2s}
#bx.open{transform:none;opacity:1;pointer-events:all}
#hd{padding:12px 14px;display:flex;align-items:center;gap:9px;border-bottom:1px solid #fff1}
#av{width:29px;height:29px;border-radius:8px;background:var(--a);display:flex;align-items:center;justify-content:center;flex-shrink:0}
#av svg{width:15px;height:15px}
#hn{font-family:'Syne',sans-serif;font-size:13px;font-weight:700;color:#fff}
#hs{font-size:10px;color:#22d3a5}
#cl{margin-left:auto;background:none;border:none;cursor:pointer;color:#fff4;font-size:15px;padding:2px 4px}
#cl:hover{color:#fff}
#ms{height:232px;overflow-y:auto;padding:10px;display:flex;flex-direction:column;gap:7px;scroll-behavior:smooth;scrollbar-width:none}

.b{max-width:85%;padding:7px 11px;font-size:12.5px;line-height:1.55;animation:fu .2s forwards}
@keyframes fu{from{opacity:0;transform:translateY(5px)}to{opacity:1;transform:none}}
.bo{background:var(--d);color:var(--t);border-radius:10px 10px 10px 2px;align-self:flex-start}
.bu{background:var(--a);color:#fff;border-radius:10px 10px 2px 10px;align-self:flex-end}
.ty{display:flex;gap:4px;padding:7px 11px;background:var(--d);border-radius:10px 10px 10px 2px;align-self:flex-start}
.td{width:5px;height:5px;border-radius:50%;background:var(--a);animation:bc .8s infinite}
.td:nth-child(2){animation-delay:.13s}.td:nth-child(3){animation-delay:.26s}
@keyframes bc{40%{transform:translateY(-4px)}}
#ft{padding:8px 10px;border-top:1px solid #fff1;display:flex;gap:7px;align-items:center;background:#0c1424}
#ip{flex:1;background:var(--d);border:none;border-radius:9px;padding:8px 10px;color:var(--t);font-family:inherit;outline:none;resize:none;max-height:60px}
#ip::placeholder{color:#3d5070}
#sn{width:30px;height:30px;border-radius:8px;background:var(--a);border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;flex-shrink:0}
#sn svg{width:12px;height:12px;fill:#fff}
</style>
<div id=sw><div id=bx><div id=hd>
<div id=av><svg viewBox="0 0 24 24"><rect x=7 y=11 width=10 height=8 rx=2 fill=white/><circle cx=9.5 cy=15 r=1 fill=#3A59FF/><circle cx=14.5 cy=15 r=1 fill=#3A59FF/><path d="M12 11V8M7 14H5M17 14h2" stroke=white stroke-width=1.5 stroke-linecap=round/><circle cx=12 cy=7 r=1.5 fill=white/></svg></div>
<div><div id=hn>Syntaro Solutions</div><div id=hs>● Online</div></div><button id=cl>✕</button></div>
<div id=ms></div>
<div id=ft><textarea id=ip rows=1 placeholder="Ask me anything..."></textarea><button id=sn><svg viewBox="0 0 24 24"><path d="M2 21l21-9L2 3v7l15 2-15 2v7z"/></svg></button></div></div>
<button id=sb><svg viewBox="0 0 24 24"><path d="M20 2H4c-1.1 0-2 .9-2 2v18l4-4h14c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2z"/></svg><div id=sp></div></button></div>
<script>
const[ms,ip,bx]=['ms','ip','bx'].map(id=>document.getElementById(id)),g=id=>document.getElementById(id);let sid='s'+Date.now();
const add=(t,u)=>{let d=document.createElement('div');d.className='b '+(u?'bu':'bo');d.textContent=t;ms.appendChild(d);ms.scrollTop=9e9},showT=()=>{let d=document.createElement('div');d.className='ty';d.id='ty';d.innerHTML='<div class=td></div>'.repeat(3);ms.appendChild(d);ms.scrollTop=9e9},hideT=()=>g('ty')?.remove(),send=async()=>{let t=ip.value.trim();if(!t)return;add(t,1);ip.value='';showT();try{let j=await(await fetch('https://syntaroai.app.n8n.cloud/webhook/35eebe44-8cdd-43d3-b526-24b7fb7be2bd/chat',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({action:'sendMessage',sessionId:sid,chatInput:t})})).json();hideT();add(j.output||"On it!",0)}catch{hideT();add('Error, try again.',0)}};
g('sb').onclick=()=>{let o=bx.classList.toggle('open');if(o&&!ms.children.length){setTimeout(()=>add('Hi! I'm Syntaro AI Assistant 🤖',0),150);setTimeout(()=>add('How can I help?',0),600)}};
g('cl').onclick=()=>bx.classList.remove('open');g('sn').onclick=send;
ip.onkeydown=e=>{if(e.key==='Enter'&&!e.shiftKey){e.preventDefault();send()}};
ip.oninput=()=>{ip.style.height='auto';ip.style.height=Math.min(ip.scrollHeight,60)+'px'};
</script>

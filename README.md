[index.html](https://github.com/user-attachments/files/35031185/index.html)
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Государственные символы РФ — тест</title>
<style>
*{box-sizing:border-box}body{margin:0;font-family:system-ui,-apple-system,Segoe UI,Roboto,sans-serif;background:linear-gradient(135deg,#eef4ff,#f7f8fc);color:#172033;padding:18px}
main{max-width:760px;margin:24px auto;background:white;border-radius:22px;padding:clamp(18px,4vw,32px);box-shadow:0 12px 40px #1d355715}
header{text-align:center;margin-bottom:24px}h1{font-size:clamp(24px,5vw,34px);margin:8px 0}header p{color:#657087}
.progress{height:9px;background:#e8edf5;border-radius:99px;overflow:hidden;margin:20px 0}.bar{height:100%;background:#315de7;width:0;transition:.25s}
.q{padding:18px 0;border-bottom:1px solid #edf0f5}.q h3{font-size:18px;margin:0 0 12px}.opts{display:grid;gap:9px}
label.opt{display:flex;gap:10px;align-items:flex-start;padding:12px 14px;border:1px solid #dce3ee;border-radius:12px;cursor:pointer;transition:.15s}
label.opt:hover{background:#f5f7ff;border-color:#9db1f8}input{margin-top:3px;accent-color:#315de7}
button{border:0;border-radius:12px;background:#315de7;color:white;font-size:16px;font-weight:700;padding:14px 18px;cursor:pointer;margin-top:20px;width:100%}button:hover{background:#2448c6}
#result{display:none;text-align:center;padding:22px 0}.score{font-size:42px;font-weight:800;color:#315de7}.small{color:#68748a}
</style>
</head>
<body><main>
<header>
<div style="font-size:36px">🇷🇺</div>
<h1>Государственные символы РФ</h1>
<p>Тест по обществознанию · 15 вопросов</p>
</header>
<div class="progress"><div class="bar" id="bar"></div></div>
<form id="quiz"></form>
<section id="result"></section>
<script>
const questions = [
["Какие символы являются государственными символами Российской Федерации?",["Герб, флаг и гимн","Конституция, паспорт и герб","Флаг, президент и столица","Гимн, парламент и флаг"],0],
["Как выглядит Государственный флаг РФ?",["Три вертикальные полосы: белая, синяя, красная","Три горизонтальные полосы: белая, синяя, красная","Три горизонтальные полосы: красная, синяя, белая","Белое полотнище с красным крестом"],1],
["Какой цвет находится на флаге РФ сверху?",["Красный","Синий","Белый","Золотой"],2],
["Что изображено на Государственном гербе РФ?",["Синий щит с белым орлом","Золотой двуглавый орёл на красном щите","Белый медведь на синем щите","Три звезды на красном фоне"],1],
["Сколько голов у орла на гербе России?",["Одна","Три","Две","Четыре"],2],
["Что держит орёл на гербе РФ в правой лапе (со стороны изображённого орла)?",["Скипетр","Меч","Факел","Ветвь"],0],
["Что держит орёл на гербе РФ в левой лапе (со стороны изображённого орла)?",["Корону","Державу","Щит","Знамя"],1],
["Какой музыкальный символ является государственным символом России?",["Народная песня «Калинка»","Марш «Прощание славянки»","Государственный гимн РФ","Любая патриотическая песня"],2],
["Кто является автором музыки современного гимна РФ?",["Пётр Чайковский","Александр Александров","Михаил Глинка","Сергей Прокофьев"],1],
["Кто написал слова современного гимна РФ?",["Сергей Михалков","Александр Пушкин","Александр Твардовский","Василий Лебедев-Кумач"],0],
["В каких случаях обычно исполняется государственный гимн?",["Только на школьных линейках","На официальных церемониях и важных государственных мероприятиях","Только на спортивных тренировках","Только в кино"],1],
["Что выражают государственные символы?",["Личные вкусы граждан","Единство, суверенитет и государственную идентичность страны","Только историю одной области","Спортивные достижения"],1],
["Как следует вести себя при официальном исполнении гимна РФ?",["Разговаривать громко","Продолжать заниматься своими делами","Стоять уважительно, если это предусмотрено церемонией","Обязательно хлопать в ладоши"],2],
["Где закреплены положения о государственных символах России?",["В Конституции РФ и федеральных конституционных законах","Только в школьном уставе","Только в указах губернаторов","В правилах спортивных федераций"],0],
["Какой щит расположен на груди двуглавого орла на гербе РФ?",["С изображением всадника, поражающего дракона","С изображением корабля","С изображением солнца и луны","С изображением трёх гор"],0]
];
const form=document.getElementById("quiz");
questions.forEach((q,i)=>{
 const block=document.createElement("section");block.className="q";
 block.innerHTML=`<h3>${i+1}. ${q[0]}</h3><div class="opts">${q[1].map((a,j)=>`<label class="opt"><input type="radio" name="q${i}" value="${j}"><span>${a}</span></label>`).join("")}</div>`;
 form.appendChild(block);
});
const bar=document.getElementById("bar");
form.addEventListener("change",()=>{let n=questions.filter((_,i)=>form.querySelector(`input[name=q${i}]:checked`)).length;bar.style.width=(n/questions.length*100)+"%"});
form.insertAdjacentHTML("beforeend",'<button type="submit">Завершить тест</button>');
form.addEventListener("submit",e=>{
 e.preventDefault();let score=0,answered=0;
 questions.forEach((q,i)=>{let a=form.querySelector(`input[name=q${i}]:checked`);if(a){answered++;if(+a.value===q[2])score++}});
 const grade=score>=13?5:score>=10?4:score>=7?3:2;
 form.style.display="none";bar.style.width="100%";
 const r=document.getElementById("result");r.style.display="block";
 r.innerHTML=`<h2>Тест завершён!</h2><div class="score">${score} / ${questions.length}</div><p>Отвечено: ${answered} из 15</p><h2>Оценка: ${grade}</h2><p class="small">${grade===5?"Отличный результат!":grade===4?"Хорошая работа!":grade===3?"Неплохо, но стоит повторить тему.":"Попробуй повторить тему и пройти тест ещё раз."}</p><button onclick="location.reload()">Пройти заново</button>`;
});
</script>
</main></body></html>

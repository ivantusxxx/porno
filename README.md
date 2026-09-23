<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>STROY RENT</title>

<style>

*{
box-sizing:border-box;
margin:0;
padding:0;
font-family:Arial,sans-serif
}

body{
background:#f4f4f4;
color:#111
}

header{
height:90px;
background:#fff;
display:flex;
align-items:center;
justify-content:space-between;
padding:0 8%;
}

.logo{
font-size:32px;
font-weight:900;
}

.logo span{
color:#e5a000;
}

nav a{
margin-left:25px;
text-decoration:none;
color:#222;
}


.hero{

height:560px;

background:
linear-gradient(
rgba(0,0,0,.55),
rgba(0,0,0,.8)
),
url("https://images.unsplash.com/photo-1504307651254-35680f356dfd")
center/cover;

color:white;
display:flex;
align-items:center;
padding:0 8%;

}

.hero h1{
font-size:60px;
max-width:800px;
}

.hero p{
font-size:24px;
margin:20px 0;
}

.price-main{
font-size:35px;
font-weight:bold;
color:#e5a000;
}


button{
background:#e5a000;
border:0;
padding:15px 35px;
border-radius:10px;
font-weight:bold;
cursor:pointer;
}



section{
padding:70px 8%;
}


h2{
font-size:40px;
margin-bottom:35px;
}



.categories{

display:grid;
grid-template-columns:repeat(6,1fr);
gap:15px;

}


.category{

background:white;
padding:25px 10px;
border-radius:15px;
text-align:center;
font-weight:bold;

}



.cards{

display:grid;
grid-template-columns:repeat(4,1fr);
gap:25px;

}



.card{

background:white;
border-radius:20px;
overflow:hidden;
box-shadow:0 10px 30px #0002;

}



.card img{

width:100%;
height:220px;
object-fit:cover;

}


.card-body{

padding:20px;

}


.card h3{
font-size:23px;
}


.card p{

margin-top:10px;
color:#666;

}


.cost{

margin-top:15px;
font-size:25px;
font-weight:bold;
color:#e5a000;

}


.card button{

width:100%;
margin-top:20px;
background:#111;
color:white;

}



.advantages{

background:white;

display:grid;
grid-template-columns:repeat(4,1fr);
gap:20px;

}


.adv{

background:#f3f3f3;
padding:30px;
border-radius:20px;

}



.modal{

display:none;
position:fixed;
inset:0;
background:#0009;
align-items:center;
justify-content:center;

}


.modal-box{

background:white;
padding:35px;
border-radius:20px;
width:400px;

}


.modal-box input{

width:100%;
padding:15px;
margin:20px 0;

}



.close{

float:right;
cursor:pointer;
font-size:25px;

}


footer{

background:#111;
color:white;
padding:40px 8%;

}



@media(max-width:1000px){

.cards{
grid-template-columns:repeat(2,1fr);
}

.categories{
grid-template-columns:repeat(3,1fr);
}

}


@media(max-width:600px){

.cards,
.categories,
.advantages{

grid-template-columns:1fr;

}

.hero h1{

font-size:38px;

}

}

</style>

</head>


<body>


<header>

<div class="logo">
STROY <span>RENT</span>
</div>


<nav>
<a href="#">Техника</a>
<a href="#">Услуги</a>
<a href="#">Контакты</a>
</nav>

</header>




<div class="hero">

<div>

<h1>
Аренда строительной техники
</h1>

<p>
Экскаваторы, самосвалы, траллы и спецтехника
</p>

<div class="price-main">
100 BYN / час
</div>


<button onclick="scrollTech()">
Выбрать технику
</button>

</div>

</div>





<section>

<h2>
Категории
</h2>

<div class="categories">

<div class="category">🚜 Экскаваторы</div>
<div class="category">🚚 Самосвалы</div>
<div class="category">🛣 Катки</div>
<div class="category">🚛 Фуры</div>
<div class="category">🛻 Траллы</div>
<div class="category">🏗 Краны</div>

</div>

</section>






<section id="tech">

<h2>
Техника в аренду
</h2>


<div class="cards" id="cards"></div>


</section>







<section class="advantages">

<div class="adv">
<h3>✓</h3>
Свой парк техники
</div>

<div class="adv">
<h3>✓</h3>
Опытные операторы
</div>

<div class="adv">
<h3>✓</h3>
Быстрая подача
</div>

<div class="adv">
<h3>✓</h3>
Работа 24/7
</div>

</section>







<div class="modal" id="modal">

<div class="modal-box">

<div class="close" onclick="closeModal()">×</div>


<h2 id="title">
</h2>


<p>
Стоимость:
<b>100 BYN / час</b>
</p>


<input placeholder="Ваш телефон">


<button>
Отправить заявку
</button>


</div>

</div>






<footer>

STROY RENT © 2026

</footer>





<script>


let tech=[

["Экскаватор","https://images.unsplash.com/photo-1509391366360-2e959784a276"],
["Самосвал","https://images.unsplash.com/photo-1590496793929-36417d3117de"],
["Дорожный каток","https://images.unsplash.com/photo-1581093458791-9d42e3c9f8f2"],
["Фура","https://images.unsplash.com/photo-1601584115197-04ecc0da31d3"],
["Тралл","https://images.unsplash.com/photo-1577905607694-88b0c0f8dce4"],
["Низкорамный трал","https://images.unsplash.com/photo-1504307651254-35680f356dfd"],
["Погрузчик","https://images.unsplash.com/photo-1586864387967-d02ef85d93e8"],
["Бульдозер","https://images.unsplash.com/photo-1541888946425-d81bb19240f5"],
["Автокран","https://images.unsplash.com/photo-1504307651254-35680f356dfd"],
["Манипулятор","https://images.unsplash.com/photo-1581092918056-0c4c3acd3789"]

];


let box=document.getElementById("cards");


tech.forEach(item=>{

box.innerHTML+=`

<div class="card">

<img src="${item[1]}">

<div class="card-body">

<h3>${item[0]}</h3>

<p>
Работа с оператором
</p>

<p>
Для строительных работ
</p>


<div class="cost">
100 BYN / час
</div>


<button onclick="openModal('${item[0]}')">
Арендовать
</button>

</div>

</div>

`;

});




function openModal(name){

document.getElementById("modal")
.style.display="flex";


document.getElementById("title")
.innerHTML=name;

}



function closeModal(){

document.getElementById("modal")
.style.display="none";

}



function scrollTech(){

document.getElementById("tech")
.scrollIntoView({
behavior:"smooth"
});

}


</script>


</body>
</html>

<p></p>

<h2 align="center">ФЕДЕРАЛЬНОЕ ГОСУДАРСТВЕННОЕ БЮДЖЕТНОЕ ОБРАЗОВАТЕЛЬНОЕ УЧРЕЖДЕНИЕ ВЫСШЕГО ПРОФЕССИОНАЛЬНОГО ОБРАЗОВАНИЯ <br> «САХАЛИНСКИЙ ГОСУДАРСТВЕННЫЙ УНИВЕРСИТЕТ» <br> КАФЕДРА ИНФОРМАТИКИ </h2>
<p align="center">Лабораторная работа №4 <br>
по курсу «Web-технологии, языки и средства создания web-приложений» 

<p align="center"><b>"Node.js"</b><p>
<p align="right"><b>Выполнила: </b> студентка 331 группы Витковская Полина</p>
<p  align="right"><b>Принял: </b> Соболев Е. И., старший преподователь</p>
<br>
<br>
<br>
<p align="center">Южно-Сахалинск <br> СахГУ <br> 2023</p>
<h2> Введение </h2>
<p>Лабораторные работы по дисциплине «Web-технологии, языки и средства создания web-приложений» предназначены для освоения полученных теоретических знаний на практике. Перед началом лабораторной работы были поставлены цели: <br>
<ol>
  <li>Овладеть навыками работы с node.js. Используя Java Script, решить задачи.
</ol>
В соответствии с данными целями необходимо решить следующие задачи:
<ol>
   <li> Написать скрипты для решения данных задач.
   </ol>
Для реализации данной работы будет использоваться Visual Studio Code. Выполнение кода будет происходить в браузере Google Chrome с использованием node.js.
</p>
<h2>Решение задач</h2>
<p>Файл, запускающий сервер на node.js: </p>
<code>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <script>
alert("Лабораторная 4");
//1
{
    let x = parseInt(prompt("Введите x"));
if (x > 0)
    alert(Math.pow(Math.sin(x), 2));
else
    alert(1 - 2 * Math.sin(x*x));  
}
//2
{
    let n = parseInt(prompt("Введите n"));
let temp = n;
let reverse = 0;
while (temp > 0){
    reverse  = reverse * 10 + temp % 10;
    temp = Math.round(temp / 10);
}
alert(n == reverse);
}
//3
{
    let n = parseInt(prompt("Введите n"));

if(n % 4 == 0 & (n % 100 != 0 || n % 400 == 0))
    alert("Год високосный");
else
    alert("Год не високосный"); 
}
//4
{

    let x = parseInt(prompt("Введите x"));
    alert(y(x));


function y(x)
{
    if (x < -1) return -1;
    if (x > -1) return x;
    if (x == -1) return 1;
}
}
//5
{
    let n = parseInt(prompt("Введите номер месяца"));

if (n == 12 || n == 1 || n == 2) alert("Зима");
else if (3 <= n && n <= 5) alert("Весна");
else if (6 <= n && n <= 8) alert("Лето");
else if (9 <= n && n <= 11) alert("Осень");
else alert("Неверный ввод");  
}
//6
{
    let m = parseInt(prompt("Введите номер масти"));
let k = parseInt(prompt("Введите номер карты"));
let mast = "";
let card = "";
switch (m)
{
    case 1:
        mast += "пики";
        break;
    case 2:
        mast += "трефы";
        break;
    case 3:
        mast += "бубны";
        break;
    case 4:
        mast += "червы";
        break;
    default:
        alert("Неверный ввод m");
        return;
}

switch (k)
{
    case 6:
        card = "Шестерка";
        break;
    case 7:
        card = "Семерка";
        break;
    case 8:
        card = "Восьмерка";
        break;
    case 9:
        card = "Девятка";
        break;
    case 10:
        card = "Десятка";
        break;
    case 11:
        card = "Валет";
        break;
    case 12:
        card = "Дама";
        break;
    case 13:
        card = "Король";
        break;
    case 14:
        card = "Туз";
        break;
    default:
        alert("Неверный ввод k");
        return;
}
alert(card +" "+ mast);
}
//7
{
    let n = parseInt(prompt("Введите год"));
n = n % 60;
let animal = ["Обезьяна", "Петух", "Собака", "Свинья", "Крыса", "Корова", "Тигр", "Заяц", "Дракон", "Змея", "Лошадь", "Овца"];
let color = ["Белый","Белый","Черный", "Черный", "Зеленый", "Зеленый", "Красный", "Красный", "Желтый", "Желтый"];
let num_animal = n % 12;
let num_color = n % 10;
alert(`${animal[num_animal]} ${color[num_color]}`);
}
//8
{
    let style = "<style>table, th, td {border: 1px solid black;}</style>\n"
let result = "<table style='border: 1px solid black'>\n<tr>\n";
for(let i = 1; i <= 9; i++)
{
    result+=`<th>${i}</th>\n`;
}
result+="</tr>\n<tr>\n";
for(let i = 1; i <= 9; i++)
    result += `<td>${i * 9}</td>\n`
result += "</tr>\n</table>";

document.write(style + result); 
}
//9
{
    let result = "";
for(let i = 1; i <= 20; i++)
{
    result += `sin ${i} = ${Math.sin(i)}<br>`;
}
document.write(result);
}
//10
{
    let result = 0;
for(let i = 100; i <=500; i++)
    result+= i;
alert(`a) Сумма от 100 до 500 =  ${result}`);

let a = parseInt(prompt("Введите a"));
if(a > 500) {
    alert("Число больше 500!");
    return;
}
result = 0;
for(let i = a; i <=500; i++)
    result+= i;
alert(`б) Сумма от ${a} до 500 =  ${result}`);

let b = parseInt(prompt("Введите b"));
if(b < -10)
{
    alert("Число меньше -10!");
    return;
}
result = 0;
for(let i=-10; i <= b; i++)
{
    result += i;
}
alert(`в) Сумма от -10 до ${b} =  ${result}`);

a = parseInt(prompt("Введите a"));
b = parseInt(prompt("Введите b"));

if (a > b) {
    alert("Число a больше b!");
    return;
}
result = 0;
for (let i = a; i <= b; i++)
    result+=i;
alert(`г) Сумма от ${a} до ${b} = ${result}`);
}
//11
{
    let n = parseInt(prompt("Введите n"));
let result = 1;
for(let i = 1; i <= n; i++)
    result+= 1/i;
alert(`Сумма равна ${result}`);
}
//12
{
    let x = parseInt(prompt("Введите x"));
let y = parseInt(prompt("Введите y"));

let result = x;


for(let i = 1; i < y; i++)
    result += x;
alert(`${x} * ${y} = ${result}`);
}
//13
{
    let n = parseInt(prompt("Введите n"));
let result = 0;
for (let i = 1; i <= n ; i++)
    result += 2 * i - 1;
alert(`${n}^2 = ${result}`);
}
//14
{
    let n = 0;
for (let i = 50; i >= 1; i--)
{
    n= Math.sqrt(i + n);
}
alert(n);
}
//15
{
let array = [1, 2, 3, 4, 5, 6, 0];
let result = 0;
let length = 0;
for(let i = 0; array[i] != 0; i++)
{
    result += array[i];
    length++;
}
alert(`Сумма = ${result}`);
alert(`Кол-во чисел = ${length}`);}
//16
{
    let array = [1, 2, 3, 4, 5, -6];
let result = 0;
for(let i = 0; array[i] >= 0; i++)
{
result+= array[i];
}
alert(`Среднее = ${result / (array.length - 1)}`);
}
//17
{let n = prompt('Введите число n');
let a = 0, b = 0, c = 0,
    g = 0, d = 1, e = 0;

for(let i = 0; i < n.length; i++)
{
    if (n[i] == '3') a++;
    if (n[i] == n[n.length - 1]) b++;
    if (parseInt(n[i]) % 2 == 0) c++;
    if (parseInt(n[i]) > 5) g+= parseInt(n[i]);
    if (parseInt(n[i]) > 7) d*= parseInt(n[i]);
    if (n[i] == '0') e++;
    if (n[i] == '5') e++;
}

alert(`а) ${a}
б) ${b}
в) ${c}
г) ${g}
д) ${d}
е) ${e}`)}
//18
{let n = prompt('Введите число n');
let max = 0;
let maxRe = 0;
let min = 0;
let minRe = 0;

for(let i = 0; i < n.length; i++)
    if (n[i] > n[max]) max = i;

maxRe = -1 * (max - n.length);
max++;
for(let i = 0; i < n.length; i++)
    if (n[i] < n[min]) min = i;

minRe = -1 * (min - n.length);
min++;
alert(`а) от конца числа: ${maxRe} \nот начала числа ${max}
б) от конца числа: ${minRe}\nот начала числа: ${min}`);
}
//19
{let n = parseInt(prompt('Введите число n'));
let value = 2;
while(value != n)
{
    if (n % value == 0)
    {
        alert("Число не простое");
        return;
    } 
    value++;
}
alert("Число простое");}
//20
{let n = prompt('Введите число n');

for(let i = 0; i < n.length - 1; i++)
    if (n[i] >= n[i + 1]) 
    {
        alert("false");
        return;
    }
alert('true');}
//21
{let array = [];
for (let i = 1; i <= 10000; i++)
    array.push(i);

let n = parseInt(prompt('Введите число n'));
for (let i = 0; i < array.length; i++)
{
    if (array[i] > n)
    {
        alert(i);
        return;
    }
}
alert('Нет такого числа');}
//22
{let n = prompt('Введите число n');
let a = prompt("Введите цифру a"), acount = 0;
let b = prompt("Введите цифру b"), bcount = 0;

for(let i = 0; i < n.length; i++)
{
    if (n[i] == a) acount++;
    if (n[i] == b) bcount++;
}
alert(acount < bcount);}
//23
{
    let str = "";
let value = 10;
let max = 30;

while (value <= 30)
{
    str+=`${value}\n`;
    value++;
}

alert(str);

str = "";
value = 10;

do{
    str+=`${value}\n`;
    value++;
} while (value <= 30);

alert(str);
}
    </script>
    
</body>
</html>
</code>
<p>Также были выполнены задачи на codewars.</p>
<code>
  function head(array) {
  return array[0];
}

function last(array) {
  return array[array.length - 1];
}

function init(array) {
  return array.slice(0, array.length - 1);
}

function tail(array) {
  return array.slice(1, array.length);
}

function deepCount(a){
  let length = 0;
  for(let i = 0; i < a.length; i++){
    if (typeof a[i] == 'object')
      length += deepCount(a[i]);
    length ++;
  }
  return length;
}

function numberOfPairs(array)
{
  let gloves = array.slice(0);
  let pair = 0;
  let i = 0;
  while(i != gloves.length){
    let flag = true;
    
    for(let j = i + 1; j < gloves.length; j++){
      if(gloves[i] == gloves[j]){
        pair++;
        gloves.splice(i, 1);
        gloves.splice(j - 1, 1);
        flag = false;
        break;
      }
    }
    
    if (flag) i++;
  }
  return pair;
}

function sortByBit(arr) {
  
  for(let i = 0; i < arr.length; i++){
    for(let j = i + 1; j < arr.length; j++){
      one_i = countOne(arr[i].toString(2));
      one_j = countOne(arr[j].toString(2));
      
      if(one_i > one_j)
      {
        let temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
      } else if(one_i == one_j)
      {
        if (arr[i] > arr[j]){
            let temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;
        }
      }
    }
  }
}
  
function countOne(str){
  let count = 0;
  for(let i = 0; i < str.length; i++)
    if (str[i] == '1') count++;
  
  return count;
}
function recycle(array) {
  let paper = [];
  let glass = [];
  let organic = [];
  let plastic = [];
  
  for(let i = 0; i < array.length; i++){
    if(Object.keys(array[i]).length == 3){
      switch (array[i].secondMaterial){
          case 'paper':
            paper.push(array[i].type);
            break;
          case 'glass':
            glass.push(array[i].type);
            break;
          case 'organic':
            organic.push(array[i].type);
            break;
          case 'plastic':
            plastic.push(array[i].type);
            break;
      }
    } 
    
     switch (array[i].material){
          case 'paper':
            paper.push(array[i].type);
            break;
          case 'glass':
            glass.push(array[i].type);
            break;
          case 'organic':
            organic.push(array[i].type);
            break;
          case 'plastic':
            plastic.push(array[i].type);
            break;
      }
  }
  return [paper, glass, organic, plastic]
}
function getLengthOfMissingArray(arrayOfArrays) {
  if (arrayOfArrays === null || arrayOfArrays.length == 0) return 0;
  
  let array = [];
  for(let i = 0; i < arrayOfArrays.length; i++){
    if (arrayOfArrays[i] === null || arrayOfArrays[i].length == 0) return 0;
    array.push(arrayOfArrays[i].length);
  }
  array = array.sort((a,b)=>a-b);
  for(let i = 0; i < array.length-1; i++)
  {
    if (array[i + 1] != array[i] + 1)
      return array[i] + 1;
  }
}
</code>
<h2>Вывод</h2>
<p>В ходе лабораторной работы были решены задачи на Java Script, а также написан бот для телеграмма с помощью grammy API. Выполнение происходило с помощью Node.js</p>

<!DOCTYPE html>
<html><head>
<style>
header {
 
  	padding: 15px;
 	font-size: 15px;
	background-color: black;
 	text-align: center;
 	color: white;
}
#t1 th{
text-align:left;
width:500px;
}

</style>
</head>
<body onload="showDiv3()">
<script>
function showDiv3() {
   document.getElementById('mine').style.display = "none";
  document.getElementById('one').style.display = "block"; 
}
</script>
<header>
<div >PHONE DIRECTORY</div></header>

<br>
<br>

<div id="one" >
&nbsp;
<button style='color: white ;background-color: green; padding: 5px;' onclick="showDiv1()">ADD</button>
<script>
function showDiv1() {
   document.getElementById('mine').style.display = "block";
  document.getElementById('one').style.display = "none"; 
}
</script>
<br>

&nbsp;
<table id="t1">
<tr>
<th >NAME </th>
<th >PHONE</th></tr>
</table>
</div>

<div id="mine">
&nbsp;
<button style='color: black;background-color:white ; padding: 5px;' onclick="showDiv2()">BACK</button>
<script>
function showDiv2() {
document.getElementById('one').style.display = "block";
   document.getElementById('mine').style.display = "none"; 
}
</script>

<br>
<br>
NAME:<br>
<input id="nam"  type =text pattern=[a-z][A-Z] ><br><br>
PHONE:<br>
<input id="mob"  pattern=[0-9]{10} ><br><p>details being added:</p>
<p>name:<span id="re"><br></span></p>
<p>mobile:<span id="res"></span></p>

<script>
  nam.oninput = function() {
    re.innerHTML = nam.value;
  };
</script>
<script>
  mob.oninput = function() {
    res.innerHTML = mob.value;
  };
</script>
<button onclick="functional11()">ADD</button>
<script>
function functional11(){
var x=document.getElementById('nam').value;
var y=document.getElementById('mob').value;
if ( x  != '' && y != ''){
functional1();
}
else if(x != '' && y == ''){
alert("enter phone number");
}
else if(x == '' && y != ''){
alert("enter name");
}
else{
alert("enter name and phone number");}


}
function functional1(){
document.getElementById('one').style.display = "block";
   document.getElementById('mine').style.display = "none"; 
var x=document.getElementById('nam').value;
var y=document.getElementById('mob').value;
var tab=document.getElementById("t1");
 var row=tab.insertRow(-1);
 var cell1=row.insertCell(0);
 var cell2=row.insertCell(1);
 var cell3=row.insertCell(2);
 var btn= "<input type='button' style='color:black ; background-color:red;' value='delete' onclick='del(this);'>";
 cell1.innerHTML=x;
	cell2.innerHTML=y;
	cell3.innerHTML=btn;
document.getElementById('nam').value='';
document.getElementById('mob').value='';
document.getElementById('re').innerHTML='';
document.getElementById('res').innerHTML='';

}
function del(r){
var i=r.parentNode.parentNode.rowIndex;
document.getElementById("t1").deleteRow(i);
}
</script>
</div>

</body>
</html>

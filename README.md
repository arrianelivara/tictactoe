<html>
<head>
 <title>Tic Tac Toe</title>
 <meta charset="utf-8">
 <meta http-equiv="X-UA-Compatible" content="IE=edge">
 <meta name="viewport" content="width=device-width, initial-scale=1">
 <link href="scripts/bootstrap/css/bootstrap.min.css" rel="stylesheet" />
 <link href="scripts/toastr.css" rel="stylesheet" />
 <link href="scripts/bootstrap/css/datepicker.css" rel="stylesheet" />
 
</head>
<style>
body{
background-image: url("bg.jpg");
}
table tr td{
	height: 100px;
	width:100px;
	text-align:center;
	font-size:26px;
    border:5px solid white;
    background-image: url("bg.png");
.score{
	font-size:32px;
	
}
</style>
<body>

<h1 style="font-family:AR HERMANN;color:red;font-size:350%;text-align:center"> TIC TAC TOE </h1>

<div style="text-align:center;">
<input type="button" value="New Game" id="btn" onClick = "New()" />
</div>
<br>
<table id="tbl1" border="1" cellpadding="50" align="center" >
	<tr>
    	<td id="c1" class="c"></td>
        <td id="c2" class="c"></td>
        <td id="c3" class="c"></td>
    </tr>
    <tr>
    	<td id="c4" class="c"></td>
        <td id="c5" class="c"></td>
        <td id="c6" class="c"></td>
    </tr>
    <tr>
    	<td id="c7" class="c"></td>
        <td id="c8" class="c"></td>
        <td id="c9" class="c"></td>
    </tr>
</table>
<table id="tbl2" align="center">
	<tr>
    	<th colspan="2"><h4 style="font-family:Arial;color:white;font-size:250%;text-align:center">Score</h4></th>
    </tr>
    <tr>
    	<th><h4 style="font-family:Arial;color:white;font-size:150%;text-align:center">Player X </h4></th>
        <th><h4 style="font-family:Arial;color:white;font-size:150%;text-align:center">Player O</h4></th>
    </tr>
    <tr>
    	<td class="score" id="p1score" style="color:white;">0</td>
        <td class="score" id="p2score" style="color:white;">0</td>
    </tr>
</table>
</body>

 <script src="scripts/jquery.min.js"></script>
 <script src="scripts/bootstrap/js/bootstrap.min.js"></script>
 <script src="jquery-1.4.2.min.js"></script>
 <script>
 $(document).ready(function(){

	var p1 = 0;
	var p2 = 0;
	
	function Winner(){
	

		if(p1==6){

			alert("Congratulations Player X!");
			$(".c").html("");
			x=0;
			p1=0;
			p2=0;
			$("#p1score").html(p1);
			$("#p2score").html(p2);
			counter=0;
			
		}
		if(p2==6){
				alert("Congratulations Player O!");
			$(".c").html("");
			x=0;
			p1=0;
			p2=0;
			$("#p1score").html(p1);
			$("#p2score").html(p2);
			counter=0;
		}
	}

	function checkifWon(a){
		var w = false;

		if ($("#c1").html()==a && $("#c2").html()==a && $("#c3").html()==a){
			w = true;
		}
		if ($("#c4").html()==a && $("#c5").html()==a && $("#c6").html()==a){
			w = true;
		}
		if ($("#c7").html()==a && $("#c8").html()==a && $("#c9").html()==a){
			w = true;
		}
		if ($("#c1").html()==a && $("#c4").html()==a && $("#c7").html()==a){
			w = true;
		}
		if ($("#c2").html()==a && $("#c5").html()==a && $("#c8").html()==a){
			w = true;
		}
		if ($("#c3").html()==a && $("#c6").html()==a && $("#c9").html()==a){
			w = true;
		}
		if ($("#c1").html()==a && $("#c5").html()==a && $("#c9").html()==a){
			w = true;
		}
		if ($("#c3").html()==a && $("#c5").html()==a && $("#c7").html()==a){
			w = true;
		}

		if(counter==9){
				$(".c").html("");
				x=0;
				counter=0;
		}

		if (w){
			
			if (checker=="x"){
				alert("Player X Wins!");
				p1 = p1 + 1;
				$("#p1score").html(p1);
				$(".c").html("");
				x=0;
				counter=0;
				Winner();
				
			}else {
				alert("Player O Wins!");
				p2 = p2 + 1;
				$("#p2score").html(p2);
				$(".c").html("");
				x=0;
				counter=0;
				Winner();
			}
			
			
		}
	}

	
	var x = 0;
	var checker;
	var counter=0;
	$(".c").click(function(){
		if ($(this).html()=="") {
			if (x % 2 ==0){
				$(this).html("<img src='x.png' width='50'height='50'/>");
				checker = "x";
				counter++;
			} else {
				$(this).html("<img src='o.png' width='50'height='50'/>");
				checker = "o";
				counter++;
			}
		}
		x = x+1;
		checkifWon($(this).html());
	});
	
	$("#btn").click(function(){
		$(".c").html("");
		x=0;
		p1=0;
		p2=0;
		counter=0;
		$("#p1score").html(p1);
		$("#p2score").html(p2);
		
	});

function New() {
	window.open("tic tac toe.html" , "_self").close
}
	
});
 </script>
</body>
</html>

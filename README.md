<!DOCTYPE html>
<html>
    <head>
	    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
        <title>Play Rock Paper Scissors!</title>
        <script>
            $(document).ready(function(){
                var humanscores = new Array;
                var botscores = new Array;
                var humanscore = 0;
                var botscore = 0;

                $(".btn").click(function(){
                location.reload();
                });
                $("button").click(function(){
                    var userChoice = $(this).attr("id");
                    $("strong").html("You chose...");
                    $("b").html("Bot chose...");
                var pc = "rock";
		        var bot = Math.floor(Math.random()*3) + 1;
                switch (bot){
			    case (1):
				    var pc = "rock";
                    $("#gen").attr('src','https://i.ibb.co/DW37hVz/rock.png');
                    $("#gen").attr('alt','rock');
				    break;
			    case (2):
				    var pc = "paper";
                    $("#gen").attr('src','https://i.ibb.co/FJPpQgf/paper.png');
                    $("#gen").attr('alt','paper');
				    break;
			    case (3):
				    var pc = "scissors";
                    $("#gen").attr('src','https://i.ibb.co/tbjDkkz/scissors.png');
                    $("#gen").attr('alt','scissors');
				    break;	
                };
                console.log(userChoice);
	            console.log(pc);
                var n1=0;
                var n2=0;
                if (userChoice === "rock")
                {
                    $("#user").attr('src','https://i.ibb.co/DW37hVz/rock.png');
			    if (pc === userChoice)
                {
                    $("#popup").fadeIn(2000).fadeOut(1000);
                    $("p").text("Tied!");
                    $("#react").attr('src','https://i.ibb.co/Qmvp4x2/okayge.png');
                    n1=0;
                    n2=0;
                }
                else if (pc === "paper") {
                    $("#popup").fadeIn(2000).fadeOut(1000);
                    $("p").text("You Lost!");
                    $("#react").attr('src','https://i.ibb.co/m8h0HR6/pepetakethel.png');
                    n1=0;
                    n2=1;
                }	
                else {
                    $("#popup").fadeIn(2000).fadeOut(1000);
                    $("p").text("You Won!");
                    $("#react").attr('src','https://i.ibb.co/ykTjVdR/peepohypers.png');
                    n1=1;
                    n2=0;
                }
		        }	
                else if (userChoice === "paper") {
                    $("#user").attr('src','https://i.ibb.co/FJPpQgf/paper.png');
                    if (pc === "paper") {
                        $("#popup").fadeIn(2000).fadeOut(1000);
                        $("p").text("Tied!");
                        $("#react").attr('src','https://i.ibb.co/Qmvp4x2/okayge.png');
                        n1=0;
                        n2=0;
                    }
                    else if (pc === "scissors") {
                        $("#popup").fadeIn(2000).fadeOut(1000);
                        $("p").text("You Lost!");
                        $("#react").attr('src','https://i.ibb.co/m8h0HR6/pepetakethel.png');
                        n1=0;
                        n2=1;
                    }
                    else {
                        $("#popup").fadeIn(2000).fadeOut(1000);
                        $("p").text("You Won!");
                        $("#react").attr('src','https://i.ibb.co/ykTjVdR/peepohypers.png');
                        n1=1;
                        n2=0;
                    }	
                }
                else {
                    $("#user").attr('src','https://i.ibb.co/tbjDkkz/scissors.png');
                    if (pc === "scissors") {
                        $("#popup").fadeIn(2000).fadeOut(1000);
                        $("p").text("Tied!");
                        $("#react").attr('src','https://i.ibb.co/Qmvp4x2/okayge.png');
                        n1=0;
                        n2=0;
                    }
                    else if (pc === "rock") {
                        $("#popup").fadeIn(2000).fadeOut(1000);
                        $("p").text("You Lost!");
                        $("#react").attr('src','https://i.ibb.co/m8h0HR6/pepetakethel.png');
                        n1=0;
                        n2=1;
                    }
                    else {
                        $("#popup").fadeIn(2000).fadeOut(1000);
                        $("p").text("You Won!");
                        $("#react").attr('src','https://i.ibb.co/ykTjVdR/peepohypers.png');
                        n1=1;
                        n2=0;
                    }
                }
                var addScores = function (n2,n1){
                botscores.push(n2);
                humanscores.push(n1);}

                addScores(n2,n1);

                console.log(botscores);
                console.log(humanscores);

                console.log(botscore);
                console.log(humanscore);

		var sumScore = function(array1, array2) {
			for (var i = botscores.length -1; i<botscores.length; i++) {
				var botPoint = botscores[i];
				var humanPoint = humanscores[i];
				botscore = botscore + botPoint;
				humanscore = humanscore + humanPoint;
            }};
            sumScore();

		    console.log(botscore);
		    console.log(humanscore);

		    $("#span1").each(function(){
			$(this).html(humanscore);
            })
		    $("#span2").each(function(){
			$(this).html(botscore);
		})
        });
    });
        </script>
        <style>
            body{
                font-family: monospace;
                background-color: #ffe5b4;
            }
            #title{
                position: relative;
                top: 70px;
            }
            #panel1,#panel2{
                position: relative;
                top:120px;
                left:400px;
                display: table-cell;
                text-align: center;
                font-size: 20px;
                padding: 20px;
                width: 160px;
                height: 120px;
                background-color: #ff6f61;
                color: #ffe5b4;
                border:#ffe5b4 solid 10px;
            }
            #rock,#paper,#scissors{
                position: relative;
                top:150px;
                left:430px;
            }
            button {
                background-color: #7E4847;
                color: #ffe5b4;
                border: 2px solid #ffe5b4;
                border-radius: 7px;
                padding: 20px 25px;
                font-size: 1.4em;
                font-weight: bold;
                cursor: pointer;
                }
            button:hover{
                background-color: #ff6f61;
                color: #ffe5b4;
                border: 2px solid #7E4847;
            }
            button:active{
                background-color: #ffe5b4;
                color: #7E4847;
                border: 3px solid #ff6f61;
            }
            #popup{
                display: none;
                text-align: center;
                font-size: 24px;
                position: fixed;
                top:165px;
                width:420px;
                height: 160px;
                left:415px;
                border: 5px solid #ff6f61;
                background-color: #7E4847;
                color: #ffe5b4;
                box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
                z-index: 11;
            }
            .btn{
                position: relative;
                top:250px;
                left:165px;
                background-color: #ff6f61;
                color: #ffe5b4;
                border: #7E4847 2px solid;
            }
            .btn:hover{
                background-color: #7E4847;
                color: #ffe5b4;
                border: #ff6f61 solid 2px;
            }
            #st1,#st2{
                position: absolute;
                left: 260px;
                width: 158px;
                height: 7px;
                z-index: 1;
                background-image: url("https://media.istockphoto.com/photos/natural-wood-texture-background-picture-id1127341937?k=20&m=1127341937&s=612x612&w=0&h=K_WEgdZMQYJoUyXqP0QDyYlCh1k0FRoNbrgRkU52y0c=");
            }
            #st3,#st4{
                position: absolute;
                left:838px;
                width: 158px;
                height: 7px;
                z-index: 1;
                background-image: url("https://media.istockphoto.com/photos/natural-wood-texture-background-picture-id1127341937?k=20&m=1127341937&s=612x612&w=0&h=K_WEgdZMQYJoUyXqP0QDyYlCh1k0FRoNbrgRkU52y0c=");              
            }
            #st1,#st3{
                top:210px;
            }
            #st2,#st4{
                top:270px;
            }
            #score1{
                position: absolute;
                top:175px;
                left:220px;
                width: 120px;
                height: 120px;
                z-index: 1;
                background-image: url("https://st2.depositphotos.com/1097421/6461/i/600/depositphotos_64612339-stock-photo-blackboard-chalkboard-texture-empty-blank.jpg");
                background-size: cover;
                border:sienna solid 7px;
                border-radius: 50%;
            }
            #span1,#span2{
                position: absolute;
                top:20%;
                left:45px;
                color:white;
                font-size: 60px;
            }
            #score2{
                position: absolute;
                top:175px;
                left:890px;
                width: 120px;
                height: 120px;
                z-index: 1;
                background-image: url("https://st2.depositphotos.com/1097421/6461/i/600/depositphotos_64612339-stock-photo-blackboard-chalkboard-texture-empty-blank.jpg");
                background-size: cover;
                border:sienna solid 7px;
                border-radius: 50%;
            }
        </style>
</head>
<body><!-- Living Coral (#ff6f61), Spiced Apple (#7E4847) and Peach (#FFE5B4)-->
    <center><img src="https://fontmeme.com/permalink/211225/e2cc05de117b615da70d0e966f4a36b2.png" id="title"></center>
    <div id="st1"></div>
    <div id="st2"></div>
    <div id="score1"><span id="span1">0</span></div>
    <div id="panel1">
        <strong>Choose...</strong><br>
        <img src="https://i.ibb.co/rkny06X/rock-paper-scissors.png" alt="pls choose" height="80px" width="80px" id="user">
    </div>
    <div id="panel2">
        <b>Waiting...</b><br>
        <img src="https://i.ibb.co/RhnhhD3/bot.png" alt="bot" height="80px" width="80px" id="gen">
    </div>
    <div id="st3"></div>
    <div id="st4"></div>
    <div id="score2"><span id="span2">0</span></div>
    <button id="rock">Rock</button>
    <button id="paper">Paper</button>
    <button id="scissors">Scissors</button>
    <div id="popup"><p></p>
    <img src="https://i.ibb.co/Qmvp4x2/okayge.png" alt="tied" id="react" height="60px" width="60px">
    </div>
    <button class="btn">Reset</button>
</body>
</html>

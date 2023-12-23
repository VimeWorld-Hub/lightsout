<html>
<head>
    <title>
    LO Solver
    </title>
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<style>
	    body {
	        background-color: #1a1a1a; /* Тёмный цвет фона */
	        color: #fff; /* Цвет текста */
	        text-align: center;
	        font-family: Arial, sans-serif;
	        margin: 0;
	        padding: 0;
	    }
		#buttonContainer {
		    display: flex;
		    justify-content: center;
		    margin-bottom: 20px; /* Регулируйте отступ снизу при необходимости */
		}
        #modal {
            display: none;
            position: absolute;
            background-color: #1a1a1a;
            color: #ff0000; /* Красный цвет текста */
            padding: 10px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
            font-family: Arial, sans-serif;
            text-align: center;
            font-size: 18px;
        }
		#buttonContainer div {
		    display: flex;
		}

		#buttonContainer input {
		    margin-right: 10px;
		    background-color: #333; /* Новый цвет фона кнопок */
		    color: #fff; /* Новый цвет текста кнопок */
		    border: none;
		    padding: 10px 20px;
		    cursor: pointer;
		}

		#buttonContainer div input:last-child {
		    margin-right: 0;
		}

		#buttonContainer input:hover {
		    background-color: #555; /* Новый цвет фона кнопок при наведении */
		}

		#buttonContainer input:disabled {
		    background-color: #666; /* Новый цвет фона выключенных кнопок */
		    color: #999; /* Новый цвет текста выключенных кнопок */
		    cursor: not-allowed;
		}

	    #container {
	        display: flex;
	        flex-direction: column;
	        align-items: center;
	        justify-content: flex-start;
	        height: 100vh; /* 100% высоты окна браузера */
	        margin-top: 20px;
	    }

	    #toolbar {
	        margin-bottom: 20px;
	    }


		.cell {
		    white-space: nowrap;
		    width: 48px;
		    height: 48px;
		    float: left;
		    color: #FFF;
		    text-align: center;
		    font-weight: bold;
		    cursor: pointer;
		    position: relative;
		}

		.answer-cell {
		    width: 100%;
		    height: 100%;
		    background-color: #66FF66;
		    position: absolute;
		    top: 0;
		    left: 0;
		    display: none;
		}

	    .cell img {
	        width: 100%;
	        height: 100%;
	    }

	</style>
	<script type="text/javascript" src="jquery-3.6.3.min.js"></script>
    <script type="text/javascript">

	    function customAlert(message, color) {
	        var gameGridWidth = $("#gameGrid").width();
	        var gameGridHeight = $("#gameGrid").height();

	        // Определите положение посередине gameGrid
	        var centerX = $("#gameGrid").offset().left + gameGridWidth / 2;
	        var centerY = $("#gameGrid").offset().top + gameGridHeight + 35 + (message.split('\n').length - 1) * 10;

	        // Позиционируйте модальное окно посередине gameGrid и установите цвет текста
	        $("#modal").html(message.replace(/\n/g, "<br>")).css({
	            left: centerX - $("#modal").outerWidth() / 2,
	            top: centerY - $("#modal").outerHeight() / 2,
	            color: color
	        }).fadeIn();

	        // Закрыть модальное окно через 3 секунды
	        setTimeout(function () {
	            $("#modal").fadeOut();
	        }, 3000);
	    }

        // --- constants ---
        var imgs = new Array();     // string[], URLs of tile images
        var nums = new Array();     // string[], URLs of digit images
        var maxcolcount = 5;        // integer, maximum number of columns
        var maxrowcount = 5;        // integer, maximum number of rows
        var isCircular = false;
		var hasHighlightedSquare = false;

        var circleFlips;

        var outrangeimg = "outrange.gif";   // string, URL of empty ans cell
        var emptyimg = "empty.gif";      // string, URL of empty cell
        imgs[0] = "blue.jpg";
        imgs[1] = "red.jpg";

        // --- global variables ---
        var colcount;   // integer, number of columns
        var rowcount;   // integer, number of rows
        var imgcount;   // integer, number of states of a tile
        var cells;      // integer[row][col], current states of tiles
        var steps;      // integer, current steps of operation
        var playing;    // boolean, if playing
        var autogen;    // boolean, if playing with an auto-generated problem

        // --- initialization ---
        //function onLoad(){}
        init();
        function init()
        {
            for (var val = 0; val < imgs.length; val++)
                nums[val] = "number" + val + ".gif";
            var col;
            var row;
            cells = new Array();

            for (col = 0; col < maxcolcount; col++)
            {
                cells[col] = new Array();
                for (row = 0; row < maxrowcount; row++)
                    cells[col][row] = 0;
            }
            //  playing = false;
        }

        // --- event handlers ---
        function newSettings()
        {
            isCircular = false;
            colcount = 5;
            rowcount = 5;
            imgcount = 2;
            for (var col = 0; col < maxcolcount; col++)
            {
                for (var row = 0; row < maxrowcount; row++)
                {
                    setcellimage(col, row, emptyimg);
                    setanscellimage(col, row, outrangeimg);
                }
            }
            newGame();
        }

        function newGame()
        {
        	hasHighlightedSquare = false;
    		$("#allowEditB").attr("disabled", true);
            for (var col = 0; col < colcount; col++) {
				for (var row = 0; row < rowcount; row++) {
					setcell(col, row, 1);
		            setanscellimage(col, row, "empty.gif");
                }
            }

            playing = false;
            autogen = false;
            steps = 0;
        }

        function allowEdit()
        {
        	hasHighlightedSquare = false;
            for (var col = 0; col < colcount; col++) {
				for (var row = 0; row < rowcount; row++) {
		            setanscellimage(col, row, "empty.gif");
                }
            }
    		$("#allowEditB").attr("disabled", true);
        }

        function edit()
        {
            if (!playing)
            {
                for (var col = 0; col < colcount; col++)
                {
                    for (var row = 0; row < rowcount; row++)
                    {
                        setcell(col, row, 0);
                    }
                }
            }
            playing = false;
            autogen = false;
        }

        function play()
        {
            playing = true;
        }

        function ansoperate(col, row)
        {
            operate(col, row);
            solve();
        }

        function operate(col, row)
        {
            if (col >= colcount || row >= rowcount)
                return;

			if (hasHighlightedSquare)
				return customAlert("Решение уже найдено!\nИспользуйте команду редактирования\nдля смены состояния ламп.", "#f2cc6d");
			
            flip(col, row);
            if (playing)
            {
                if (col > 0)
                    flip(col - 1, row);
                if (row > 0)
                    flip(col, row - 1);
                if (col < colcount - 1)
                    flip(col + 1, row);
                if (row < rowcount - 1)
                    flip(col, row + 1);

                steps++;
                if (autogen && isCleared())
                {
                    var row;
                    var col;
                    for (row = 0; row < maxrowcount; row++)
                    {
                        for (col = 0; col < maxcolcount; col++)
                        {
                            try
                            {
                                $("#ansDiv_" + col + row).hide();
                            }
                            catch (err) { }
                        }
                    }
                    autogen = false;
                }
            }
        }
        // --- operation methods ---
        function setcell(col, row, val)
        {
            cells[col][row] = val;
            setcellimage(col, row, imgs[val]);
        }

        function setcellimage(col, row, imgsrc)
        {
            $("#img_" + col + row).attr('src', imgsrc);
        }

        function setanscellimage(col, row, imgsrc)
        {

            if (imgsrc == emptyimg || imgsrc == outrangeimg)
            {
                try
                {
                    $("#ansDiv_" + col + row).hide();
                }
                catch (err) { }
            }
            else if (imgsrc == "number1.gif")
            {
                $("#ansDiv_" + col + row).fadeTo(0, 0.4).show();
        		hasHighlightedSquare = true; // Устанавливаем флаг, если есть подсвеченный квадратик
            }
            else if (imgsrc == "number0.gif")
            {
                try
                {
                    $("#ansDiv_" + col + row).hide();
                }
                catch (err) { }
            }
        }

        function cellname(col, row)
        {
            return "cell" + col + "_" + row;
        }

        function flip(col, row)
        {
            setcell(col, row, (cells[col][row] + 1) % imgcount);
        }

        function isCleared()
        {
            var sample = cells[0][0];
            for (var col = 0; col < colcount; col++)
                for (var row = 0; row < rowcount; row++)
                if (cells[col][row] != sample) return false;
            return true;
        }

        // --- finite field algebra solver
        function modulate(x)
        {
            // returns z such that 0 <= z < imgcount and x == z (mod imgcount)
            if (x >= 0) return x % imgcount;
            x = (-x) % imgcount;
            if (x == 0) return 0;
            return imgcount - x;
        }
        function gcd(x, y)
        { // call when: x >= 0 and y >= 0
            if (y == 0) return x;
            if (x == y) return x;
            if (x > y) x = x % y; // x < y
            while (x > 0)
            {
                y = y % x; // y < x
                if (y == 0) return x;
                x = x % y; // x < y
            }
            return y;
        }
        function invert(value)
        {
            if (value <= 1) return value;
            var seed = gcd(value, imgcount);
            if (seed != 1) return 0;
            var a = 1, b = 0, x = value;    // invar: a * value + b * imgcount == x
            var c = 0, d = 1, y = imgcount; // invar: c * value + d * imgcount == y
            while (x > 1)
            {
                var tmp = Math.floor(y / x);
                y -= x * tmp;
                c -= a * tmp;
                d -= b * tmp;
                tmp = a; a = c; c = tmp;
                tmp = b; b = d; d = tmp;
                tmp = x; x = y; y = tmp;
            }
            return a;
        }

        var mat;    // integer[i][j]
        var cols;   // integer[]
        var m;      // count of rows of the matrix
        var n;      // count of columns of the matrix
        var np;     // count of columns of the enlarged matrix
        var r;      // minimum rank of the matrix
        var maxr;   // maximum rank of the matrix

        function a(i, j) { return mat[i][cols[j]]; }
        function setmat(i, j, val) { mat[i][cols[j]] = modulate(val); }


        function solve()
        {
            playing = false;
            var col;
            var row;
            for (var goal = 0; goal < imgcount; goal++)
            {
                if (solveProblem(goal))
                {
                	$("#allowEditB").removeAttr("disabled");
            		customAlert("Решение найдено!\nТеперь в игре нажмите <b>один раз</b> в любом порядке\nна подсвеченные лампы.", "#f2cc6d");
                    var anscols = new Array();
                    var j;
                    for (j = 0; j < n; j++) anscols[cols[j]] = j;
                    for (col = 0; col < colcount; col++)
                        for (row = 0; row < rowcount; row++)
                    {
                        var value;
                        j = anscols[row * colcount + col];
                        if (j < r) value = a(j, n); else value = 0;
                        setanscellimage(col, row, nums[value]);
                    }
                    return;
                }
            }
            // (aborted or) no solution
            for (var col = 0; col < colcount; col++)
                for (var row = 0; row < rowcount; row++)
                setanscellimage(col, row, outrangeimg);

            customAlert("Нет решений!", "#ff0000");
        }

        function showSolution(sol)
        {
            var tmp = "";

            for (col = 0; col < colcount; col++)
            {
                for (row = 0; row < rowcount; row++)
                {
                    if ((col == 0 || row == 0) || (col == 3 || row == 0) ||
                        (col == 1 || row == 1) || (col == 2 || row == 1) ||
                        (col == 1 || row == 2) || (col == 2 || row == 2) ||
                        (col == 0 || row == 3) || (col == 3 || row == 3))
                    {
                        setanscellimage(col, row, outrangeimg);
                    }
                }
            }
            for (i = 0; i < sol.length; i++)
            {
                if (sol[i])
                {
                    setanscellimage(circleFlips[i][1], circleFlips[i][0], nums[1]);
                }
                else
                {
                    setanscellimage(circleFlips[i][1], circleFlips[i][0], nums[0]);
                }
            }
        }

        function nextSol(sol)
        {
            var count = 0;

            for (i = 0; i < sol.length; i++)
            {
                if (sol[i])
                    count++;
            }

            //count backwards until we get to 10 and make all ending 1's 0's
            zeros = false;
            ones = 0;
            index = sol.length - 1;

            while (!(zeros && sol[index]) && index >= 0)
            {
                if (sol[index])
                {
                    ones++;
                    sol[index] = false;
                }
                else
                {
                    zeros = true;
                }

                index--;
            }

            if (count == ones)
                return false;

            sol[index] = false;
            index++;

            for (j = index; j <= index + ones; j++)
            {
                sol[j] = true;
            }

            return (sol);
        }

        function initMatrix()
        {
            maxr = Math.min(m, n);
            mat = new Array();
            for (var col = 0; col < colcount; col++)
                for (var row = 0; row < rowcount; row++)
            {
                var i = row * colcount + col;
                var line = new Array();
                mat[i] = line;
                for (var j = 0; j < n; j++) line[j] = 0;
                line[i] = 1;
                if (col > 0) line[i - 1] = 1;
                if (row > 0) line[i - colcount] = 1;
                if (col < colcount - 1) line[i + 1] = 1;
                if (row < rowcount - 1) line[i + colcount] = 1;
            }
            cols = new Array();
            for (var j = 0; j < np; j++) cols[j] = j;
        }

        function solveProblem(goal)
        {
            var size = colcount * rowcount;
            m = size;
            n = size;
            np = n + 1;
            initMatrix();
            for (var col = 0; col < colcount; col++)
                for (var row = 0; row < rowcount; row++)
                mat[row * colcount + col][n] = modulate(goal - cells[col][row]);
            return sweep();
        }

        function sweep()
        {
            for (r = 0; r < maxr; r++)
            {
                if (!sweepStep()) return false; // failed in founding a solution
                if (r == maxr) break;
            }
            return true; // successfully found a solution
        }

        function sweepStep()
        {
            var i;
            var j;
            var finished = true;
            for (j = r; j < n; j++)
            {
                for (i = r; i < m; i++)
                {
                    var aij = a(i, j);
                    if (aij != 0) finished = false;
                    var inv = invert(aij);
                    if (inv != 0)
                    {
                        for (var jj = r; jj < np; jj++)
                            setmat(i, jj, a(i, jj) * inv);
                        doBasicSweep(i, j);
                        return true;
                    }
                }
            }
            if (finished)
            { // we have: 0x = b (every matrix element is 0)
                maxr = r;   // rank(A) == maxr
                for (j = n; j < np; j++)
                    for (i = r; i < m; i++)
                    if (a(i, j) != 0) return false; // no solution since b != 0
                return true;    // 0x = 0 has solutions including x = 0
            }
            return false;   // failed in finding a solution
        }

        function swap(array, x, y)
        {
            var tmp = array[x];
            array[x] = array[y];
            array[y] = tmp;
        }

        function doBasicSweep(pivoti, pivotj)
        {
            if (r != pivoti) swap(mat, r, pivoti);
            if (r != pivotj) swap(cols, r, pivotj);
            for (var i = 0; i < m; i++)
            {
                if (i != r)
                {
                    var air = a(i, r);
                    if (air != 0)
                        for (var j = r; j < np; j++)
                        setmat(i, j, a(i, j) - a(r, j) * air);
                }
            }
        }
    </script>
</head>

<body>
    <div id="container">
		<div id="buttonContainer">
		    <div>
		        <input type="button" id="newGameB" value="Сбросить" onClick="newGame()">
		        <input type="button" id="solveB" value="Найти решение" onClick="solve()">
		        <input type="button" id="allowEditB" value="Редактировать" onClick="allowEdit()" disabled>
		    </div>
		</div>

        <div id="gameGrid">
<div>
    <div class="cell" id="div_00" onmousedown='operate(0,0);'>
        <img id='img_00' src='empty.gif'></img>
        <div id='ansDiv_00' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_01" onmousedown='operate(0,1);'>
        <img id='img_01' src='empty.gif'></img>
        <div id='ansDiv_01' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_02" onmousedown='operate(0,2);'>
        <img id='img_02' src='empty.gif'></img>
        <div id='ansDiv_02' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_03" onmousedown='operate(0,3);'>
        <img id='img_03' src='empty.gif'></img>
        <div id='ansDiv_03' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_04" onmousedown='operate(0,4);'>
        <img id='img_04' src='empty.gif'></img>
        <div id='ansDiv_04' class='answer-cell'>&nbsp;</div>
    </div>
</div>
<div>
    <div class="cell" id="div_10" onmousedown='operate(1,0);'>
        <img id='img_10' src='empty.gif'></img>
        <div id='ansDiv_10' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_11" onmousedown='operate(1,1);'>
        <img id='img_11' src='empty.gif'></img>
        <div id='ansDiv_11' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_12" onmousedown='operate(1,2);'>
        <img id='img_12' src='empty.gif'></img>
        <div id='ansDiv_12' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_13" onmousedown='operate(1,3);'>
        <img id='img_13' src='empty.gif'></img>
        <div id='ansDiv_13' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_14" onmousedown='operate(1,4);'>
        <img id='img_14' src='empty.gif'></img>
        <div id='ansDiv_14' class='answer-cell'>&nbsp;</div>
    </div>
</div>
<div>
    <div class="cell" id="div_20" onmousedown='operate(2,0);'>
        <img id='img_20' src='empty.gif'></img>
        <div id='ansDiv_20' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_21" onmousedown='operate(2,1);'>
        <img id='img_21' src='empty.gif'></img>
        <div id='ansDiv_21' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_22" onmousedown='operate(2,2);'>
        <img id='img_22' src='empty.gif'></img>
        <div id='ansDiv_22' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_23" onmousedown='operate(2,3);'>
        <img id='img_23' src='empty.gif'></img>
        <div id='ansDiv_23' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_24" onmousedown='operate(2,4);'>
        <img id='img_24' src='empty.gif'></img>
        <div id='ansDiv_24' class='answer-cell'>&nbsp;</div>
    </div>
</div>
<div>
    <div class="cell" id="div_30" onmousedown='operate(3,0);'>
        <img id='img_30' src='empty.gif'></img>
        <div id='ansDiv_30' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_31" onmousedown='operate(3,1);'>
        <img id='img_31' src='empty.gif'></img>
        <div id='ansDiv_31' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_32" onmousedown='operate(3,2);'>
        <img id='img_32' src='empty.gif'></img>
        <div id='ansDiv_32' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_33" onmousedown='operate(3,3);'>
        <img id='img_33' src='empty.gif'></img>
        <div id='ansDiv_33' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_34" onmousedown='operate(3,4);'>
        <img id='img_34' src='empty.gif'></img>
        <div id='ansDiv_34' class='answer-cell'>&nbsp;</div>
    </div>
</div>
<div>
    <div class="cell" id="div_40" onmousedown='operate(4,0);'>
        <img id='img_40' src='empty.gif'></img>
        <div id='ansDiv_40' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_41" onmousedown='operate(4,1);'>
        <img id='img_41' src='empty.gif'></img>
        <div id='ansDiv_41' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_42" onmousedown='operate(4,2);'>
        <img id='img_42' src='empty.gif'></img>
        <div id='ansDiv_42' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_43" onmousedown='operate(4,3);'>
        <img id='img_43' src='empty.gif'></img>
        <div id='ansDiv_43' class='answer-cell'>&nbsp;</div>
    </div>
    <div class="cell" id="div_44" onmousedown='operate(4,4);'>
        <img id='img_44' src='empty.gif'></img>
        <div id='ansDiv_44' class='answer-cell'>&nbsp;</div>
    </div>
</div>
</div>
<div id="modal"></div>
<script type="text/javascript">
    newSettings();
</script>
</BODY>
</HTML>


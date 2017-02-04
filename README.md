<!DOCTYPE html>
<html>
<head>
	<link rel="shortcut icon" type="image/x-icon" href="favicon.ico" />
	<meta charset="utf-8">
	<title>Text Adventure!</title>
	<style>

	body {
		margin: 15px 15px 15px 15px;
	}

	::-webkit-scrollbar { 
    	display: none; 
	}

	div.container {
	    width: 100%;
	    border: 6px solid gray; 
	    background-color: #ccc;
	    border-color: rgb(100,100,100);
	    border-top-left-radius: 11px;
		border-top-right-radius: 36px;
		border-bottom-right-radius: 11px;
		border-bottom-left-radius: 36px;
	}

	p {
		font-family: Optima;
		font-size: 17px;
		font-style: normal;
		font-variant: normal;
		line-height: 20px;
	}

	header{
		border-top-left-radius: 5px;
		border-top-right-radius: 30px;
		font-family: Rockwell;
		text-shadow: 1px 3px 0px #AAA, .2px .6px 0px #AAA, .4px 1.2px 0px #AAA, .6px 1.8px 0px #AAA, .8px 2.4px 0px #AAA, -1px 4px 3px #000, 0px 4px 3px #000, 1px 4px 3px #000;
		font-size: 20px;
		letter-spacing: 6px;
		word-spacing: 2px;
		font-weight: bold;
	    padding: 1em;
	    color: white;
	    background-color: rgb(130,130,130);
	    clear: left;
	    text-align: center;
		background-image: linear-gradient(90deg, transparent 50%, rgba(120,120,120,.9) 30%);
		background-size: 20px 45px;
	}

	header:hover {
		color: #F7F6CF;
		letter-spacing: 6.5px;
		word-spacing: 4.2px;
		text-shadow: .2px .6px 0px #AAA, .4px 1.2px 0px #AAA, .6px 1.8px 0px #AAA, .8px 2.4px 0px #AAA, 1px 3px 0px #AAA, 1.2px 3.6px 0px #AAA, 1.4px 4.2px 0px #AAA, -1px 6px 3px #000, 0px 6px 3px #000, 1px 6px 3px #000, -1px 4px 3px #000, 0px 4px 3px #000, 1px 4px 3px #000, 2px 4px 3px #000, 2px 6px 3px #000;
		background-color: rgb(120,120,120);
	    clear: left;
	    text-align: center;
		background-image: linear-gradient(90deg, transparent 50%, rgba(110,110,110,.9) 30%);
		background-size: 25px 50px;	
	}

	a {
		color: inherit;
		text-decoration: inherit;
	}

	a:hover{
		color: #EFEE9A;
		text-shadow: .2px .6px 0px #AAA, .4px 1.2px 0px #AAA, .6px 1.8px 0px #AAA, .8px 2.4px 0px #AAA, 1px 3px 0px #AAA, 1.2px 3.6px 0px #AAA, 1.4px 4.2px 0px #AAA, 1.6px 4.8px 0px #AAA, -1px 6px 3px #000, 0px 6px 3px #000, 1px 6px 3px #000, -1px 4px 3px #000, 0px 4px 3px #000, 1px 4px 3px #000, -1px 7px 3px #000, 0px 7px 3px #000, 1px 7px 3px #000, 2px 4px 3px #000, 2px 6px 3px #000, 2px 7px 3px #000, 3px 4px 3px #000, 3px 6px 3px #000, 3px 7px 3px #000;
	}

	footer{
		font-family: Optima;
		font-weight: bold;
		padding: 1em;
	    color: white;
	    background-color: rgb(180,180,180);
	    clear: left;
	    text-align: center;
		background-image: linear-gradient(90deg, transparent 50%, rgba(170,170,170,.9) 30%);
		background-size: 20px 45px;
		border-bottom-right-radius: 5px;
		border-bottom-left-radius: 30px;
	}

	footer:hover{
	    background-color: rgb(170,170,170);
	    clear: left;
	    text-align: center;
		background-image: linear-gradient(90deg, transparent 50%, rgba(160,160,160,.9) 30%);
		background-size: 25px 50px;
		letter-spacing: .3px;
		word-spacing: .3px;
	}

	nav {
	    float: left;
	    max-width: 160px;
	    margin: 0;
	    padding: 1em;
	}

	nav ul , section ul{
	    list-style-type: none;
	    padding: 0;
	}
	   
	nav ul a {
	    text-decoration: none;
	}

	article {
		background-color: #eee;
	    margin-left: 170px;
	    padding: 1em;
	    overflow: hidden;
	}

	button {
		color: #444;
	    background:none!important;
	    border:none; 
	    padding:0!important;
	    font-size: 12.5pt; 
	    cursor: pointer;
	    font-weight: bold;
	    outline: none;
	}

	button:hover {
		color: #FFFA05;
	}

	</style>
</head>
<body>
	<script type="text/javascript">
		var p = [document.getElementById('p1'),document.getElementById('p2'),document.getElementById('p3'),document.getElementById('p4'),document.getElementById('p5')];
		function changeParagraph(p1, p2, p3, p4, p5){
			document.getElementById('p1').innerHTML=p1;
			document.getElementById('p1').style.display='block';
			if (p2 == null) {
				document.getElementById('p2').style.display='none';
				document.getElementById('p3').style.display='none';
				document.getElementById('p4').style.display='none';
				document.getElementById('p5').style.display='none';
			}
			else {
				document.getElementById('p2').innerHTML=p2;
				document.getElementById('p2').style.display='block';
				if (p3 == null) {
					document.getElementById('p3').style.display='none';
					document.getElementById('p4').style.display='none';
					document.getElementById('p5').style.display='none';
				}
				else {
					document.getElementById('p3').innerHTML=p3;
					document.getElementById('p3').style.display='block';
					if (p4 == null) {
						document.getElementById('p4').style.display='none';
						document.getElementById('p5').style.display='none';
					}
					else {
						document.getElementById('p4').innerHTML=p4;
						document.getElementById('p4').style.display='block';
						if (p5 == null) {
							document.getElementById('p5').style.display='none';
						}
						else {
							document.getElementById('p5').innerHTML=p5;
							document.getElementById('p5').style.display='block';
						}
					}
				}
			}
		}
		function changeButtons(o1,o2,o3,a1,a2,a3){ //o1 is text of first button, a1 is the id of the button o should click instead.
			document.getElementById('o1').innerHTML=o1;
			document.getElementById('o1').style.display='block';
			if (o2 == null){
				document.getElementById('o2').style.display='null';
				document.getElementById('o3').style.display='null';
			}
			else {
				document.getElementById('o2').innerHTML=o2;
				document.getElementById('o2').style.display='block';
				if (o3 == null) {
					document.getElementById('o3').style.display='null';
				}
				else {
					document.getElementById('o3').innerHTML=o3;
					document.getElementById('o3').style.display='block';
				}
			}
		}
	</script>
	<div class="container">
		<header>
			<h1><a href="CYOA.html">TEXT ADVENTURE</a></h1>
		</header>
		<nav>
		  <ul>
		    <li><button id="home" onclick="changeParagraph('Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum tincidunt nulla vel ligula interdum, quis imperdiet quam efficitur. In malesuada scelerisque sodales. Fusce sit amet commodo sem. Sed aliquam lacinia nisl, in elementum diam posuere quis. Vestibulum molestie arcu lacinia vulputate dignissim. Aenean feugiat vitae lectus eu ultrices. In ultricies enim dui, ut laoreet neque faucibus et. Vestibulum luctus, nisi nec sodales hendrerit, dolor leo finibus felis, ac dignissim est leo sed sem. Integer odio nunc, interdum eu tellus at, rutrum pulvinar ipsum. Pellentesque elementum, diam nec porttitor scelerisque, ex enim ultrices urna, et dignissim libero nunc ac est. Morbi laoreet lorem ante, ac commodo enim ultricies et. Morbi fermentum blandit mauris non luctus. Sed ipsum ligula, rhoncus ut odio ac, fermentum faucibus justo. Vestibulum laoreet dui ante, vehicula sodales nulla maximus a. In commodo, eros sed luctus condimentum, massa magna interdum nulla, sit amet imperdiet nibh eros quis odio. Suspendisse finibus, turpis sed bibendum volutpat, enim ante varius odio, eget interdum lectus risus nec libero.','Nam sit amet odio in enim euismod convallis. Nulla laoreet justo lacus, vitae aliquam erat mollis in. Mauris lacinia interdum dui, a posuere tellus consectetur nec. Morbi blandit pretium nisi, porttitor viverra metus cursus sit amet. Proin maximus augue metus, vel varius massa pharetra pretium. Curabitur lobortis tincidunt elementum. Phasellus auctor mattis quam, nec efficitur ipsum rhoncus non. Etiam ut lorem congue, maximus nisi ac, fringilla augue. Suspendisse porttitor dui vel diam aliquet, at auctor elit lacinia. Morbi maximus ligula id fringilla placerat.','Proin porta, nulla vel porttitor consequat, mi lacus vehicula justo, eget malesuada lectus lacus at metus. Quisque sit amet orci in leo tempus maximus. Curabitur ut sem quis sapien bibendum luctus. Nunc nibh eros, pulvinar ullamcorper ex sed, pharetra imperdiet felis. Curabitur vel vehicula est. Donec vulputate felis vel fringilla maximus. Nulla eget blandit risus. Morbi luctus tortor iaculis, ultrices purus ac, semper metus. Vivamus blandit, arcu gravida vehicula viverra, erat eros volutpat nulla, ac consequat urna purus sit amet diam. Duis maximus quam diam, id gravida lectus cursus et. Vestibulum lacinia ante ut metus maximus, nec convallis nibh pretium. Aenean dictum a augue non volutpat. Curabitur vehicula, arcu eu malesuada tempor, urna tellus aliquam quam, ut pulvinar sapien nibh et odio.','In bibendum dui vitae porta elementum. Nunc mauris justo, tincidunt ac enim vel, eleifend pulvinar erat. Curabitur lobortis feugiat nisi ac convallis. Ut fringilla tristique odio non mollis. Ut sit amet viverra velit, eget consequat nunc. Nunc eget dignissim sem, vel vulputate augue. In non turpis libero. Quisque orci ante, volutpat eu accumsan in, egestas non ligula. Donec dictum mollis dui. Aenean placerat eros lacus, sed cursus neque accumsan sit amet.','Duis nisl nisi, varius vel commodo vel, ultrices finibus risus. Aliquam ultrices feugiat est quis rhoncus. Integer eget mattis ipsum, et malesuada erat. Vestibulum vel lorem et lorem pellentesque tristique sit amet at mauris. Nullam sollicitudin nulla in nulla pharetra, ut venenatis leo tincidunt. Donec tincidunt id risus a pretium. Maecenas et nisl vel tortor pellentesque mollis. Nam in ante enim. Integer iaculis convallis urna vitae mattis. Nunc lectus purus, venenatis ut ante a, faucibus pharetra velit. In in rutrum urna. Duis libero dui, ornare et eleifend eget, volutpat nec leo.');
		    	changeButtons('Continue','','');
		    	document.getElementById('o1').onclick = function() { document.getElementById('b1').click(); }">Home Page</button></li>
		    <li><button id='b1' onclick="changeParagraph('Ex nam diam graece vituperatoribus. Ut vide adhuc maiestatis vis, et pro ferri prodesset philosophia. In eam numquam equidem, ex vel malis latine apeirian. Te sale accusam ius, nam modus tincidunt moderatius in. In epicuri repudiandae cum, dico percipit reprehendunt cum id, vix ea minim ornatus consulatu. Ad vide graece eripuit duo.','Eu has vide mediocrem, eum facer intellegat interesset ut. Et quo omnes temporibus, eam molestie maluisset ei. Ius nullam similique te. Te pro altera abhorreant, duo in pertinacia constituto efficiantur, elitr accusata cu nec. Graece dissentiet has ad, vulputate quaerendum disputationi in vim, clita tritani sed ut.','Ex nam d&#34;iam graece vituperatoribus. Ut vide adhuc maiestatis vis, et pro ferri prodesset philosophia. In eam numquam equidem, ex vel malis latine apeirian. Te sale accusam ius, nam modus tincidunt moderatius in. In epicuri repudiandae cum, dico percipit reprehendunt cum id, vix ea minim ornatus consulatu. Ad vide graece eripuit duo.','Eu has vide mediocrem, eum facer intellegat interesset ut. Et quo omnes temporibus, eam molestie maluisset ei. Ius nullam similique te. Te pro altera abhorreant, duo in pertinacia constituto efficiantur, elitr accusata cu nec. Graece dissentiet has ad, vulputate quaerendum disputationi in vim, clita tritani sed ut.','Qui ludus constituam honestatis ut, an vis alii omnium, id tale inciderint mel. Graece commune vix et, vocent deleniti apeirian qui an. Cu vis saepe hendrerit, id illud reque persius vel. Ad has omnes mollis, mei eu sumo quot graeco, in vide ullamcorper eos. Ea vim sanctus debitis ullamcorper. Ornatus intellegam sadipscing has ne.');
				changeButtons('Don\'t click me!','Click me','');
				document.getElementById('o1').onclick = function() { document.getElementById('b1').click(); };
				document.getElementById('o2').onclick = function() { document.getElementById('b2').click(); }">Page 1</button></li>
		    <li><button id='b2' onclick="changeParagraph('Sed habeo torquatos conceptam et, et his dolor malorum. Clita consetetur te sed, pro ipsum aeque dictas at, impetus integre definitionem vel et. Pri at errem periculis reformidans, eam amet assum in, eum eruditi sanctus id. Vis suas molestie incorrupte ex. Te duo consulatu urbanitas, pri mucius ceteros lobortis et.','Ea est eros augue, has no ridens appetere instructior. Pri te ornatus alienum suavitate, et vis iusto timeam ancillae, has eu animal copiosae efficiantur. Ei augue tacimates vel. Id elitr delectus vis. Vel nisl stet honestatis in. His ad scaevola volutpat conceptam, an noster dictas neglegentur sit, suas posse choro qui ei.','Cu eos albucius percipit, ei his legimus aliquando. Doming veritus corrumpit ei eam, ut dolorum elaboraret duo. Lorem commodo vel no. In qui quis natum epicuri. Pro case volumus dignissim ex, summo denique ea pri. Rebum assum his id. Vidisse numquam qualisque ne nec, at essent recteque nec.','Ex nam diam graece vituperatoribus. Ut vide adhuc maiestatis vis, et pro ferri prodesset philosophia. In eam numquam equidem, ex vel malis latine apeirian. Te sale accusam ius, nam modus tincidunt moderatius in. In epicuri repudiandae cum, dico percipit reprehendunt cum id, vix ea minim ornatus consulatu. Ad vide graece eripuit duo.','Eu has vide mediocrem, eum facer intellegat interesset ut. Et quo omnes temporibus, eam molestie maluisset ei. Ius nullam similique te. Te pro altera abhorreant, duo in pertinacia constituto efficiantur, elitr accusata cu nec. Graece dissentiet has ad, vulputate quaerendum disputationi in vim, clita tritani sed ut.');
				changeButtons('Click me!','Don\'t click me','');
				document.getElementById('o1').onclick = function() { document.getElementById('b1').click(); };
				document.getElementById('o2').onclick = function() { document.getElementById('b2').click(); }">Page 2</button></li>
		  </ul>
		</nav>
		<article>
			<blockquote>
				<p id="p1">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum tincidunt nulla vel ligula interdum, quis imperdiet quam efficitur. In malesuada scelerisque sodales. Fusce sit amet commodo sem. Sed aliquam lacinia nisl, in elementum diam posuere quis. Vestibulum molestie arcu lacinia vulputate dignissim. Aenean feugiat vitae lectus eu ultrices. In ultricies enim dui, ut laoreet neque faucibus et. Vestibulum luctus, nisi nec sodales hendrerit, dolor leo finibus felis, ac dignissim est leo sed sem. Integer odio nunc, interdum eu tellus at, rutrum pulvinar ipsum. Pellentesque elementum, diam nec porttitor scelerisque, ex enim ultrices urna, et dignissim libero nunc ac est. Morbi laoreet lorem ante, ac commodo enim ultricies et. Morbi fermentum blandit mauris non luctus. Sed ipsum ligula, rhoncus ut odio ac, fermentum faucibus justo. Vestibulum laoreet dui ante, vehicula sodales nulla maximus a. In commodo, eros sed luctus condimentum, massa magna interdum nulla, sit amet imperdiet nibh eros quis odio. Suspendisse finibus, turpis sed bibendum volutpat, enim ante varius odio, eget interdum lectus risus nec libero.</p>
				<p id="p2">Nam sit amet odio in enim euismod convallis. Nulla laoreet justo lacus, vitae aliquam erat mollis in. Mauris lacinia interdum dui, a posuere tellus consectetur nec. Morbi blandit pretium nisi, porttitor viverra metus cursus sit amet. Proin maximus augue metus, vel varius massa pharetra pretium. Curabitur lobortis tincidunt elementum. Phasellus auctor mattis quam, nec efficitur ipsum rhoncus non. Etiam ut lorem congue, maximus nisi ac, fringilla augue. Suspendisse porttitor dui vel diam aliquet, at auctor elit lacinia.g Morbi maximus ligula id fringilla placerat.</p>
				<p id="p3">Proin porta, nulla vel porttitor consequat, mi lacus vehicula justo, eget malesuada lectus lacus at metus. Quisque sit amet orci in leo tempus maximus. Curabitur ut sem quis sapien bibendum luctus. Nunc nibh eros, pulvinar ullamcorper ex sed, pharetra imperdiet felis. Curabitur vel vehicula est. Donec vulputate felis vel fringilla maximus. Nulla eget blandit risus. Morbi luctus tortor iaculis, ultrices purus ac, semper metus. Vivamus blandit, arcu gravida vehicula viverra, erat eros volutpat nulla, ac consequat urna purus sit amet diam. Duis maximus quam diam, id gravida lectus cursus et. Vestibulum lacinia ante ut metus maximus, nec convallis nibh pretium. Aenean dictum a augue non volutpat. Curabitur vehicula, arcu eu malesuada tempor, urna tellus aliquam quam, ut pulvinar sapien nibh et odio.</p>
				<p id="p4">In bibendum dui vitae porta elementum. Nunc mauris justo, tincidunt ac enim vel, eleifend pulvinar erat. Curabitur lobortis feugiat nisi ac convallis. Ut fringilla tristique odio non mollis. Ut sit amet viverra velit, eget consequat nunc. Nunc eget dignissim sem, vel vulputate augue. In non turpis libero. Quisque orci ante, volutpat eu accumsan in, egestas non ligula. Donec dictum mollis dui. Aenean placerat eros lacus, sed cursus neque accumsan sit amet.</p>
				<p id="p5">Duis nisl nisi, varius vel commodo vel, ultrices finibus risus. Aliquam ultrices feugiat est quis rhoncus. Integer eget mattis ipsum, et malesuada erat. Vestibulum vel lorem et lorem pellentesque tristique sit amet at mauris. Nullam sollicitudin nulla in nulla pharetra, ut venenatis leo tincidunt. Donec tincidunt id risus a pretium. Maecenas et nisl vel tortor pellentesque mollis. Nam in ante enim. Integer iaculis convallis urna vitae mattis. Nunc lectus purus, venenatis ut ante a, faucibus pharetra velit. In in rutrum urna. Duis libero dui, ornare et eleifend eget, volutpat nec leo.</p>
			</blockquote>
			<section>
				<blockquote><br>
					<ul>
						<li><button id="o1" onclick="document.getElementById('b1').click()">Continue</button></li>
			  			<li><button id="o2" onclick="document.getElementById('b2').click()" style="display: none"></button></li>
			  			<li><button id="o3" onclick="document.getElementById('b2').click()" style="display: none"></button></li>
					</ul>
				</blockquote>
			</section>
		</article>
		<footer>
			Copyright &copy; Prytherch.com
		</footer>
	</div>
</body>
</html>

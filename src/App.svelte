<script>

var URL = ""
var ytbcheck = ""

function getId(url) {
    const regExp = /^.*(youtu.be\/|v\/|u\/\w\/|embed\/|watch\?v=|&v=)([^#&?]*).*/;
    const match = url.match(regExp);

    return (match && match[2].length === 11)
      ? match[2]
      : null;
}

function setvideo() {
	URL = document.getElementById("URL").value;
	ytbcheck = URL.includes("https://www.youtube.com/watch?v")
	if (URL == 0) {
		document.getElementById("error").innerHTML = "merci de remplir le champ textuel"
		setTimeout(function(){ 
				document.getElementById("error").innerHTML = "";
			}, 5000);
	} else {
		if (ytbcheck == true){
			URL = getId(URL)
			URL = "https://www.youtube.com/embed/"+URL
		} else {
			document.getElementById("error").innerHTML = "merci d'entrer une URL valide"
			setTimeout(function(){ 
				document.getElementById("error").innerHTML = "";
				}, 5000);
		}
	}
}

function dlvideo() {
	console.log('download')
}

</script>

<style>


	body {
	padding: 25px;
	background-color: white;
	color: black;
	font-size: 25px;
	}

	.container { 
	height: 200px;
	position: relative;
	}

	.center {
	margin: 0;
	position: absolute;
	top: 50%;
	left: 50%;
	-ms-transform: translate(-50%, -50%);
	transform: translate(-50%, -50%);
	}

	h2,p {
		text-align: center;
	}

	svg {
		display: block;
		margin-left: auto;
		margin-right: auto;
		width: 300px;
		height: 200px;
		overflow: visible;
	}

	.filler {
		border: 1px solid #ddd;
	}

	button {
		height: 4rem;
		width: 8rem;
		background-color: white;
		border-color: #ddd;
		color: black;
		font-size: 1.25rem;
		background-image: linear-gradient(45deg, grey 50%, transparent 50%);
		background-position: 100%;
		background-size: 400%;
		transition: background 300ms ease-in-out;
	}
	button:hover {
		background-position: 0;
		color: black;
	}
	

</style>

<body>



	<h2>SVG video Embeder</h2>

	<svg class="filler">
		
		<foreignObject width="300" height="200">
			<iframe title="embed" xmlns="http://www.w3.org/1999/xhtml"
			width="300" height="200"
			src={URL}
			frameborder="0"></iframe>
	</foreignObject>
	</svg>



	<p></p>
	<div class="container">
		<p id="error" style="color:red"></p>
		<div class="center">
			<input id="URL" placeholder="Youtube video URL" type="text">
			<button  on:click={setvideo}>Valider</button>
			<button  on:click={dlvideo}>Download</button>
			
		</div>
	</div>

	
</body>


<script>

var URL = ""

function setvideo() {
	URL = document.getElementById("URL").value;.0
	URL = URL.substring(URL.indexOf('=') + 1);
	URL = "https://www.youtube.com/embed/"+URL
}

</script>

<style>
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
	<div class="center">
		<input id="URL" placeholder="Youtube video URL" type="text">
		<button  on:click={setvideo}>Valider</button>
		
	</div>
</div>



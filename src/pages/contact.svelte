<style>
form {
	margin:10% auto 0 auto;
	padding:30px;
	width:400px;
	height:auto;
	overflow:hidden;
	background:white;
	border-radius:10px;
}

form label {
	font-size:14px;
	color:darkgray;
	cursor:pointer;
}

form label,
form input {
	float:left;
	clear:both;
}

form input {
	margin:15px 0;
	padding:15px 10px;
	width:100%;
	outline:none;
	border:1px solid #bbb;
	border-radius:20px;
	display:inline-block;
	-webkit-box-sizing:border-box;
	   -moz-box-sizing:border-box;
	        box-sizing:border-box;
    -webkit-transition:0.2s ease all;
	   -moz-transition:0.2s ease all;
	    -ms-transition:0.2s ease all;
	     -o-transition:0.2s ease all;
	        transition:0.2s ease all;
}

form input[type=text]:focus {
	border-color:cornflowerblue;
}

button {
	padding:15px 50px;
	width: 100%;
	background:#1abc9c;
	border:none;
	color:white;
	cursor:pointer;
	display:inline-block;
	float:right;
	clear:right;
	-webkit-transition:0.2s ease all;
	   -moz-transition:0.2s ease all;
	    -ms-transition:0.2s ease all;
	     -o-transition:0.2s ease all;
	        transition:0.2s ease all;
}

button:hover {
	opacity:0.8;
}

button:active {
	opacity:0.4;
}
</style>

<form name="contact" method="POST" data-netlify="true">
	  <label>Your Name: <input type="text" name="name" /></label>   
	  <label>Your Email: <input type="email" name="email" /></label>
	  <input type="hidden" name="form-name" value="contact" />
	  <button type="submit">Send</button>
</form>
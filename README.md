XHTML
<!DOCTYPE html>
<html lang="en" dir="ltr">
   <head>
      <meta charset="utf-8">
      <title>Random Password Generator</title>
      <link rel="stylesheet" href="style.css">
     
   </head>
   <body>
      <div class="container">
         <div class="text">
            Random Password Generator
         </div>
         <div class="input-data">
            <div class="display">
               <input type="text">
               <span class="far fa-copy" onclick="copy()"></span>
               <span class="fas fa-copy" onclick="copy()"></span>
            </div>
            <button>Generate Password</button>
         </div>
      </div>
      <script>
         const display = document.querySelector("input"),
         button = document.querySelector("button"),
         copyBtn = document.querySelector("span.far"),
         copyActive = document.querySelector("span.fas");
         let chars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#$%^&*()_+~`|}{[]:;?><,./-=";
         button.onclick = ()=>{
           let i,
           randomPassword = "";
           copyBtn.style.display = "block";
           copyActive.style.display = "none";
           for (i = 0; i < 16; i++) {
             randomPassword = randomPassword + chars.charAt(
               Math.floor(Math.random() * chars.length)
             );
           }
           display.value = randomPassword;
         }
         function copy(){
           copyBtn.style.display = "none";
           copyActive.style.display = "block";
           display.select();
           document.execCommand("copy");
         }
      </script>
   </body>
       
            *{
	margin: 0;
	padding: 0;
	box-sizing: border-box;
	font-family: 'Poppins', sans-serif;
  }
  html,body{
	display: grid;
	height: 100%;
	place-items: center;
	background: #000;
	text-align: center;
  }
  .container{
	width: 450px;
	background: #111;
	border: 1px solid #444;
	border-radius: 5px;
	padding: 20px 25px;
  }
  .container .text{
	color: #ccc;
	font-weight: 600;
	font-size: 26px;
	line-height: 35px;
  }
  .container .input-data{
	margin: 20px 5px 15px 5px;
  }
  .input-data .display{
	height: 45px;
	width: 100%;
	display: flex;
	position: relative;
  }
  .input-data .display input{
	height: 100%;
	width: 100%;
	outline: none;
	color: #eee;
	border: 1px solid #333;
	background: #222;
	padding: 10px;
	font-size: 17px;
	pointer-events: none;
	user-select: none;
  }
  .input-data .display span{
	position: absolute;
	right: 15px;
	top: 50%;
	transform: translateY(-50%);
	font-size: 25px;
	color: grey;
	z-index: 999;
	display: none;
	cursor: pointer;
  }
  .input-data button{
	display: block;
	height: 45px;
	width: 100%;
	margin-top: 15px;
	border: 1px solid #444;
	outline: none;
	background: #1b1b1b;
	color: #999;
	font-size: 17px;
	font-weight: 500;
	text-transform: uppercase;
	cursor: pointer;
	transition: all 0.3s ease;
  }
  .input-data button:hover{
	background: #222;
  }
            
</html>

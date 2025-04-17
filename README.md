#HTML+JAVASCRIPT:
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>QR Code Generator Using HTML CSS And Javascript</title>
    <link rel="stylesheet" href="CSS.css" />
  </head>
  <body>
    <div class="container">
      <p>Enter your text or URL</p>
      <input type="text" placeholder="Text or URL" id="qrText" />
      <div id="imgBox">
        <img src="" id="qrImage" />
      </div>
      <button onclick="generateQR()">Generate QR Code</button>
    </div>

    <script>
      let imgBox = document.getElementById("imgBox");
      let qrImage = document.getElementById("qrImage");
      let qrText = document.getElementById("qrText");

      function generateQR() {
        if (qrText.value.trim().length > 0) {
          qrImage.src =
            "https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=" +
            encodeURIComponent(qrText.value);
          imgBox.classList.add("show-img");
        } else {
          alert("Please enter some text or a URL!");
        }
      }
    </script>
  </body>
</html>


CSS:
*{
margin:0;
padding: 0;
font-family:'Poppins',sans-serif;
box-sizing: border-box;
}
body
{
    background: #262a2f;
}
.container{
    width: 400px;
    padding: 25px 35px;
    position: absolute;
    top:50%;
    left:50%;
    transform: translate(-50%,-50%);
    background: #fff;
    border-radius: 10px;
}
.container p{
    font-weight: 600;
    font-size: 15px;
    margin-bottom: 8px;

}
.container input{
    width: 100%;
    height: 50px;
    border: 1px solid #494eea;
    outline: 0;
    padding: 10px;
    margin: 10px 0 20px;
    border-radius: 5px;
}
.container button{
    width: 100%;
    height: 50px;
    background: #494eea;
    color:#fff;
    border:0;
    border-radius:5px;
    box-shadow: 0 10px 10px rgba(0,0,0,0.1);
    cursor:pointer;
    margin: 20px 0;
    font-weight: 500;
}
#imgBox{
    width: 200px;
    border-radius: 5px;
    max-height: 0;
    overflow: hidden;
    transition: max-height 1s;
}
#imgBox img{
    width: 100%;
    padding: 10px;
}
#imgBox.show-img
{
    max-height: 300px;
    margin: 10px auto;
    border: 1px solid #d1d1d1;
}


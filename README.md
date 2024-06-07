# Q-scanner-project
it is based on Html, CSS, and Js.
--- html 
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Q-Scaneer</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <div class="conatiner">

        <h1>Scan Qr Codes</h1>
        <div class="section">

            <div id="my-qr-reading">

            </div>
        </div>
    </div>
    <script src="https://unpkg.com/html5-qrcode">
    </script>
    <script src="script.js"></script>
</body>

</html>
---

--- css 
body {
    display: flex;
    justify-content: center;
    margin: 0;
    padding: 0;
    height: 100vh;
    box-sizing: border-box;
    text-align: center;
    background: rgba(5, 243, 227, 0.66);
   
   
}

.container {

    width: 100%;
    max-width: 500px;
    margin: 5px;
}

.container h1 {

    color: #ffffff;

}

.section {

    background-color: #ffffff;
    padding: 50px 30px;
    border: 1.5px solid #b2b2b2;
    border-radius: 0.25em;
    box-shadow: 0 20px 25px rgba(0, 0, 0, 0.25);
}

#my-qr-reader {

    padding: 20px !important;
    border: 1.5px solid #b2b2b2  !important;
    border-radius: 8px;

}

 
#my-qr-reader img[alt="Info icon"] {
    display: none;
}
 
 
#my-qr-reader img[alt="Camera based scan"] {
    width: 100px !important;
    height: 100px !important;
}

button {

    padding:10px 20px;
    border: 1px solid #b2b2b2;
    outline: none;
    border-radius: 0.25em;
    color:white;
    font-size: 15px;
    cursor: pointer;
    margin-top: 15px;
    margin-bottom: 10px;
    background-color: #008000AD;
    transition: 0.3s background-color;
}
button:hover {
    background-color: #008000;
}
 
#html5-qrcode-anchor-scan-type-change {
    text-decoration: none !important;
    color: #1d9bf0;
}
 
video {
    width: 100% !important;
    border: 1px solid #b2b2b2 !important;
    border-radius: 0.25em;
}
---

--- js 
function domReady(fn){
    if(
        document.readyState === "complete" || 
        document.readyState === "interactive"
    )
    {

        setTimeout(fn, 1000);
    }
    else {

        document.addEventListener("DOMContentLoaded", fn)
    }
} 

domReady(function (){
    
    function onScanSuccess(decodeText, decodeResult) {
        
        alert("you Qr is: " + decodeText, decodeResult);
    }

    let htmlscanner = new Html5QrcodeScanner (
        "my-qr-reading",
        {
            fps:10, qrbos:250 
        }
    );
    htmlscanner.render(onScanSuccess);
});

// fps: Sets the frames per second for video capture.

// qrbos: Sets the QR code detection boundary size.
---


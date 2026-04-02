# N.M. MANASIA – Art Payment & Book System

## 🌐 Live Platform
👉 https://Pr791610.github.io/art-payment/

---

## 📚 Overview

Professional integrated system combining:

- 🎨 Artworks
- 📄 Certificates (7 pages + QR)
- 📚 Books (MK / IT – 500 pages)
- 🔳 QR Verification System
- 💳 Secure Payment Integration

---

## 🎨 Artwork Galleries

---

## 📄 Certificates System

Each artwork includes:

- ✔ 7-page professional certificate  
- ✔ Signed authenticity proof  
- ✔ Official seal  
- ✔ QR verification page  

---

## 🔳 QR Code System

### 📚 Full Book Access
Scan to view full 500-page documentation  
👉 (ADD LINK)

### 🎨 Artwork Details
Scan to access artwork archive  
👉 (ADD LINK)

### 🌐 Collection Archive
Scan to view full collection  
👉 (ADD LINK)

### 💳 Secure Payment
Scan for direct payment system  
👉 https://Pr791610.github.io/art-payment/

---

## 🎟 Collector Benefits

- Access to full archive  
- Exclusive QR content  
- Discount coupons for future artworks  
- Verified ownership system  

---

## 🧠 Concept

This system represents:

**Art + Theory + Documentation + Digital Verification**

Creating a complete:

👉 **Art Documentation & Payment System**

---

## 🏷 Edition

**N.M. MANASIA**  
**N.M. EDITION**

---

## ⚙️ Repository Structure
</html>mailto:manasievnikola79@gmail.com 
</html>© 2025 N.M. MANASIA – All Rights Reserved


<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>N.M. MANASIA – Order System</title>
</head>

<body style="font-family:Arial; background:black; color:gold; text-align:center; padding:20px;">

<h1>N.M. MANASIA</h1>
<h2>Art Order & Activation System</h2>

<p>Complete the form and proceed with payment</p>

<hr>

<h3>📋 Order Form</h3>

<form action="mailto:YOUR_EMAIL@gmail.com" method="post" enctype="text/plain">

<input type="text" name="Name" placeholder="Your Name" required style="padding:10px; width:80%;"><br><br>

<input type="email" name="Email" placeholder="Your Email" required style="padding:10px; width:80%;"><br><br>

<input type="text" name="Artwork" placeholder="Artwork / Book Name" required style="padding:10px; width:80%;"><br><br>

<input type="number" name="Amount" placeholder="Amount (€)" required style="padding:10px; width:80%;"><br><br>

<textarea name="Message" placeholder="Additional Message" style="padding:10px; width:80%; height:100px;"></textarea><br><br>

<button type="submit" style="padding:15px; font-size:18px; background:gold; color:black;">
Submit Order
</button>

</form>

<hr>

<h3>💳 Payment Information</h3>

<p><b>Name:</b> Nikolce Manasiev</p>
<p><b>IBAN:</b> MK07210501678618611</p>
<p><b>SWIFT:</b> TUTNMK22</p>
<p><b>Bank:</b> NLB Banka Skopje</p>

<p><b>Scan QR or copy details to complete payment</b></p>

<hr>

<h3>🔐 Activation</h3>

<p>After payment, send confirmation via email.</p>
<p>Access to artwork, book, and certificate will be provided by the author.</p>

</body>
</html>mailto:manasievnikolce5@gmail.com
<!DOCTYPE html>
<html lang="mk">
<head>
<meta charset="UTF-8">
<title>Hub Payment</title>

<script data-main="payment-js" src="https://gateway.bankart.si/js/integrated/payment.1.3.min.js"></script>

<style>
body {font-family:Arial;background:#1e1e2f;color:#fff;padding:20px;}
.box {max-width:420px;margin:auto;background:#fff;color:#000;padding:20px;border-radius:10px;}
input {width:100%;padding:10px;margin:8px 0;border-radius:6px;border:1px solid #ccc;}
#number_div,#cvv_div {height:45px;border:1px solid #ccc;border-radius:6px;padding:5px;}
button {width:100%;padding:12px;background:#00c853;color:#fff;border:none;border-radius:6px;}
.error {color:red;}
</style>

</head>
<body>

<div class="box">
<h2>Плаќање</h2>

<form id="payment_form" method="POST" action="process.php" onsubmit="pay(); return false;">

<input type="hidden" id="transaction_token" name="transaction_token">

<input id="card_holder" placeholder="Име и презиме">
<input id="exp_month" placeholder="MM">
<input id="exp_year" placeholder="YYYY">
<input id="email" placeholder="Email">

<div id="number_div"></div>
<div id="cvv_div"></div>

<div id="errors" class="error"></div>

<button type="submit">Плати</button>

</form>
</div>

<script>
var payment = new PaymentJs();

payment.init('PUBLIC_KEY_HERE','number_div','cvv_div',function(p){

    p.setNumberStyle({'border-color':'green'});
    p.setCvvStyle({'border-color':'green'});

    p.enableAutofill();
    p.onAutofill(function(d){
        document.getElementById('card_holder').value = d.card_holder;
        document.getElementById('exp_month').value = d.month;
        document.getElementById('exp_year').value = d.year;
    });

});

function showErrors(errs){
    let h='';
    errs.forEach(e=>h+=`<div>${e.attribute}: ${e.message}</div>`);
    document.getElementById('errors').innerHTML=h;
}

function pay(){

    let data={
        card_holder:card_holder.value,
        month:exp_month.value,
        year:exp_year.value,
        email:email.value
    };

    payment.tokenize(data,
        function(token){
            transaction_token.value=token;
            payment_form.submit();
        },
        function(errors){
            showErrors(errors);
        }
    );
}
</script>

</body>
</html>
var payment = new PaymentJs();

// INIT + RISK SCRIPT
payment.init('public-integration-key', 'number_div', 'cvv_div', function(p){

    // Risk script (пример Kount)
    payment.initRiskScript({type:'kount'}, function(){
        console.log("Risk script активен");
    });

    // STYLE
    p.setNumberStyle({
        'border-color':'#00c853',
        'font-size':'16px'
    });

    p.setCvvStyle({
        'border-color':'#00c853',
        'font-size':'16px'
    });

    // EVENTS
    p.numberOn('input', function(data){
        console.log("Card:", data);
    });

    p.numberOn('focus', function(){
        console.log("Focus на број");
    });

    // AUTOFILL
    p.enableAutofill();
    p.onAutofill(function(data){
        document.getElementById('card_holder').value = data.card_holder;
        document.getElementById('exp_month').value = data.month;
        document.getElementById('exp_year').value = data.year;
    });

});

// ERROR HANDLER
function showErrors(errors){
    let html = '';
    errors.forEach(e=>{
        html += `<div>${e.attribute}: ${e.message}</div>`;
    });
    document.getElementById('errors').innerHTML = html;
}

// SUBMIT TOKENIZE
function interceptSubmit(){

    let data = {
        card_holder: document.getElementById('card_holder').value,
        month: document.getElementById('exp_month').value,
        year: document.getElementById('exp_year').value,
        email: document.getElementById('email').value
    };

    payment.tokenize(
        data,
        function(token, cardData){

            console.log("TOKEN:", token);
            console.log("CARD:", cardData);

            document.getElementById('transaction_token').value = token;

            document.getElementById('payment_form').submit();
        },
        function(errors){
            showErrors(errors);
        }
    );
}

// CVV REFRESH (ако користиш зачувана картичка)
function refreshCVV(){
    payment.refreshCvv(
        function(){
            document.getElementById('payment_form').submit();
        },
        function(errors){
            showErrors(errors);
        }
    );
}
</script>

</body>
</html>

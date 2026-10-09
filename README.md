<!doctype html>
<html lang="es">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>KURAMA SUSHI</title>

<style>
:root{
  --r:#7d2630;
  --r2:#a43b42;
  --g:#c79b55;
  --p:#fff9ed;
  --ink:#34231d;
  --green:#355c45
}

*{box-sizing:border-box}

html{scroll-behavior:smooth}

body{
  margin:0;
  color:var(--ink);
  font-family:Georgia,serif;
  background:linear-gradient(135deg,#291813,#5b3024,#241510);
  min-height:100vh
}

header{
  position:sticky;
  top:0;
  z-index:20;
  background:#2d1913f7;
  border-bottom:2px solid var(--g);
  box-shadow:0 4px 18px #0008
}

.head{
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding:10px 14px;
  max-width:1100px;
  margin:auto
}

.logo{
  color:#fff;
  font-weight:bold;
  font-size:22px;
  letter-spacing:3px
}

.logo small{
  display:block;
  text-align:center;
  color:var(--g);
  font-size:10px;
  letter-spacing:5px
}

.cart{
  border:0;
  border-radius:28px;
  background:var(--r2);
  color:#fff;
  padding:11px 15px;
  font-weight:bold;
  font-size:15px
}

.count{
  background:#fff;
  color:var(--r);
  border-radius:50%;
  padding:2px 7px;
  margin-left:4px
}

.nav{
  overflow:auto;
  white-space:nowrap;
  padding:7px 10px 10px;
  text-align:center
}

.nav a{
  display:inline-block;
  color:#fff;
  text-decoration:none;
  border:1px solid #c79b5560;
  border-radius:22px;
  padding:9px 15px;
  margin:0 3px
}

.nav a:hover{
  background:var(--g);
  color:#241510
}

.paper{
  width:min(96%,1000px);
  margin:18px auto 35px;
  background:
    radial-gradient(#8b694115 1px,transparent 1px),
    var(--p);
  background-size:8px 8px;
  padding:22px 14px 55px;
  box-shadow:0 20px 60px #0009
}

.brand{
  text-align:center
}

.brand .fox{
  font-size:52px
}

.brand h1{
  margin:3px 0;
  color:var(--r);
  font-size:36px;
  letter-spacing:5px
}

.brand h2{
  margin:0;
  color:var(--g);
  font-size:15px;
  letter-spacing:7px
}

.orn{
  color:var(--g);
  margin:8px
}

section{
  scroll-margin-top:125px;
  margin-top:40px
}

.title{
  text-align:center;
  color:var(--r);
  font-size:30px;
  margin:0 0 6px
}

.sub{
  text-align:center;
  color:#76584c;
  margin:0 0 18px
}

.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(230px,1fr));
  gap:14px
}

.card{
  background:#fffdf7;
  border:1px solid #d6bd91;
  border-radius:13px;
  padding:16px;
  box-shadow:0 5px 15px #573b2412
}

.card h3{
  margin:0 0 7px;
  color:var(--r);
  font-size:21px
}

.desc{
  color:#6d574c;
  min-height:42px
}

.price{
  color:var(--r);
  font-size:21px;
  font-weight:bold;
  margin:11px 0
}

.actions{
  display:flex;
  gap:8px;
  align-items:center
}

.qty{
  display:flex;
  border:1px solid #c9ad7e;
  border-radius:8px;
  overflow:hidden
}

.qty button{
  border:0;
  background:#f2e3ca;
  width:32px;
  height:35px;
  font-size:18px
}

.qty span{
  width:30px;
  text-align:center;
  padding-top:8px;
  font-weight:bold
}

.add{
  border:0;
  border-radius:8px;
  padding:10px 13px;
  color:#fff;
  background:var(--r);
  font-weight:bold;
  cursor:pointer;
  flex:1
}

.modalbg{
  display:none;
  position:fixed;
  inset:0;
  background:#000b;
  z-index:100;
  padding:14px;
  align-items:center;
  justify-content:center
}

.modalbg.show{
  display:flex
}

.modal{
  width:min(560px,100%);
  max-height:92vh;
  overflow:auto;
  background:var(--p);
  border-radius:15px;
  padding:20px;
  box-shadow:0 20px 70px #000
}

.modal h2{
  color:var(--r);
  margin:0 35px 15px 0
}

.close{
  float:right;
  border:0;
  background:none;
  font-size:28

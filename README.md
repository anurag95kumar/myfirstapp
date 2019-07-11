# Menu Click Animation
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
<style>
.container {
  display: inline-block;
  cursor: pointer;
}

.bar1, .bar2, .bar3 {
  width: 35px;
  height: 5px;
  background-color: #333;
  margin: 6px 0;
  transition: 0.4s;
}
.change:active::after{
  transition: scale(0, 0);
}
.menu {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 0 0 0 100%;
  transform: scale(0, 0);
  transform-origin: top right;
  background: green;
  z-index: -1;
  transition: transform 2s ease;
  display: block;
  animation-name: move;
}



.change .bar1 {
  -webkit-transform: rotate(-45deg) translate(-9px, 6px);
  transform: rotate(-45deg) translate(-9px, 6px);
}

.change .bar2 {opacity: 0;}

.change .bar3 {
  -webkit-transform: rotate(45deg) translate(-8px, -8px);
  transform: rotate(45deg) translate(-8px, -8px);
}
.row {
    width: 100%;
}
.menu{
  opacity: 0;
}
.menu_content{
  opacity: 1;
  color: #fff;
  transform: scale(1.5,1.5);
}
.menu_content ul.nav_menu li {
  color: #fff;
}
ul.nav_menu a {
    text-decoration: none;
}
ul.nav_menu li {
    list-style-type: none;
    text-align: center;
    font-size: 25pt;
    line-height: 2.2;
}

</style>
</head>
<body>

<p>Click on the Menu Icon to transform it to "X":</p>
<div class="container" onclick="myFunction(this)">
  <div class="bar1"></div>
  <div class="bar2"></div>
  <div class="bar3"></div>
</div>
<div class="row menu">
  <ul class="nav_menu">
    <a href="#"><li>Home</li></a>
    <a href="#"><li>Page1</li></a>
    <a href="#"><li>Page2</li></a>
    <a href="#"><li>Page3</li></a>
    <a href="#"><li>Contact Us</li></a>
  </ul>
</div>

<script>
function myFunction(x) {
  x.classList.toggle("change");
}
$(document).ready(function(){
  $(".container").click(function(){
    $(".container").toggleClass("animate");
    $(".menu").toggleClass("menu_content");
  });
});

</script>

</body>
</html>
    

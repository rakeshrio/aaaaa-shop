<template>
  <div class="col-md-12 m-0 p-0">
      <nav>
    <input type="checkbox" id="check" />
    <label for="check" class="checkbtn">
      <i class="fa fa-bars"></i>
    </label>
    <label class="logo">
      <img src="" alt="screen-content"/></label>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">Rent</a></li>
      <li><a href="#">Finance</a></li>
      <li class="mid"><a href="#">Shop</a></li>
      <li>
        <a href="#"><img src="" alt="screen-content" /><span>+91-XXXXXXXXXX</span></a>
      </li>
      <li>
        <a href="#"><img src="" alt="screen-content"><span>+91-XXXXXXXXXX</span></a>
      </li>
      <li>
        <a href="#"><img src="" alt="screen-content"/><span>contact@ontrack.in</span></a>
      </li>
    </ul>
  </nav>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.mid {
  padding-right: 100px;
}
nav {
  background: #4e44d8;
  height: 97px;
  width: 100%;
}
label.logo {
  height: 28px;
  line-height: 80px;
  padding: 0 50px;
  font-weight: bold;
}
nav ul {
  float: right;
  margin-right: 20px;
}
nav ul li {
  display: inline-block;
  line-height: 90px;
  margin: 0 5px;
}
.logo > span {
  font-size: 16px;
  line-height: 20px;
  font-weight: lighter;
}
ul li img {
  padding-right: 5px;
}
nav ul li a {
  color: white;
  font-size: 17px;
  padding: 7px 13px;
  border-radius: 3px;
}
a.active,
a:hover {
  background: #1b9bff;
  transition: 0.5s;
}
.checkbtn {
  font-size: 30px;
  color: white;
  float: right;
  line-height: 80px;
  margin-right: 40px;
  cursor: pointer;
  display: none;
}
#check {
  display: none;
}
@media (max-width: 952px) {
  label.logo {
    font-size: 30px;
    padding-left: 50px;
  }
  nav ul li a {
    font-size: 16px;
  }
}
@media (max-width: 858px) {
  .checkbtn {
    display: block;
  }
  .mid {
    padding-right: 0px;
  }
  ul {
    position: fixed;
    width: 100%;
    height: 100vh;
    background: #4e44d8;
    top: 80px;
    left: -100%;
    text-align: center;
    transition: all 0.5s;
  }
  nav ul li {
    display: block;
    margin: 50px 0;
    line-height: 30px;
  }
  nav ul li a {
    font-size: 20px;
  }
  a:hover,
  a.active {
    background: none;
    color: #0082e6;
  }
  #check:checked ~ ul {
    left: 0;
  }
}
section {
  background-size: cover;
  height: calc(100vh - 80px);
}
</style>
<template>
    <div class="col-md-12 m-0 pt-5 p-0 " style="background:white; color:#7d7d7d; font-family:gilroy; z-index:99999" >
        <div class="col-md-8  m-auto m-0 p-0 lap">
            <div class="col-md-12 m-0 p-0 row justify-content-between ">
                <div class=" m-0 p-0">
                    <div class="col-md-12 mb-4 text-left m-0 p-0">
                        <img src="https://on-track.in/wp-content/uploads/2018/10/logo.svg" alt="">
                    </div>
                    <div class="text-left">
                    <p class="mb-0">We are here to make your </p>
                    <p class="mb-0">everyday travel pocket-friendly </p>
                    <p>and hassle-free!</p>
                    <div class="row">

                    </div>
                    </div>
                </div>
                <div class=" m-0 p-0">
                    <div class="col-md-12 col-12 text-left m-0 p-0">
                        <h3 class="mb-3" style="font-family:gilroyf; color:black" >About </h3>
                        <a href="https://on-track.in/about/"><p class="mb-3">Our Story</p></a>
                        <!-- <p class="mb-3">FAQ</p> -->
                        <a href="https://on-track.in/blog-2/"><p class="mb-1">Blog</p></a>
                    </div>
                </div>
                <div class="  m-0 p-0">
                    <div class="col-md-12 col-12 text-left m-0 p-0">
                        <h3 class="mb-3" style="font-family:gilroyf;color:black ">Company</h3>
                        <p class="mb-3" @click="$router.push('/termsandcondition')" style="cursor:pointer">Terms & Conditions</p>
                        <a href="https://on-track.in/privacy-policy2/"><p class="mb-3">Privacy Policy</p></a>
                        <a href="mailto:info@on-track.in"><p class="mb-3">Partner With Us</p></a>
                        <!-- <p class="mb-1">Copyright Guidelines</p> -->
                    </div>
                </div>
                <div class=" ml-5 text-center">
                    <div class="col-md-12 col-12 text-left m-0 p-0">
                        <h3 class="mb-3" style="font-family:gilroyf; color:black">Contact Us</h3>
                        <div class="row mb-2 col-md-12 m-0 p-0">
                            <div class="col-md-2 m-0 p-0">
                                <i class="fa fa-map-marker"></i>
                            </div>
                            <div class="col-md-10 m-0 p-0">
                               <p> #441 Indiranagar, Bengaluru</p>
                            </div>
                        </div>
                        <div class="row mb-1 col-md-12 m-0 p-0">
                            <div class="col-md-2 m-0 p-0">
                                <i class="fa fa-envelope" aria-hidden="true"></i>
                            </div>
                            <div class="col-md-10 m-0 p-0">
                              <a href="mailto:info@on-track.in"><p>tech@on-track.in</p></a>
                            
                            </div>
                        </div>
                        <div class="row col-md-12 m-0 p-0">
                            <div class="col-md-2 m-0 p-0">
                                <i class="fa fa-phone" aria-hidden="true"></i>
                            </div>
                            <div class="col-md-10 m-0 p-0">
                               <a href="tel:+91-9148518401"><p>+91 91485 18401</p></a>
                             
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <hr class="mb-0">
        <div class="col-md-12 row py-4  py-0" style="justify-content:space-between" >
            <div class="">
                <p class="mb-0">Copyright © 2021 Ontrack. Designed By <strong style="font-family:gilroyf; color:black">Ontrack</strong></p> 
            </div>
            <div class=""  @click="top()">
                <p class="mb-0"><i class="fa fa-angle-up font" style="font-size:28px; " ></i></p>
            </div>
        </div>
        </div>
        <div class="col-12 m-0 p-0 mob">
            <div class="col-12 row m-0 p-0">
              <div class="col-12 mb-3">
                  <div class="col-12 m-0 p-0">
                    <div class="col-md-12 mb-4 text-center m-0 p-0">
                        <img src="https://on-track.in/wp-content/uploads/2018/10/logo.svg" alt="">
                    </div>
                    <div class="text-center" >
                    <p class="mb-0">We are here to make your everyday travel</p>
                    <!-- <p class="mb-0">  pocket-friendly </p> -->
                    <p>and hassle-free!</p>
                    <div class="row">

                    </div>
                    </div>
                  </div>
              </div>
              <div class="col-6 m-0 p-0">
                    <div class="col-md-12 col-12 ml-4 text-left m-0 p-0">
                        <h3 class="mb-3" style="font-family:gilroyf; color:black" >Company</h3>
                        <p class="mb-3">About Us</p>
                        <p class="mb-3">FAQ</p>
                        <p class="mb-3">Contact Us</p>
                        <p class="mb-1">Blog</p>
                    </div>
                </div>
                <div class="col-6  m-0 p-0">
                    <div class="col-md-12 col-12 ml-3 text-left m-0 p-0">
                        <h3 class="mb-3" style="font-family:gilroyf;color:black ">About </h3>
                        <p class="mb-3">Terms & Conditions</p>
                        <p class="mb-3">Privacy Policy</p>
                        <p class="mb-3">Disclaimer Policy</p>
                        <p class="mb-1">Copyright Guidelines</p>
                    </div>
                </div>
                <div class="col-6 mt-5 m-0 p-0">
                  <div class="text-left ml-2 col-12 mb-4" >
                    <h3 class="mb-3" style="font-family:gilroyf;color:black ">Contact </h3>
                    <a href="mailto:info@on-track.in"> <p class="mb-3" >info@on-track.in</p></a>
                    <a href="tel:+91-9148518401">  <p class="mb-3" >+91 91485 18401</p></a>
                  </div>
                </div>
                <div class="col-6 mt-5 m-0 p-0">
                  <div class=" text-left ml-2 col-12 mb-4" >
                    <h3 class="cal mb-3" style="font-family:gilroyf;color:black ">Follow Us</h3>
                        <a href="https://www.facebook.com/ontrackBikes/">  <img src="https://cdn1.iconfinder.com/data/icons/social-media-2285/512/Colored_Facebook3_svg-128.png" alt="" width="auto" height="30px" class="pr-2"></a>
                        <a  href="https://www.linkedin.com/company/ontrack-technologies-private-limited/">  <img src="https://cdn2.iconfinder.com/data/icons/social-media-2285/512/1_Linkedin_unofficial_colored_svg-128.png" alt="" width="auto" height="30px" class="pr-2"></a>
                        <a href="https://www.instagram.com/ontrackbikes/">  <img src="https://cdn2.iconfinder.com/data/icons/social-media-2285/512/1_Instagram_colored_svg_1-128.png" alt=" "  width="auto" height="30px" class="pr-2"></a>
                  </div>        
                </div>

            </div>
            <hr class="mb-0">
            <div class="col-md-12 row py-4 py-0 m-0 p-0" >
            <div class="col-8 text-left   mr-0">
                <p class="mb-0 ml-2">Copyright © 2021 <strong style="font-family:gilroyf; font-size:15px; color:black">Ontrack</strong></p> 
            </div>
            <div class="col-4" @click="top()">
                <p class="mb-0"><i class="fa fa-angle-up font" style="font-size:28px; " ></i></p>
            </div>
        </div>
        </div>
        
    </div>
</template>

<script>
export default {
methods:{
  top(){
    window.document.body.scrollTop = 0;
  window.document.documentElement.scrollTop = 0;
  }
}
}
</script>

<style scoped>
/* @font-face {
  font-family:rubik ;
  src: url(../assets/font/rubik/Rubik-VariableFont_wght.ttf);
}
@font-face {
  font-family:gilroyf ;
  src: url(../assets/font/rubik/Rubik-VariableFont_wght.ttf);
  font-weight: 600;
}
@font-face {
 font-family:roboto ;
  src: url(../assets/font/roboto/Roboto-Black.ttf); 
}  */
@font-face {
  font-family: Gilroy;
  src: url(../assets/font/Gilroy-Light.otf);
}
@font-face {
  font-family: Gilroyf;
  src: url(../assets/font/Gilroy-ExtraBold.otf);
}
.mob{
  display: none  !important;
}
.lap{
    display: block !important;
}
p{
    font-size:14px
}
a{
  color:grey !important
}
.font{
    color:black;
    height:36px;
    width:36px;
    border-radius: 50%;
   /* position: fixed; */
    cursor: pointer; 
    background:#B3AEE1;
}
.font:hover{
    background:#4e44d8;
    color:white;
    border-radius:50px;
    transform: translateY(-50%);
    box-shadow: 0 4px 6px rgb(50 50 93 / 11%), 0 1px 3px rgb(0 0 0 / 8%);
    transition: 1s;
    /* transform: translateY(-5px); */
}
@media screen and (max-width: 600px) {
  .mob{
    display: block !important;

  }
  .lap{
    display: none !important;
  }
}
</style>
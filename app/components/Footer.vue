<template>
  <footer class="footer">
    <div class="footer-container">
      <div class="footer-box">
        <i class="fas fa-map-marker-alt icon"></i>
        <h4>Address</h4>
        <p>A108 Adam Street<br>New York, NY 535022</p>
      </div>
      <div class="footer-box">
        <i class="fas fa-phone icon"></i>
        <h4>Contact</h4>
        <p><strong>Phone:</strong> +1 5589 55488 55<br>
           <strong>Email:</strong> info@example.com</p>
      </div>
      <div class="footer-box">
        <i class="fas fa-clock icon"></i>
        <h4>Opening Hours</h4>
        <p><strong>Mon-Sat:</strong> 11AM - 23PM<br>
           <strong>Sunday:</strong> Closed</p>
      </div>
      <div class="footer-box-social">
        <h3>Follow Us</h3>
        <div class="social-icons">
          <a href="#"><i class="fa-brands fa-x-twitter"></i></a>
          <a href="#"><i class="fa-brands fa-facebook"></i></a>
          <a href="#"><i class="fab fa-instagram"></i></a>
          <a href="#"><i class="fa-brands fa-linkedin"></i></a>
        </div>
      </div>
    </div>
    <hr class="footer-divider" />
    <div class="footer-bottom">
      <p>© Copyright <strong>Yummy</strong>. All Rights Reserved</p>
      <p class="second-p">Designed by <span class="red">BootstrapMade</span> Distributed by <span class="red">ThemeWagon</span></p>
    </div>
    <a href="#" class="back-to-top"><i class="fa-solid fa-arrow-up"></i></a>
  </footer>
</template>

<script>
export default {
  name: 'FooterComponent'
}
</script>

<style scoped>
.footer {
  background: #1f1f24;
  color: white;
  padding: 40px 20px;
  position: relative;
  font-family: "Roboto", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
}

.footer-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 2px;
  height: 80px;
  margin: 10px 60px;
}

.footer-box {
  flex: 1 1 220px;
  margin-bottom: auto;
  margin-left: 0px;
  gap: 40px;
  margin-top: -20px;
  
}
.footer-box i{
  margin-top: 18px;
  color: #ce1212;
  font-size: 24px;
}

.footer-box h4 {
  margin-bottom: 30px;
  font-size: 16px;
  font-weight: 700;
  margin-left: 40px; 
  margin-top: -25px;
}

.footer-box p {
  margin-left: 40px;
  line-height: 1.4;
  margin-bottom: 20px;
  margin-top: -15px;
  
}

.icon {
  color: #ce1212;
  font-size: 20px;
}
.footer-box-social{
  margin-right: 80px;
  margin-top: -1px;
}
.footer-box-social h3{
  font-family: "Roboto", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  font-size: 16px;
  font-weight: bold;
  
}
.social-icons {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-top: 10px;
}

.social-icons a {
  width: 40px;
  height: 40px;
  background-color: transparent;
  border: 1px solid gray;
  border-radius: 50%;
  color: white;
  display: flex; 
  justify-content: center; 
  align-items: center;
  text-decoration: none;
  transition: background-color 0.3s ease;
}
.social-icons a i{
  font-size: 15px;
  margin-bottom: 5px;
  

}

.social-icons a:hover {
  color: white;
  border-color: #ce1212;
}

.footer-divider {
  border-color: rgba(255, 255, 255, 0.1);
  margin: 30px 0;
}

.footer-bottom {
  text-align: center;
  font-size: 14px;
  line-height: 25px;
}

.footer-bottom .red {
  color: #ce1212;
}
.second-p{
  font-size: 13px;
}

.back-to-top {
  position: fixed;
  right: 15px;
  z-index: 99999;
  bottom: 20px;
  background: #ce1212;
  /* height: 44px;
  width: 44px; */
  color: white;
  padding: 10px 12px;
  border-radius: 50%;
  text-align: center;
  font-size: 16px;
  text-decoration: none;
}

</style>

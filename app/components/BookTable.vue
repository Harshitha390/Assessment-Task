<template>
  <section class="book-table-section">
    <h4 class="subheading">Book a Table</h4>
    <h2 class="heading">Book Your <span>Stay With Us</span></h2>

    <div class="form-container">
      <div class="image-side">
        <img src="/images/reservation.jpg" alt="Table" />
      </div>

      <form class="form-side">
        <div class="input-row">
          <input type="text" placeholder="Your Name" />
          <input type="email" placeholder="Your Email" />
          <input type="tel" placeholder="Your Phone" />
        </div>
        <div class="input-row">
          <input type="date" placeholder="dd-mm-yyyy" />
          <input type="time" />
          <input type="number" placeholder="# of people" />
        </div>
        <textarea rows="5" placeholder="Message"></textarea>

        <button type="submit">Book a Table</button>
      </form>
    </div>
  </section>
</template>

<script setup>
// You can add form logic later if needed
</script>

<style scoped>
.book-table-section {
  padding: 40px 20px;
    padding: 60px 0;
  text-align: center;
}

.subheading {
  text-transform: uppercase;
  /* margin-bottom: 8px; */
    font-size: 13px;
    letter-spacing: 1px;
    font-weight: 400;
    padding: 0;
    margin: 0;
    color: color-mix(in srgb, #212529, transparent 50%);
    font-family: "Roboto", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
}

.heading {
    margin-bottom: 30px;
    color: #37373f;
    margin: 10px 0 0 0;
    font-size: 48px;
    font-weight: 500;
    font-family: "Amatic SC", sans-serif;
}

.heading span {
  color: #ce1212;
}

.form-container {
  display: flex;
  justify-content: center;
  /* align-items: flex-start; */
  align-items: center;
  gap: 30px;
  flex-wrap: wrap;
  padding: 80px 100px;
  border-radius: 8px;
}

.image-side img {
  width: 400px;
  /* height: auto; */
  min-height: 500px;
  background-size: cover;
  background-position: center;
  margin-left: 10px;
 
}

.form-side {
  flex: 1;
  padding: 30px;
  min-width: 300px;
   background: color(srgb 0.129412 0.145098 0.160784 / 0.03);
  display: flex;
  flex-direction: column;
  gap: 15px;
  align-self: center;
  margin-left: -20px;
}


.input-row {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  /* margin-bottom: 5px; */
 
}

.input-row input {
  flex: 1;
  font-size: 14px;
  color: #212529;
  background-color: color-mix(in srgb, white, transparent 20%);
  padding: 10px 15px;
  border: 1px solid #ccc;
  border-radius: 0px;
  border-color: color-mix(in srgb, #212529, transparent 80%);
  
}

textarea {
  padding: 10px 15px;
  font-size: 14px;
  color: #212529;
  border: 1px solid #ccc;
    border-radius: 0px;
  border-color: color-mix(in srgb, #212529, transparent 80%);
  resize: vertical;
}

button {
  /* padding: 12px 20px; */
  background-color: #ce1212;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  align-self: flex-start;
  border-width: 0px;
  border-style: initial;
  border-color: initial;
  border-image: initial;
  padding: 14px 60px;
  transition: 0.4s;
   
}

button:hover {
  background: 
 color-mix(in srgb, #ce1212, transparent 20%);
}

.input-row input:focus,
textarea:focus {
  border-color: #ce1212;
  outline: none;
}

.form-container .form-side button{
  align-self: center;
}
/* Responsive for tablets */
@media (max-width: 1024px) {
  .form-container {
    flex-direction: column;
    align-items: center;
    padding: 40px 20px;
    gap: 20px;
  }

  .image-side img {
    width: 100%;
    min-height: auto;
    margin-left: 0;
  }

  .form-side {
    margin-left: 0;
    padding: 20px;
  }

  .heading {
    font-size: 38px;
  }
}

/* Responsive for mobile */
@media (max-width: 768px) {
  .form-container {
    flex-direction: column;
    align-items: center;
    padding: 30px 15px;
  }

  .image-side img {
    width: 100%;
    max-width: 500px;
    min-height: auto;
  }

  .form-side {
    width: 100%;
    max-width: 500px;
    padding: 20px;
  }

  .input-row {
    flex-direction: column;
    gap: 12px;
  }

  .input-row input,
  textarea {
    width: 100%;
  }

  button {
    align-self: center;
    width: 80%;
    max-width: 300px;
  }

  .heading {
    font-size: 32px;
  }
}

/* Extra small devices */
@media (max-width: 480px) {
  .heading {
    font-size: 26px;
  }

  .subheading {
    font-size: 12px;
  }

  .form-side {
    padding: 15px;
  }

  button {
    padding: 12px 20px;
    font-size: 14px;
  }
}
@keyframes fadeUp {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.book-table-section,
.subheading,
.heading,
.form-container,
.image-side img,
.form-side {
  opacity: 0;
  animation-name: fadeUp;
  animation-duration: 0.6s;
  animation-fill-mode: forwards;
  animation-timing-function: ease-out;
}

.book-table-section { animation-delay: 0.1s; }
.subheading { animation-delay: 0.2s; }
.heading { animation-delay: 0.3s; }
.form-container { animation-delay: 0.4s; }
.image-side img { animation-delay: 0.5s; }
.form-side { animation-delay: 0.6s; }

</style>

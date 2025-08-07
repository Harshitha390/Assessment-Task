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
          <input type="text" placeholder="dd-mm-yyyy" />
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
    color: 
 color-mix(in srgb, #212529, transparent 50%);
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
  align-items: flex-start;
  gap: 30px;
  flex-wrap: wrap;
  background: white;
  padding: 20px;
  border-radius: 8px;
}

.image-side img {
  width: 300px;
  height: auto;
}

.form-side {
  flex: 1;
  min-width: 300px;
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.input-row {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
}

.input-row input {
  flex: 1;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

textarea {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  resize: vertical;
}

button {
  padding: 12px 20px;
  background-color: #c0392b;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  align-self: flex-start;
}

button:hover {
  background-color: #a93226;
}
</style>

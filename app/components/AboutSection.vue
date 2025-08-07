<template>
    <section class="about-section" id="AboutSection">
        <div class="heading">
            <small>ABOUT US</small>
            <h2>Learn More <span class="highlight">About Us</span></h2>
        </div>

        <div class="about-content">
            <!-- Left Side Image -->
            <div class="about-image">
                <img src="/images/about.jpg" />
                <!-- Contact Section -->
                <div class="contact-box">
                    <p>
                        <strong>Book a Table</strong><br /><span class="phone">+1 5589 55488 55</span>
                    </p>
                </div>
            </div>

            <!-- Right Side Content -->
            <div class="about-text">
                <p class="intro">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, <br />sed do
                    eiusmod tempor incididunt ut labore et dolore <br />magna aliqua.
                </p>

                <ul class="features">
                    <li>
                        <i class="fa-solid fa-circle-check" style="color: #c11212"></i>
                        Ullamco laboris nisi ut aliquip ex ea commodo
                        consequat.
                    </li>
                    <li>
                        <i class="fa-solid fa-circle-check" style="color: #c11212"></i> Duis
                        aute irure dolor in reprehenderit in voluptate <br />
                        velit.
                    </li>
                    <li>
                        <i class="fa-solid fa-circle-check" style="color: #c11212"></i>
                        Ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate trideta storacalaperda mastiro dolore eu fugiat nulla pariatur.
                    </li>
                </ul>

                <p class="para">
                    Ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute
                    irure dolor in reprehenderit in voluptate velit esse cillum dolore eu
                    fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident.
                </p>

                <div class="video-section">
                    <div class="video-thumb">
                        <img src="/images/about-2.jpg" alt="Food Video" />
                        <div class="play-btn">
                            <span>
                                <a href="https://www.youtube.com/watch?v=Y7f98aduVJ8" class="">
                                    <i class="fa-solid fa-play"></i>
                                </a>
                            </span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup></script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Amatic+SC:wght@400;700&display=swap");

.about-section {
    padding: 4rem 2rem;
    background: #fff;
    display: block;
    unicode-bidi: isolate;
    scroll-margin-top: 92px;
    padding: 60px 0px;
    overflow: clip;
}

.heading {
    text-align: center;
    margin-bottom: 2rem;
}

small {
    letter-spacing: 1px;
    font-weight: 400;
    color: color-mix(in srgb, #212529, transparent 50%);
    display: inline-block;
    font-family: "Roboto", system-ui, -apple-system, "Segoe UI", Roboto,
        "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif,
        "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
    padding: 0px;
    margin: 0px;
}

.heading h2 {
    /* font-size: 2rem;
  font-weight: normal;
  font-size: 13px; */
    color: #37373f;
    font-size: 48px;
    font-weight: 500;
    font-family: "Amatic SC", sans-serif;
    margin: 10px 0px 0px;
}

.heading .highlight {
    color: #ce1212;
}

.heading {
    display: block;
    margin-block-start: 1em;
    margin-block-end: 1em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    unicode-bidi: isolate;
}

.about-content {
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    align-items: flex-start;
    width: 114%;
    padding-right: 12px;
    padding-left: 14px;
    margin-right: auto;
    margin-left: auto;
}

.about-image {
    flex: 1 1 45%;
    max-width: 100%;
    height: auto;
    padding-top: 50px;
    padding-left: 90px;
}

.about-image img {
    width: 100%;
    object-fit: cover;
    vertical-align: middle;
}

.about-content .contact-box {
    text-align: center;
    border: 4px solid color-mix(in srgb, #212529, transparent 30%);
    padding: 22px;
}

.contact-box strong {
    font-size: 24px;
    color: #37373f;
    /* display: block; */
    margin-block-start: 1em;
    margin-block-end: 1em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    unicode-bidi: isolate;
}

.contact-box .phone {
    color: #ce1212;
    font-weight: 500;
    font-size: 28px;
    margin: 0px;
}

.about-text {
    flex: 1 1 45%;
    font-family: sans-serif;
    padding-left: 40px;
    padding-top: 50px;

}

.para{
    padding-right: 300px;
}

.intro {
    font-style: italic;
    color: color-mix(in srgb, #212529, #ffffff 50%);
    margin-top: 0;
    margin-bottom: 1rem;
}

.features {
    list-style: none;
    padding: 0;
    margin: 1rem 0;
    margin-top: 0;
    margin-bottom: 1rem;
    display: block;
    margin-block-start: 1em;
    margin-block-end: 1em;
    /* padding-inline-start: 40px; */
    unicode-bidi: isolate;
    max-width: 400px;
}

.features li {
    margin: 0.5rem 0;
    font-size: 1rem;
    /* position: absolute;
        font-size: 20px;
        left: 0px;
        top: -3px;
        color: #CE1212;
        font-style: italic; */
}

.check {
    color: #ce1212;
    margin-right: 0.5rem;
}

.video-section {
    margin-top: 1.5rem;
}

.video-thumb {
    position: relative;
    display: inline-block;
    max-width: 350px;
    overflow: hidden;
}

.video-thumb img {
    width: 100%;
    display: block;
}

.play-btn {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: radial-gradient(#ce1212 50%, color-mix(in srgb, #ce1212, transparent 75%) 52%);
  color: white;
  width: 94px;
  height: 94px;
  font-size: 24px;
  display: flex;
  justify-content: center;
  align-items: center;
  animation: pulse 2s infinite;
  cursor: pointer;
  border-radius: 50%;
  transition: transform 0.3s ease, scale 0.3s ease;
}

.play-btn:hover {
  transform: translate(-50%, -50%) scale(1.2);
}

.play-btn:active {
  transform: translate(-50%, -50%) scale(1.4);
}

@keyframes pulse {
  0% {
    transform: translate(-50%, -50%) scale(1);
  }

  50% {
    transform: translate(-50%, -50%) scale(1.1);
  }

  100% {
    transform: translate(-50%, -50%) scale(1);
  }
}

.contact-box {
    border: 2px solid #444;
    margin-top: 2rem;
    padding: 1rem 2rem;
    text-align: center;
}
</style>

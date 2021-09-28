<template>
  <div id="app-container">
    <header>
      <div class="logo">
        <h1>Utopia</h1>
        <p>Мир квартир</p>
      </div>
      <div class="links">
        <h3>Мы в соц. сетях!</h3>
        <div>
          <a href="https://www.instagram.com/utopia.uzbekistan/" target="_blank"
            ><img src="./assets/instagram.svg" alt="instagram"
          /></a>
          <a
            href="https://www.facebook.com/UtopiaUzbekistan-111223251255196"
            target="_blank"
            ><img src="./assets/facebook.svg" alt="facebook"
          /></a>
          <a href="https://t.me/utopia_uz_official" target="_blank"
            ><img src="./assets/telegram.svg" alt="telegram"
          /></a>
        </div>
      </div>
    </header>
    <section>
      <div class="main">
        <h1>Наш сайт в разработке!</h1>
      </div>
      <div class="sub">
        <h3>Свяжитесь с нами!</h3>
        <p>+998 88 300-32-02</p>
        <a href="mailto: Utopia.Uzbekistan@gmail.com" target="_blank"
          ><p>Utopia.Uzbekistan@gmail.com</p></a
        >
      </div>
    </section>
    <footer>© {{ new Date().getFullYear() }} | "UTOPIA"</footer>
  </div>
</template>

<script>
export default {
  name: "App",
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Sofia&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Days+One&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  background: linear-gradient(to right, #d52735, #ec4438);
}
#app-container {
  width: 100%;
  height: 100vh;
}
header {
  display: flex;
  justify-content: space-between;
  /* height: 22vh; */
  width: 80%;
  margin: 0 auto;
  padding-top: 2.5rem;
  color: #fff;
}
.logo h1 {
  font-family: "Sofia", cursive;
  font-size: 5rem;
}
.logo p {
  font-family: "Sofia", cursive;
  font-size: 1.5rem;
  text-align: end;
}
.links {
  display: flex;
  flex-direction: column;
  justify-content: center;
  color: #e2b370;
}
.links h3 {
  font-size: 1.6rem;
  font-family: "Days One", sans-serif;
  margin-bottom: 8px;
}
.links div {
  text-align: end;
}
.links div img {
  margin-left: 8px;
}
.links a:hover {
  opacity: 0.7;
}
section {
  width: 80%;
  height: 78vh;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  font-family: "Days One", sans-serif;
  margin: 0 auto;
  color: rgb(233, 219, 219);
}
.main {
  animation: fading 3s ease infinite;
}
.main h1 {
  font-size: 5rem;
  animation: coming-home 3s ease;
}
.sub {
  width: fit-content;
  font-size: 1.8rem;
}
.sub h3 {
  color: #e2b370;
  font-size: 2.3rem;
  animation: coming 3s ease;
  transform: translateX(-300%);
  animation-fill-mode: forwards;
}
.sub p:nth-child(1) {
  animation: coming 3s ease 0.5s;
  transform: translateX(-300%);
  animation-fill-mode: forwards;
}
.sub p:nth-child(2) {
  animation: coming 3s ease 0.3s;
  transform: translateX(-300%);
  animation-fill-mode: forwards;
}
.sub a {
  color: rgb(233, 219, 219);
  transition: all 0.4s ease;
  text-decoration: none;
}
.sub a:hover {
  text-decoration: underline;
}
footer {
  width: 80%;
  margin: 2rem auto 0;
  padding-bottom: 2rem;
  font-family: "Days One", sans-serif;
  color: rgb(233, 219, 219);
}
@keyframes fading {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}
@keyframes coming-home {
  0% {
    transform: translateX(-100%);
  }
  80% {
    transform: translateX(2%);
  }
  100% {
    transform: translateX(0);
  }
}
@keyframes coming {
  0% {
    transform: translateX(-300%);
  }
  80% {
    transform: translateX(2%);
  }
  100% {
    transform: translateX(0);
  }
}
@media screen and (max-width: 1260px) {
  .logo h1 {
    font-size: 4rem;
  }
  .main h1 {
    font-size: 3rem;
  }
}
@media screen and (max-width: 765px) {
  .logo h1 {
    font-size: 3rem;
  }
  section {
    height: 50vh;
  }
  .links h3 {
    font-size: 1.3rem;
  }
  .main h1 {
    font-size: 2rem;
  }
  .sub h3 {
    font-size: 1.6rem;
  }
  .sub {
    font-size: 1.2rem;
  }
}
@media screen and (max-width: 576px) {
  header {
    flex-direction: column;
    align-items: center;
  }
  .links div {
    text-align: center;
  }
  section {
    align-items: center;
    justify-content: space-evenly;
    text-align: center;
  }
  footer {
    text-align: center;
  }
}
</style>

<template>
    <div id="wrap">
        <header class="page-header">
            <router-link :to="{ name: 'home' }" :class="['logo']">
                <img src="./assets/img/logo.png" alt="Sedona">
            </router-link>
            <ul class="main-menu clearfix">
                <li class="main-menu__item" v-for="(item, index) in menu" :key="'main-menu__item-' + index">
                    <router-link :to="{ name: item.route }" :class="['main-menu__link']">{{ item.title }}</router-link>
                </li>
            </ul>
        </header>
        <section class="welcome">
            <img class="welcome__img" src="./assets/img/welcome.png" alt="Welcome to Sedona">
        </section>
        <section class="intro">
            <h1 class="intro__greetings">Седона — небольшой городок в Аризоне, заслуживающий большего!</h1>
            <p class="intro__tagline">Рассмотрим 5 причин, по которым Седона круче, чем гранд каньон!</p>
        </section>
    </div>
</template>

<style lang="scss">
body {
  font-family: 'PT Sans', sans-serif;
  background-color: #f2f2f2;
}

img {
  max-width: 100%;
  height: auto;
}

#wrap {
  max-width: 1200px;
  margin-left: auto;
  margin-right: auto;
  box-shadow: 0 0 15px 5px rgba(0, 0, 0, 0.2);
  background-color: #fff;

  height: 1500px;
}

.page-header {
  position: relative;
  z-index: 1;
}

.main-menu {
  list-style: none;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: 0;
  font-size: 0;

  display: flex;
  align-items: center;
  justify-content: space-between;
}

.main-menu__item {
  //   display: inline-block;
  //   vertical-align: middle;
  //   float: left;
  text-align: center;
  text-transform: uppercase;
  font-size: 14px;
  line-height: 17px;
  padding: 19px 0;
  width: 20%;
  &:nth-child(2) {
    margin-right: 20%;
  }
}

.main-menu__link {
  color: #000;
  text-decoration: none;
}

.logo {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
}

// .clearfix {
//   &:after {
//     content: '';
//     display: block;
//     clear: both;
//   }
// }

.welcome {
  background-image: url('./assets/img/background.jpg');
  background-position: center top;
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
  padding: 50px 15px;
  position: relative;
  &:after {
    content: '';
    display: block;
    width: 100%;
    height: 57px;
    background-image: url('./assets/img/shape.png');
    background-position: center top;
    background-repeat: no-repeat;
    background-size: cover;
    position: absolute;
    left: 0;
    right: 0;
    bottom: -1px;
  }
}

.welcome__img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.intro {
  text-align: center;
  padding-top: 50px;
  padding-bottom: 50px;
  max-width: 350px;
  margin-left: auto;
  margin-right: auto;
}

.intro__greetings {
  font-size: 21px;
  font-weight: bold;
  margin-bottom: 15px;
}

@media (max-width: 768px) {
  .intro {
    padding-left: 15px;
    padding-right: 15px;
  }
  
  .intro__greetings {
    font-size: 18px;
  }

  .intro__tagline {
    font-size: 12px;
  }
}
</style>

<script>
export default {
    data() {
        return {
            menu: [
                {title: "Информация", route: "home"},
                {title: "Фото и Видео", route: "home"},
                {title: "Карта Штата", route: "home"},
                {title: "Гостиницы", route: "home"}
            ]
        }
    }
}
</script>

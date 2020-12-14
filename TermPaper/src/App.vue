<template>
  <div class="div-bg">
    <div id="app">
      <div id="header">
        <a href="http://pfrf.ru">
          <div id="pfrf_logo_img"></div>
        </a>
        <a id="pfrf_link" href="http://pfrf.ru">
          <span id="pfrf_head">Пенсионный Фонд<br>Российской Федерации</span>
        </a>
      </div>
      <div id="header2" style="background: rgb(174,104,74);"><span id="album_header">Форматы документов ПФР</span></div>
      <div id="body_div">
        <ComboUl />
      </div>
    </div>
  </div>
</template>

<script>
import ComboUl from '@/components/ComboUl'
export default {
  name: 'app',
  components: {
    ComboUl
  }
}
</script>

<style>
#app {
  background-color: whitesmoke;
  height: 99%;
  width: 90%;
  margin: 10px auto;
}

.div-bg {
  background: url('images/Library.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  width: 100vw;
  height: 100vh;
}

.div-bg {
  padding: 10px;
}

body {
  padding: 0;
  margin: 0;
  overflow-x: hidden;
}

:root {
  padding: 0;
  margin: 0;
}

#pfrf_head {
  text-align: center;
  color: black;
  font-size: 30px;
  font-weight: 600;
}

#header {
  padding: 10px 0px;
  margin: 10px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}

#album_header {
  text-align: center;
  color: whitesmoke;
  font-size: 45px;
  font-weight: 550;
}

#header2 {
  background-color: #31abe4;
  margin-top: 10px;
  display: flex;
  justify-content: center;
  padding: 15px 0px;
}

#pfrf_link {
  text-align: center;
  text-decoration: none;
}

#pfrf_link:hover {
  text-decoration: none;
  color: black;
}

#pfrf_logo_img {
  background: url('images/pfrf_logo.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  width: 100px;
  height: 100px;
  margin-right: 10px;
}

#body_div {
  padding: 0px 30%;
}

.list-group-item {
  text-align: center;
  list-style-type: none;
  font-size: 35px;
}

</style>

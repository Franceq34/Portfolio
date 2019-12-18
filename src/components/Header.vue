<template>
    <div id="headerContainer">
      <div id="imgContainer">
        <img src="../assets/profile.png" alt="Photo de profil" id="profilePicture"/>
      </div>
    <div id="infosContainer">
      <div id="nameContainer">Quentin <b>FRANCE</b></div>
      <div id="locationContainer">Montpellier, France</div>
      <div id="linksContainer">
        <a class="disabled" title="Bientôt disponible !"><img src="../assets/icons/cv.svg" alt="Logo CV"/></a>
        <a href="https://www.linkedin.com/in/quentin-france-b11723107/" target="blank"><img src="../assets/icons/linkedin.svg" alt="Logo Linkedin"/></a>
        <a href="https://github.com/Franceq34" target="blank"><img src="../assets/icons/github.svg" alt="Logo Github"/></a>
      </div>
    </div>
    </div>
</template>

<style scoped>

  div#headerContainer {
    margin-top: 25px;
  }

  div#imgContainer {
    display: block;
    background: white;
    border-radius: 1000px;
    margin:auto;
    padding:0;
    width: 150px;
    height: 150px;
    box-shadow: 0 1px 4px rgba(0, 0, 0, .3);
    transition: 0.5s;
  }div#imgContainer:hover {
    scale:1.07;
  }

  a.disabled img {
    opacity: 0.4;
    cursor: default!important;
  }

  img#profilePicture {
    width: 140px;
    margin: 5px;
  }

  div#infosContainer {
    margin-top: 15px;
    color: white;
    text-align: center;
  }

  div#nameContainer{
    font-size: 1.5rem;
  }

  div#locationContainer {
    margin-top: 5px;
    font-size: 0.8rem;
  }

  div#linksContainer {
    margin-top: 7px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  div#linksContainer img {
    height: 25px;
    width: 25px;
    margin: 0px 4px;
    cursor: pointer;
    transition: 0.1s;
  }
  div#linksContainer img:hover {
    scale:1.13;
  }
  div#linksContainer .disabled img:hover {
    scale:1;
  }

</style>

<script>

export default {
  name: 'Header',

  components: {
  }
};
</script>
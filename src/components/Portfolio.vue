<template>
  <div class="container-fluid">
    <div class="parallax parapic1 no-phone" id="top">
      <div class="headline">
        <h1>BALD MIKE. WEB DEVELOPER. </h1>
        <br>
        <b-button @click="goto('nav')" variant="outline-secondary" id="welcomeSign">Welcome</b-button>  
      </div>
    </div>

    <div class="white-bar" id="nav">
      <b-row>
        <b-col cols="12" sm="3">
          <b-button class="about button" @click="goto('aboutSection')">ABOUT</b-button>
        </b-col>
        
        <b-col cols="12" sm="3">
          <b-button class="projects button" @click="goto('projects')" id="projectsButton">PROJECTS</b-button>
        </b-col>

        <b-col cols="12" sm="3">
          <a href="https://github.com/baldmike" target="_blank"><b-button id="github-desc" class="github-desc button">GITHUB</b-button></a>
        </b-col>
        
        <b-col cols="12" sm="3">
          <b-button class="contact button" @click="goto('contactSection')" id="contact">CONTACT</b-button>
        </b-col>
      </b-row>
    </div>

    <b-button style="margin-bottom: 20px;" variant="outline-secondary" @click="upTop">BACK TO THE TOP</b-button>
    

    <div class="parallax parapic2" id="aboutSection"></div>
    <b-row>
      <b-col>
        <h1>PROJECTS</h1>
      </b-col>
    </b-row>
    <div class="white-bar" id="projects">
      <b-row>
        <b-col cols="12" sm="3">
          <a href="https://livelikeroo.org" target="_blank"><b-button id="github-desc" class="roo button"></b-button></a>
        </b-col>
        
        <b-col cols="12" sm="3">
          <b-button class="gmap button" id="projectsButton" v-b-modal.gmapModal></b-button>
        </b-col>
        
        <b-col cols="12" sm="3">
          <a href="https://www.regroupconnect.com" target="_blank"><b-button id="regroupButton" class="regroup button"></b-button></a>
        </b-col>

        <b-col cols="12" sm="3">
          <b-button class="contact button" @click="goto('contactSection')" id="contact">CONTACT</b-button>
        </b-col>
      </b-row>
    </div>

    <b-button style="margin-bottom: 20px;" variant="outline-secondary" @click="upTop">BACK TO THE TOP</b-button>

    <div class="parallax parapic3"></div>

    <div class="white-bar" id="contactSection">
      <b-row>
        <b-col>
          <h1>CONTACT BALD MIKE</h1>
        </b-col>
        
      </b-row>
      <b-row>
        <b-col cols="12" sm="3">
          <a href="mailto:baldmike312@gmail.com"><b-button class="email button">EMAIL</b-button></a>
        </b-col>

        <b-col cols="12" sm="3">
          <a href="https://www.linkedin.com/in/baldmike/" target="_blank"><b-button class="contact button">LINKEDIN</b-button></a>
        </b-col>
        
        <b-col cols="12" sm="3">
          <a href="https://www.twitter.com/baldmikesays" target="_blank"><b-button id="twitterButton" class="button">TWITTER</b-button></a>
        </b-col>

        <b-col cols="12" sm="3">
          <a href="https://www.github.com/baldmike" target="_blank"><b-button class="button">GITHUB</b-button></a>
        </b-col>      
      </b-row>
    </div>

    <b-button style="margin-bottom: 20px;" variant="outline-secondary" @click="upTop">BACK TO THE TOP</b-button>

    <div class="copyright">
      &copy; {{year}}
      <a href="https://github.com/baldmike" target="_blank">Bald Mike</a>
    </div>





    <!-- Roo Modal -->
    <b-modal id="rooModal" title="Live Like Roo" hide-footer no-close-on-backdrop>
      <p class="my-4">This is the Roo Modal</p>
    </b-modal>

    <!-- Regroup Modal -->
    <b-modal id="regroupModal" title="Regroup" hide-footer no-close-on-backdrop>
      <a href="https://www.regroupconnect.com" target="_blank"><button class="my-3">Visit RegroupConnect</button></a><p class="my-4">Using Agile methodology, I was contracted to assist the Lead with building, testing and deployment of regroupconnect, a hipaa-compliant tele-
      psychiatry platform built with Laravel and Vue.js and deployed on EC2 & S3</p>
    </b-modal>

    <!-- gmap Modal -->
    <b-modal id="gmapModal" title="Coding Challenges & Personal Projects" hide-footer no-close-on-backdrop>
      <a href="https://baldmike.github.io/filtered-google-maps/" target="_blank"><button class="my-3">Google Maps Challenge</button></a><p>Given a .xlsx file, place all 1500 properties on Google Map. Markers should be a gradient of green to red, based on estimated home value, low to high. Filters are all fully reactive. Clicking button above will open a new window with a demo.</p> 

      <hr>

      <a href="https://baldmike.github.io/craps-vue/" target="_blank"><button class="my-3">Vue Craps Game</button></a><p>A craps game in Vue.js. User can make a "pass line" wager of $5, $25, $50, $100, and starts game with $500. App uses Vuex for state management, instead of passing variables as props, so there is one source of truth. Clicking button above will open a new window with a demo.</p> 

    </b-modal>

    <!-- github Modal -->
    <b-modal id="githubModal" title="Bald Mike's Github" hide-footer no-close-on-backdrop>
      <p class="my-4">This is the Github Modal</p>
    </b-modal>

    <!-- email Modal -->
    <b-modal id="emailModal" title="Email Bald Mike" hide-footer no-close-on-backdrop>
      <p class="my-4"></p>
    </b-modal>

</div>  
</template>

<script>

export default {
  name: 'Portfolio',

  data() {
    return {
      year: new Date().getFullYear()
    }
  }, 

  methods: {
    goto(value) {
      let elem = document.getElementById(value);
      elem.scrollIntoView({behavior: 'smooth'});
    },
    upTop() {
      let elem = document.getElementById("top");
      elem.scrollIntoView({behavior: 'smooth'});

    }
  }, 

  created() {
  
  }
}
</script>




<style scoped>

/* @media only screen and (min-width: 800px) { */
  
  /* .about:hover::after { 
    content: " - Who is Bald Mike?";
  }

  #projectsButton:hover::after { 
    content: " - Examples of recent work.";
  }

  #github-desc:hover::after { 
    content: " - Show me the code!";
  }

  #contact:hover::after { 
    content: " - Get in touch with Bald Mike!";
  } */


h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.parallax {
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  min-height: 100vh;
}

.parapic1 {
  background-image: url("../assets/Photo_by_Ales_Nesetril_on_Unsplash.jpg");
  margin-top: -60px;

}

.parapic2 {
  background-image: url("../assets/stairsSkills.png");
}

.parapic3 {
  background-image: url("../assets/codeBM2.jpg");
}

.white-bar { 
  background-color: white;
  min-height: 500px;
}

.button {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  margin: 150px 0px;
  background-size: 200px;
  background-repeat: no-repeat;
  background-color: white;
  color: cornflowerblue;
  transition: 800ms;
}

.regroup {
  background-image: url("../assets/regroup.png");
}

.roo {
  background-image: url("../assets/llr_logo.png");
}

.gmap {
  background-image: url("../assets/gmaps.png");
}

.github {
  background-image: url("../assets/github.jpg");
}

.headline {
  position: sticky;
  top: 200px;
}

.copyright {
  position: relative;
  bottom: 0;
  left: 0;
  right: 0;

/* } */
}
</style>

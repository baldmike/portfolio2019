<template>
  <div class="container-fluid">
    <b-navbar/>
    <div class="parallax parapic1" id="top">
      <div class="headline">
        <h1>BALD MIKE. WEB DEVELOPER. </h1>
        <br>
        <b-button @click="goto('nav')">Welcome</b-button>  
      </div>
      
    </div>

    <div class="white-bar" id="nav">
      <b-row>
        <b-col cols="6" sm="3">
          <b-button class="about button" v-b-modal.aboutModal>ABOUT</b-button>
        </b-col>
        
        <b-col cols="6" sm="3">
          <b-button class="projects button" @click="goto('projects')">PROJECTS</b-button>
        </b-col>

        <b-col cols="6" sm="3">
          <b-button class="github-desc button" v-b-modal.githubModal>GITHUB</b-button>
        </b-col>
        
        <b-col cols="6" sm="3">
          <b-button class="contact button" @click="goto('contact')">CONTACT</b-button>
        </b-col>
      </b-row>
    </div>

    <b-button style="margin-bottom: 20px;" variant="outline-primary" @click="upTop">BACK TO TOP</b-button>
    

    <div class="parallax parapic2"></div>

    <div class="white-bar" id="projects">
      <b-row>
        <b-col cols="6" sm="3">
          <b-button class="roo button" v-b-modal.rooModal></b-button>
        </b-col>
        
        <b-col cols="6" sm="3">
          <b-button class="gmap button" v-b-modal.gmapModal></b-button>
        </b-col>

        <b-col cols="6" sm="3">
          <b-button class="github button" v-b-modal.githubModal></b-button>
        </b-col>
        
        <b-col cols="6" sm="3">
          <b-button class="regroup button" v-b-modal.regroupModal></b-button>
        </b-col>
      </b-row>
    </div>

    <b-button style="margin-bottom: 20px;" variant="outline-primary" @click="upTop">BACK TO TOP</b-button>

    <div class="parallax parapic3"></div>

    <div class="white-bar" id="contact">
      <b-row>
        <b-col cols="6" sm="3">
          <b-button class="about button" v-b-modal.aboutModal>EMAIL</b-button>
        </b-col>
        
        <b-col cols="6" sm="3">
          <b-button class="projects button" v-b-modal.codeModal>TWITTER</b-button>
        </b-col>

        <b-col cols="6" sm="3">
          <b-button class="github-desc button" v-b-modal.githubModal>GITHUB</b-button>
        </b-col>
        
        <b-col cols="6" sm="3">
          <b-button class="contact button" v-b-modal.regroupModal>LINKEDIN</b-button>
        </b-col>
      </b-row>
    </div>

    <b-button style="margin-bottom: 20px;" variant="outline-primary" @click="upTop">BACK TO TOP</b-button>

    <div class="copyright">
                &copy;Copyright {{year}}
                <a href="https://github.com/baldmike" target="_blank">Bald Mike</a>
            </div>





    <!-- Roo Modal -->
    <b-modal id="rooModal" title="Live Like Roo" hide-footer no-close-on-backdrop>
      <p class="my-4">This is the Roo Modal</p>
    </b-modal>

    <!-- Regroup Modal -->
    <b-modal id="regroupModal" title="Regroup" hide-footer no-close-on-backdrop>
      <p class="my-4">This is the Regroup Modal</p>
    </b-modal>

    <!-- gmap Modal -->
    <b-modal id="gmapModal" title="Google Maps" hide-footer no-close-on-backdrop>
      <p class="my-4">This is the Google Maps Modal</p>
    </b-modal>

    <!-- github Modal -->
    <b-modal id="githubModal" title="Bald Mike's Github" hide-footer no-close-on-backdrop>
      <p class="my-4">This is the Github Modal</p>
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
  }
}
</script>




<style scoped>

/* @media only screen and (max-width: 500px) {
  h1 {
    font-size: 5vw;
  }
} */
  .button {
    width: 50%;
    height: 50%;
    border-radius: 10%;
    margin: 150px 0px;
    color: white;
    background-color: cornflowerblue;
    transition: 500ms;
  }

  .about:hover::after { 
    content: " - Who is Bald Mike?";
  }

  .projects:hover::after { 
    content: " - Examples of recent work.";
  }

  .github-desc:hover::after { 
    content: " - Show me the code!";
  }

  .contact:hover::after { 
    content: " - Get in touch with Bald Mike!";
  }


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
  background-image: url("../assets/stairs3.jpg");
}

.parapic3 {
  background-image: url("../assets/codeBM.jpg");
}


.black-bar {
  background-color:white;
  min-height: 600px;
}

.white-bar {
  
  background-color: white;
  min-height: 500px;
}

.button {
  width: 200px;
  height: 200px;
  border-radius: 10%;
  margin: 150px 0px;
  background-size: 200px;
  background-repeat: no-repeat;
  background-color: white;
  color: cornflowerblue
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

}
</style>

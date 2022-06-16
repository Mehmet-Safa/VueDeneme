
<template>
  
  <div class="main-container" v-on:contextmenu="openMenu" @click="closeMenu">
    <div id="mehmet1" > Hello World! </div>
    

    <button type="button"  class="btn btn-warning mb-2" data-toggle="modal" data-target="#setYaz">
            <i class="fa-solid fa-pen"></i> Yaz
        </button>
    

    <!-- <div class="contentmenu-container">

        </div> -->
        <div id="menu" class="menu" v-show="showMenu" >
            <ul>
                <li @click="printname2">Başarılı yazdır</li>
                <li>boş</li>
                <li>boş</li>
                <li>boş</li>
            </ul>
        </div>
  
    <!-- <ejs-contextmenu target='#safaApp' :items='menuItems' ></ejs-contextmenu> -->  
    
  <div class="modal" id="setYaz" tabindex="-1" role="dialog">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">Modal title</h5>
          <button type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">

          <div class="input-group mb-3">
            <div class="input-group-prepend">
              <span class="input-group-text" id="basic-addon1"></span>
            </div>
            <input type="text" class="form-control" id="sonucMetin" placeholder="Write Something to print" aria-label="Username" aria-describedby="basic-addon1">
          </div>

        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
          <button type="button" name="button" @click="printname">Click here for print</button>
        </div>
      </div>
    </div>
  </div>

  

  </div>
</template>

<!-- <script>
import Vue from 'vue';
import { ContextMenuPlugin } from "@syncfusion/ej2-vue-navigations";

Vue.use(ContextMenuPlugin);
  export default {
      data () {
        return {
                  viewMenu: false,
        top: '0px',
        left: '0px',
            menuItems:[
            {
                text: 'Cut'
            },
            {
                text: 'Copy'
            },
            {
                text: 'Paste'
            }]
        };
    },

    methods: {
      testFunc($event){
        // console.dir($event);
        this.viewMenu=true;
        let elem = document.querySelector("#right-click-menu");
        elem.pageX=$event.pageX+"px";
        elem.pageY=$event.pageY+"px";
                 console.dir(elem);
      },
      printname(){
        var giveName = document.getElementById("sonucMetin").value;
        //console.log(giveName);
        $('#mehmet1').text(giveName);
      },
      printname2(){
        //var giveName = document.getElementById("sonucMetin").value;
        //console.log(giveName);
        $('#mehmet1').text("giveNameeeeeeeee");
      },
       setMenu: function(top, left) {
          
            largestHeight = window.innerHeight - this.$$.right.offsetHeight - 25;
            largestWidth = window.innerWidth - this.$$.right.offsetWidth - 25;

            if (top > largestHeight) top = largestHeight;

            if (left > largestWidth) left = largestWidth;

            this.top = top + 'px';
            this.left = left + 'px';
        },

        closeMenu: function() {
            this.viewMenu = false;
        },

        openMenu: function(e) {
            this.viewMenu = true;

            Vue.nextTick(function() {
                this.$$.right.focus();

                this.setMenu(e.y, e.x)
            }.bind(this));
            e.preventDefault();
        }
    },
  };
</script> -->

<script>


export default {
    
    data() {
        return {
            showMenu: false
        }
    },
    components: {

    },
    methods: {
        openMenu($event) {
            $event.preventDefault();
            console.log($event)
            let elem = document.getElementById("menu");
            elem.style.position = "absolute";
            elem.style.left = $event.offsetX + 'px';
            elem.style.top = ($event.offsetY) + 'px';
            this.showMenu = true;
        },
        test() {
            console.log("assasasa")
        },
        closeMenu() {
            console.log("Kapandıııı");
            this.showMenu = false;
        },
        printname(){
        var giveName = document.getElementById("sonucMetin").value;
        //console.log(giveName);
        $('#mehmet1').text(giveName);
      },
      printname2(){
        //var giveName = document.getElementById("sonucMetin").value;
        //console.log(giveName);
        $('#mehmet1').text("Başarılı");
      },
    }

};
</script>



<style>
@import "../../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-buttons/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-inputs/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-popups/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-navigations/styles/material.css";

/* Context Menu target */

</style>
<style scoped>
.main-container {
    width: 100vw;
    height: 100vh;
}

.contentmenu-container {
    width: 100vw;
    height: 600px;
    background-color: gray;
}

.menu {
    width: calc(80px + 20%);
    height: 100%;
}

ul {
    border: 3px solid green;
    list-style: none;
    /* display: flex;
    flex-flow: column; */
}

li {
    width: 100%;
    height: 30px;
    font-size: 15px;
    font-family: 'Times New Roman', Times, serif;
}

li:hover {
    background-color: grey;
    list-style: none;


}
</style>

                 
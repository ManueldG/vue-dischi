<template>
  <section>
      <div class="folder" >
          <div class="loading" v-if="loading">
        <pre>
        load "*" ,8 ,1
        searching for *
        loading...
        </pre>
              <div class="square">

              </div>
          </div>
          <div  v-else>
             <ul>
              <li v-for="( fold , index ) in folders.response" :key="index">
                <img :src="fold.poster" :alt="fold.title+fold.year">
                <ul class="detail">
                    <li  v-for="(el,i) in fold" :key="i">
                        <div class="desc" v-if="(i!=='poster')">
                            {{el}} 
                        </div> 
                        
                    </li>
                </ul> 
                  
              </li>
          </ul> 
          </div>
          
          
      </div>
  </section>
</template>

<script>
import axios from "axios";
export default {
    name: 'Folder',
    data(){
        return {
            urlAPI : 'https://flynn.boolean.careers/exercises/api/array/music',
            folders : [],
            loading : true,
        }
    },
    created(){
            this.foldersGET();
            setTimeout(()=>{
                this.loading = false;
            },2000)
                     
        
    },
    methods:{
        foldersGET(){
            // Make a request for a user with a given ID
            axios.get(this.urlAPI)
            .then((response) =>{
                this.folders = response.data;
                console.log(response);
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            .then(function () {
                // always executed
            })
        }
    }

    } 


</script>

<style scoped lang="scss">

.folder{
    display:flex;
    justify-content: center;
    align-items:center;
    .loading{
        width: 400px;
        height: 300px;
        background-color: rgb(60, 134, 177);
        color: rgb(176, 196, 207);
        .square{
            margin-left:50px;
            height: 10px;
            width: 10px;
            background-color: rgb(176, 196, 207);
            animation-name: blink;
            animation-duration: .5s; 
            animation-direction: alternate;
            animation-iteration-count: infinite;
        }
        @keyframes blink {
            from {background-color:rgb(60, 134, 177);}
            to {background-color: rgb(176, 196, 207);}
        }
    }
    ul{
        display:flex;
        flex-wrap: wrap;
        justify-content:center;
        list-style: none;

        li{            
            img{
                width:250px;
                margin: 10px;
            }
            ul {
                flex-direction: column;
                display: flex;
                flex-wrap: wrap;
                justify-content: center;
                list-style: none;
                li{
                    flex-direction: column;
                display: flex;
                flex-wrap: wrap;
                justify-content: center;
                list-style: none;
                }

            }
        }
    }
}

</style>
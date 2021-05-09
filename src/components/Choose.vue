<template>
<div class="choose">
    <label for="folder">Scegli genere musicale</label>
    <select name="folder" id="folder" placeholder="seleziona genere" v-model="currentValue" @change="$emit('changeP',currentValue);" >{{currentValue}}
      <option value="">Seleziona genere</option>
      <option v-for="(val,index) in generi" :key="index" :value="val.toLowerCase()">{{val}}</option>
    </select>
</div>
</template>

<script>
export default {
    name: 'Choose',
    props: {gen:{
            type:String,
            default:'1'
            }
            },
    data() {
        return{
            currentValue:'',
            generi:['Pop','Metal','Rock','Jazz'],
            
            }
        },
    created(){
        
    },
    methods: {
        view(ev){
            console.log(ev.srcElement.value);
            return ev.srcElement.value;
        }
    }

}
</script>

<style>

.choose{
    margin: 10px auto;
    border: 1px solid blue;
    border-radius: 5px;
    width:50%;
    text-align: center;
    background-color: beige;
}

</style>
<template>
<div class="choose">
    <label for="folder">scegli genere</label>
    <select name="folder" id="folder" @change="($emit('view',currentValue))">
      <option v-for="(val,index) in generi" :key="index" :value="val.toLowerCase()">{{val}}</option>
    </select>{{genere}}
</div>
</template>

<script>
export default {
    name: 'Choose',
    props: {genere:String},
    data() {
        return{
            currentValue:'',
            generi:['Pop','Metal','Rock','Jazz']
            }
        },
    methods: {
        view(ev){
            console.log('change',ev.srcElement.value);
            this.currentValue = ev.srcElement.value;            
        }
    }

}
</script>

<style>

</style>
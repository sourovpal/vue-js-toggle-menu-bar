<script>
import { ref } from 'vue';
import MenuGroup from './MenuGroup.vue';

export default {
    components:{
        MenuGroup,
    },
    data(){
        return{
        menus:[
            {
                label:'Dashboard',
                icon:'',
                children:[
                    {
                        label:'All',
                        icon:'',
                    },
                    {
                        label:'New',
                        icon:'',
                    },
                    {
                        label:'Processing',
                        icon:'',
                    },
                    {
                        label:'Today',
                        icon:'',
                    },
                    {
                        label:'Future',
                        icon:'',
                    },
                    {
                        label:'Unassigned',
                        icon:'',
                    },
                ]
            },
            {
                label:'Leads',
                icon:'',
                children:[
                    {
                        label:'All',
                        icon:'',
                    },
                    {
                        label:'New',
                        icon:'',
                    },
                    {
                        label:'Processing',
                        icon:'',
                    },
                    {
                        label:'Today',
                        icon:'',
                    },
                    {
                        label:'Future',
                        icon:'',
                    },
                    {
                        label:'Unassigned',
                        icon:'',
                    },
                ]
            },
            {
                label:'Admin',
                icon:'',
                children:[
                    {
                        label:'All',
                        icon:'',
                    },
                    {
                        label:'New',
                        icon:'',
                    },
                    {
                        label:'Processing',
                        icon:'',
                    },
                    {
                        label:'Today',
                        icon:'',
                    },
                    {
                        label:'Future',
                        icon:'',
                    },
                    {
                        label:'Unassigned',
                        icon:'',
                    },
                ]
            }
        ]
        }
    },
    methods:{
        toggle(i){
            this.$refs.menugroup.forEach((item, index)=>{
                if(i != index){
                    item.menubarToggle(false);
                }
            });
        }
    }
}
</script>

<template>
    <section class="sidebar--submenu">

        <div class="submenu-header">
        <h1>Platform</h1>
        </div>

        <div class="submenu-body">

        <menu-group ref="menugroup" @click="toggle(index)" v-for="(menu, index) in menus" :key="index" :menu="menu" />

        </div>

    </section>
</template>

<style>
@import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro:400,600');
*{
    font-family: 'Source Sans Pro', sans-serif;
    margin:0px;
    padding:0px;
    box-sizing: border-box;
}
body{
  background:#dddddd;
}
</style>

<style scoped lang="scss">
.sidebar--submenu{
  // position: absolute;
  top:0;
  background-color: #ffffff;
  width: 18rem;
  max-height: 100vh;
  height: 100vh;
  margin-left: 4rem;
  overflow: hidden;
  border-right:1px solid #dddddd;
  position: relative;
  z-index: 999;
  .submenu-header{
    padding: 1.5rem;
    padding-bottom: 0.25rem;
    h1{
        color: #1f2933;
        font-size: 1.5rem;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
        margin-bottom: 1rem;
        font-weight: 600;
    }
  }
}
</style>

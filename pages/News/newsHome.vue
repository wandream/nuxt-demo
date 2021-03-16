<template>
    <div>
        <!-- <h1>Home</h1> -->
        <!-- {{title.damenuta}} -->
        <div>menu
            <a-menu v-model="current" mode="horizontal">
                <a-menu-item v-for="item in title.data" :key="item.id" :tab="item.id">
                    <nuxt-link :to="'/News/newsHome/'+item.id">
                        <a-icon :type="item.icon" />
                        {{item.title}}
                    </nuxt-link>
                </a-menu-item>
            </a-menu>
            <!-- <Detailid :id="getTab()"/> -->
            
        </div>
        <nuxt-child></nuxt-child>
    </div>
</template>
<script>

import axios from "axios";
// import Detailid from '../Detail/_id'
export default {
    // components: {
    //     Detailid
    // },
    data () {
        return {
            tab: 0
        }
    },
    methods: {
        getTab () {
            return this.tab 
        }
    },
    asyncData() {
            return axios.get('http://www.dell-lee.com/react/api/header.json').then(res => {
                // console.log(res.data)
                return {
                    title:res.data
                }
            })
    }
}
</script>

<style scoped>

</style>
<template>
    <div>


        <a-card :title="container.data.title" style="minWidth: 800px">
            <p v-html="container.data.content"></p>
        </a-card>
        <!-- {{$route.params.id}} -->
        <!-- <p>{{container.data.title}}</p>
        <p v-html="container.data.content"></p> -->

    </div>
</template>

<script>
import axios from 'axios'
export default {
    asyncData({params}) {
        return axios.get('http://www.dell-lee.com/react/api/detail.json?id='+params.id).then(res => {
            // console.log(res);
            return {
                container:res.data
            }
        })
    }
}
</script>

<style scoped>

</style>

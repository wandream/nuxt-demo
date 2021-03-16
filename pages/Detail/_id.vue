<template>
    <div>
        <!-- {{$route.params.id}} -->
        <!-- <ul>
            <li v-for="item in list.data" :key="item.id">
                <nuxt-link :to="'/container/'+item.id">
                    {{item.title}}
                </nuxt-link>
            </li>
        </ul> -->
        <a-list bordered :data-source="list.data">
            <a-list-item slot="renderItem" slot-scope="item">
                <nuxt-link :to="'/container/'+item.id">
                    {{item.title}}
                </nuxt-link>
            </a-list-item>
        </a-list>

        <!-- <p>{{list.data}}</p> -->
    </div>
</template>

<script>
import axios from 'axios'
export default {
    asyncData({params}) {
        return axios.get('http://www.dell-lee.com/react/api/list.json?id='+ params.id).then(res => {
            // console.log(res)
            return {
                list: res.data
            }
        })
    },
    head () {
        return {
            title: 'detailPage',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'news detail'
                }
            ]
        }
    }
}
</script>

<style scoped>

</style>
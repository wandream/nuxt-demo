<template>
    <div>
        <h1>router</h1>
        <ul>
            <li>
                <nuxt-link to="/Vrouter/page1">to page1</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/Vrouter/page2">to page2</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/Vrouter/parent/child">to child</nuxt-link>
            </li>
        </ul>
        <nuxt-child></nuxt-child>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>

</style>
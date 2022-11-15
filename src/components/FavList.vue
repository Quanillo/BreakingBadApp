<template>
    <div class="m-5 place-items-center">
        <ul>
            <li v-for="(item, index) in this.favList" :key="index">
                <CharMin :char="item" :favList="favList"  @deleteFav="deleteFav"  @showMaxChar="showMaxChar"/>
            </li>
        </ul>
    </div>
</template>

<script>
import CharMin from "./CharMin.vue";
export default {
    name: 'Fav',
    components: { CharMin },
    props: {
        favList: {
            type: Array,
        },
        maxChar: {
            type: Object,
        },
    },
    emits:["showMaxChar", "deleteFav"],
    methods: {
        deleteFav(char) {
            this.$emit('deleteFav', char);
        },
        showMaxChar(char){
            this.$emit('showMaxChar', char);
        },
    },
}
</script>

<style scoped>

</style>
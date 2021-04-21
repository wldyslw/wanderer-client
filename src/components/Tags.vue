<template>
    <ul class="tags">
        <li class="tag" v-for="tag in tags" :key="tag">
            <router-link :to="`/search?tag=${tag}`">{{ tag }}</router-link>
        </li>
    </ul>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    props: {
        tags: {
            type: Array,
            default: () => ['брестская_область', 'пинский_район', 'полесье'],
        },
    },
});
</script>

<style lang="scss" scoped>
@import '@/styles/vars';

.tags {
    list-style: none;
    padding: 0;
    color: $color-gray-dark;
}

.tag {
    display: inline-block;
    padding: 0 0.5em 0 0;
    font-family: 'Roboto Mono', monospace;
    font-size: smaller;
    color: $color-gray-dark;

    &::before {
        content: '#';
    }
}
</style>

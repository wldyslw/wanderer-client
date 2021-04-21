<template>
    <div class="home">
        <Card
            v-for="_ in [1, 2, 3, 4, 5]"
            :key="_"
            :title="'Пинск'"
            :description="
                'Город в пинском районе брестской области, легендарная столица Полесья и один из самых красивых исторических городов Беларуси'
            "
            :favs="5"
            :slug="'/schuchunshchyna'"
            :dateTime="Date.now()"
        />
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Card from '@/components/Card.vue';

export default defineComponent({
    name: 'Home',
    components: {
        Card,
    },
});
</script>

<style lang="scss" scoped>
.home {
    width: 100%;
    max-width: 800px;
    margin: auto;
}
</style>

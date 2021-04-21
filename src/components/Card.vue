<template>
    <div class="card">
        <div class="text-container">
            <h3 class="title">
                <router-link :to="`/article/${slug}`">{{ title }}</router-link>
            </h3>
            <small>{{ dateTimeFormatted }}</small>
            <p class="description">{{ description }} <a href="https://example.com">link</a> {{ description }}</p>
            <Tags :tags="tags" />
        </div>
        <div
            style="background-image: url('https://34travel.me/media/posts/5d25f589dd576-pinsk-pan.jpg')"
            class="img-container"
        ></div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { CardDateTimeFormatter } from '@/helpers/dateTime';
import Tags from '@/components/Tags.vue';

export default defineComponent({
    props: {
        img: String,
        title: String,
        description: String,
        slug: String,
        favs: Number,
        tags: {
            type: Array,
            default: () => ['брестская_область', 'пинский_район', 'полесье'],
        },
        dateTime: { type: Number, required: true },
    },
    setup(props) {
        return {
            dateTimeFormatted: CardDateTimeFormatter.format(new Date(props.dateTime)),
        };
    },
    components: { Tags },
});
</script>

<style lang="scss" scoped>
@import '@/styles/vars';

.card {
    display: flex;
    margin-bottom: 5em;
}

.img-container {
    height: 225px;
    width: 300px;
    flex-shrink: 0;
    background-position: center center;
    background-repeat: no-repeat;
    background-size: cover;

    border-radius: 5px;
}

.text-container {
    flex-grow: 1;
    padding: 0 1em;
    color: $color-dark;
}

.title a {
    color: $color-primary;
    border-bottom-color: $color-link-primary;
}
</style>

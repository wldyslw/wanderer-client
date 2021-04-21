<template>
    <div id="nav">
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
    </div>
    <router-view />
</template>

<style src="normalize.css/normalize.css"></style>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Roboto&family=Roboto+Condensed&family=Roboto+Mono&display=swap');
@import '@/styles/common';

#nav {
    padding: 30px;

    a {
        font-weight: bold;
        color: #2c3e50;

        &.router-link-exact-active {
            color: #42b983;
        }
    }
}
</style>

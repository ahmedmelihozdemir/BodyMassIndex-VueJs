<template>
    <div>
        <nav>
            <router-link to="/">Home</router-link>
            <router-link to="/about">About</router-link>
        </nav>
        <router-view />
    </div>
</template>

<script></script>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

nav {
    padding: 30px;
    background-color: #158d57bc;
    border-radius: 10px;
    width: 80%;
    margin: auto;
    a {
        font-weight: bold;
        font-size: 20px;
        color: #2c3e50;
        text-decoration: none;
        margin: 20px;
        &:hover {
            padding: 10px;
            border-radius: 5px;
            color: #2c3e50;
            background-color: burlywood;
        }

        &.router-link-exact-active {
            color: #7f42b9;
        }
    }
}
</style>

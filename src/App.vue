<template>
 
 <!--
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
-->
    <header>
        <div class="container">
            <div class="row">
                <a class="logo" href="/">
                    <img src="./assets/images/logo.svg">
                    <p>Womazing</p>
                </a>
                <nav class="navigation">
                    <ul>
                        <li><router-link to="/">Главная</router-link></li>
                        <li><router-link to="/shop">Магазин</router-link></li>
                        <li><router-link to="/about">О бренде</router-link></li>
                        <li><router-link to="/cart">Корзина</router-link></li>
                    </ul>
                </nav>
                <a class="phone" href="tel:+74958235412">
                    <img src="./assets/images/phone.svg">
                    +7 (495) 823-54-12
                </a>
                <a class="basket" href="/" @click.prevent="increment">
                    <img src="./assets/images/basket.svg">
                    <span>{{ this.$store.state.tovarsInBasket.length }}</span>
                </a>
            </div>
        </div>
    </header>
    <router-view/>
    <footer>
        <div class="container">
            <div class="row">
                <p>Project on Github: <a href="/" target="_blank">dmitriyd-web</a></p>
            </div>
        </div>
    </footer>
</template>

<script>
export default {
    beforeMount() {
        const storage = localStorage.getItem("tovarsInBasket")
        if ( storage ) {
            this.$store.commit('getLocalStorage', storage)
        }
    },
    methods: {
        /*
        increment() {
            this.$store.commit('addTovar')
            console.log(this.$store.state.tovasrsInBasket)
        }
        */
    }
}
</script>
<style src="./assets/styles/style.css"></style>
<style>
    
</style>

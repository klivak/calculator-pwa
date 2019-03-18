<template>
    <div id="app">
        <header>
            <h1>Calculator</h1>
        </header>
        <main>
            <calculator></calculator>
        </main>
        <footer>

        </footer>
    </div>
</template>

<script>
    import Calculator from './components/Calculator'

    export default {
        components: {
            Calculator
        }
    }
</script>

<style>
    @import "assets/scss/main.scss";
</style>

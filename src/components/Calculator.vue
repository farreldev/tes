<template>
    <div class="calculator">
        <div class="content-calculator">
            <h1>Calculator Biasa</h1>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Calculator',
    methods: {
        tambah() {
        },
        kurang() {
        },
        kali() {
        },
        bagi() {
        }
    }
}
</script>

<style lang="scss">
.calculator {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgb(75, 188, 216);
    .content-calculator {
        padding: 20px;
        border-radius: 5px;
        min-width: 300px;
        min-height: 400px;
        background-color: white;
        h1 {
            text-align: center;
        }
    }
}
</style>
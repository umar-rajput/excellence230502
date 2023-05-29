<template>
    <div class="CCard">
        <Card>
            <template v-slot:header>
                <img src="../assets/beautiful-nature-g3b2484d98_1280.jpg" alt="Tree image" style="height:140px; width:100%">
            </template>
            <template v-slot:title>
                <h3>Card Title</h3>
            </template>
            <template v-slot:body>
                <p>
                    Some quick example text to build on the card
                    title and make up the bulk of card's content.
                </p>
            </template>
            <template v-slot:footer>
                <button class="btn">Go somewhere</button>
            </template>
        </Card>
    </div>
</template>

<script>

import Card from './Card.vue'

export default ({
    name: 'CCard',
    components: { Card },
    data() {

    },
})
</script>

<style scoped>
.CCard {
    display: flex;
    justify-content: center;
}

.btn {
    background: #007bff;
    color: #fff;
    padding: 8px 10px;
    border-radius: 5px;
    border: none;
}
</style>

<template>
    <div class="Card">
        <header>
            <div class="header">
                <slot name="header" />
            </div>
        </header>
        <div class="main">
            <section>
                <div class="title">
                    <slot name="title" />
                </div>
            </section>
            <section>
                <div class="body">
                    <slot name="body" />
                </div>
            </section>
            <footer>
                <div class="footer">
                    <slot name="footer" />
                </div>
            </footer>
        </div>
    </div>
</template>

<script>

export default ({
    name: `Card`,
    data() {

    },
})
</script>

<style scoped>
.Card {
    height: 335px;
    width: 260px;
    border: 1px solid #0000001f;
    border-radius: 3px;
}

.main {
    text-align: left;
    padding: 10px;
}
</style>

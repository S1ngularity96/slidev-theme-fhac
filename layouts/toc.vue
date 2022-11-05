<template>
    <div class="fhlayout toc">
        <div class="headline">
            <h2><strong>{{ header }}</strong></h2>
            <h3><strong>{{ subheader }}</strong></h3>
        </div>
        <main>
            <slot></slot>
        </main>
    </div>
</template>

<script>
export default {
    props: {
        header: String,
        subheader: String
    },
    mounted() {
        console.log(this.header)
    }
}
</script>
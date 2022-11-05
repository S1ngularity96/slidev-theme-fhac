<template>
    <div class="fhlayout two-cols">
        <div class="headline">
            <h2><strong>{{ header }}</strong></h2>
            <h3><strong>{{ subheader }}</strong></h3>
        </div>
        <main>
            <div class="two-cols--left">
                <slot></slot>
            </div>
            <div class="two-cols--right">
                <slot name="right"></slot>
            </div>
        </main>

    </div>
</template>

<script>
export default {
    props: {
        header: String,
        subheader: String
    }
}
</script>
<template>
    <footer class="fhlayout" v-if="showIf">
        <div class="content">
            <p><strong>&copy; FH AACHEN</strong><span> UNIVERSITY OF APPLIED SCIENCES</span></p>
            <p>{{ date }} | {{ this.$slidev.nav.currentPage }} </p>
        </div>
    </footer>
</template>

<script>
export default {

    computed: {
        showIf() {
            return true;
        },
        date() {
            if (typeof this.$slidev.configs.date !== 'undefined') {
                return this.$slidev.configs.date;
            }
            let date = new Date();
            return `${date.getDay()}. ${date.getUTCMonth()} ${date.getFullYear()}`
        },
    }
}
</script>
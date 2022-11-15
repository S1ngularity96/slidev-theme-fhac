<template>
    <footer class="fhlayout" v-if="showIf">
        <div :class="{ 'content': true, 'content--isCover': isCover }">
            <p><strong>&copy; FH AACHEN</strong><span> UNIVERSITY OF APPLIED SCIENCES</span></p>
            <p v-if="isCover">Fachbereich {{ this.$slidev.configs.faculty }}</p>
            <p><a v-if="isCover" href="http://www.fh-aachen.de">www.fh-aachen.de</a></p>
            <p v-if="!isCover">{{ date }} | {{ this.$slidev.nav.currentPage }} </p>
        </div>
    </footer>
</template>

<script>
export default {

    computed: {
        showIf() {
            let layout = this.$slidev.nav.currentLayout;
            return layout !== 'end';
        },
        isCover(){
            return this.$slidev.nav.currentLayout === 'cover'
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
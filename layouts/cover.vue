<template>
    <div class="fhlayout cover">
        <main>
            <h1>{{ title }}</h1>
            <h2>{{ subtitle }}</h2>
            <br>
            <h4>{{ referent }}</h4>
            <h4>{{ date }}</h4>
        </main>
    </div>
</template>

<script>
export default {
    computed:{
        title(){
            return typeof this.$slidev.configs.title !== 'undefined' ? this.$slidev.configs.title : "Titel";
        },
        subtitle(){
            return typeof this.$slidev.configs.subtitle !== 'undefined' ? this.$slidev.configs.subtitle : "";
        },
        referent() {
            return typeof this.$slidev.configs.referent !== 'undefined' ? this.$slidev.configs.referent : "Vorname Nachname";
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
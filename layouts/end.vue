<template>
    <div class="fhlayout end">
            <p>FH Aachen</p>
            <p>Fachbereich {{ faculty }}</p>
            <br>
            <p>{{ referent }}</p>
            <p>{{ studentnr }}</p>
            <a :href="`mailto:${email}`">{{email}}</a>
            <br>
            <a href="http://www.fh-aachen.de">www.fh-aachen.de</a>
    </div>
</template>

<script>
export default {
    computed: {
        faculty() {
            return typeof this.$slidev.configs.faculty !== 'undefined' ? this.$slidev.configs.faculty : "";
        },
        referent() {
            return typeof this.$slidev.configs.referent !== 'undefined' ? this.$slidev.configs.referent : "Vorname Nachname";
        },
        studentnr() {
            return typeof this.$slidev.configs.studentnr !== 'undefined' ? this.$slidev.configs.studentnr : "Matrikel-Nr."
        },
        email() {
            return typeof this.$slidev.configs.email !== 'undefined' ? this.$slidev.configs.email : "E-Mail Adresse"
        }
    }
}
</script>
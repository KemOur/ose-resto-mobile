<template>
    <ion-header >
        <ion-toolbar>
            <ion-title>
                <a href="/" style="text-decoration: none; color: grey">Affluences</a>
            </ion-title>
        </ion-toolbar>
    </ion-header>
</template>

<script>
    import {IonHeader, IonToolbar, IonTitle} from "@ionic/vue";

    export default {
        name: "Header",
        components: {
            IonHeader,
            IonToolbar,
            IonTitle,
        }
    }
</script>

<style scoped>

</style>
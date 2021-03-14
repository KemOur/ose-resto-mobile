<template>

    <ion-page>
    <Header />

        <ion-content>
            <div id="container">
                <br>
                <h1 class="h2"><strong>Bon appetit</strong></h1>
                <small> Ce petit restaurant aux lignes modernes offre des recettes africaines sur place et à emporter.</small>
                <br>
                <br>
                <ReservationComponents />
                <br>
                <br>
                <Footer />

            </div>
        </ion-content>
    </ion-page>
</template>

<script>
    import ReservationComponents from "../components/ReservationComponents";
    import Header from "../components/Header";
    import Footer from "../components/Footer";
    import { IonContent, IonPage } from '@ionic/vue';
    import { defineComponent } from 'vue';
    export default defineComponent({
        name: 'Reservation',
        components: {
            Header,
            ReservationComponents,
            Footer,
            IonContent,
            IonPage,
        },

        data () {
            return {
                errors: [],
                date: '',
                heure: '',
                emails: '',
                api_token: 'ihezeodjerzkld'

            };
        },

        methods: {

            Reserver: function (e) {

                this.errors = [];

                if (!this.date) {
                    this.errors.push("Date Invalide");
                }

                if (!this.heure) {
                    this.errors.push("Heure Invalide");
                }

                else if (this.validEmail(!this.emails)){
                    this.errors.push('Email Invalide')
                }

                if (!this.errors.length){
                    return true;
                }

                e.preventDefault()

            },
            validEmail: function (emails){
                let re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
                return re.test(emails);
            }

        }
    });

</script>

<style scoped>
    body {
        font-family: 'Nunito';
    }

    .h2{
        text-align: center;
    }
    #container {
        text-align: center;
        position: absolute;
        left: 15px;
        right: 15px;
    }

    #container strong {
        font-size: 20px;
        line-height: 26px;
    }

    #container p {
        font-size: 16px;
        line-height: 22px;
        color: #8c8c8c;
        margin: 0;
    }

    #container a {
        text-decoration: none;
    }
</style>
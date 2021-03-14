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
                <form @submit="Reserver" method="post" action="http://ose-resto.herokuapp.com/api/reservation">
                    <input type="hidden" value="api_token" name="api_token">


                    <label for="date" class="form-label">Date</label>
                    <input type="date" class="form-control" id="date" name="date" v-model="date" min="2021-02-21">

                    <div class="my-3">
                        <label for="heure" class="form-label">Heure</label>
                        <input type="time" id="heure" class="form-control" name="heure" v-model="heure" min="09:00" max="18:00" step="3600" >
                    </div>
                    <div class="my-3">
                        <label for="emails" class="form-label">Votre adresse e-mail</label>
                        <input type="email" class="form-control" id="emails" name="emails" v-model="emails" placeholder="ose@gmail.com">
                    </div>

                    <div class="form-check mt-4">
                        <input class="form-check-input" type="checkbox" id="cgu" name="cgu">
                        <label class="form-check-label" for="cgu">
                            J'ai lu et accepté les <a href="#">conditions d'utilisation</a>
                        </label>
                    </div>

                    <div class=" d-grid gap-2 mt-4">
                        <button type="submit" class="btn btn-primary">Réserver</button>
                        <a href="/" class="btn btn-light" type="button">Retour</a>
                    </div>

                </form>                <br>

                <br>
                <Footer />

            </div>
        </ion-content>
    </ion-page>
</template>

<script>
    import Header from "../components/Header";
    import Footer from "../components/Footer";
    import { IonContent, IonPage } from '@ionic/vue';
    import { defineComponent } from 'vue';
    export default defineComponent({
        name: 'Reservation',
        components: {
            Header,
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
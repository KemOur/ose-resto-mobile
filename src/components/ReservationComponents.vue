<template>
    <div class="card">
        <div class="card-body">
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

            </form>

        </div>
    </div>
</template>

<script>
    export default {
        name: "ReservationComponents",
    }

</script>

<style scoped>

</style>
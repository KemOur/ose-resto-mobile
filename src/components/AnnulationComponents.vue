<template>
    <div class="lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2">
        <form method="POST">
            <input type="hidden" name="_token" value="4KdJVr1RHZUyomA9BR38HLYof3Y7OWcsDdRK1rOn">    <div class="row justify-content-center">
                <div class="container mt-5">
                    <div class="row justify-content-center">
                        <div class="col-sm-8">
                            <br>
                            <div class="card">
                              <div class="card-body">
                                <h1 class="card-title text-center mb-4">Annuler ma réservation ❌ </h1>
                                   <p class="card-text text-center"> je souhaite annuler ma réservation !</p>
                                        <div class="d-grid gap-2 mt-4">
                                        <button class="btn btn-outline-danger" type="submit">Annuler la réservation</button>
                                        <a href="/reservation" class="btn btn-light" type="button">Retour</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
     </form>
</div>
</template>

<script>
    export default {
        name: "AnnulationComponents"
    }
</script>

<style scoped>

</style>
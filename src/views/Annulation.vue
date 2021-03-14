<template>
    <Header />

  <div id="container">
    <div class="max-w-7xl mx-auto">
        <div class="relative z-10 pb-8 bg-white sm:pb-16 md:pb-20 lg:max-w-2xl lg:w-full lg:pb-28 xl:pb-32">
            <main class="mt-8 mx-auto max-w-7xl">
                <div class="sm:text-center lg:text-left">
                    <h1 class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl">
                        <span class="block text-indigo-600 xl:inline">À bientôt</span>
                    </h1>
                    <p class="mt-3 text-base text-gray-500 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0">
                        Merci de nous rendre visite dès que possible, nous vous recevrons à nouveau avec plaisir , Osé </p>
                </div>
            </main>
        </div>
    </div>
      <AnnulationComponents />
        <br>
        <br>
      <Footer />
  </div>
</template>

<script>
    import AnnulationComponents from "../components/AnnulationComponents";
    import Footer from "../components/Footer";
    import Header from "../components/Header";
    export default {
        name: "Annulation",
        components: {
            Header,
            Footer,
            AnnulationComponents,
        },

        setup () {

        }
    }
</script>

<style scoped>

    body {
        font-family: 'Nunito';
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
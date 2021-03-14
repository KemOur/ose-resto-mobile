<template>
  <ion-page>
    <Header />
      <ion-content>
      <ion-img src="/assets/img/Ose_Food-mobile.jpg"/>
      <div id="container">
      <h1 class="h1">{{info.name}}</h1>
        <h2 class="h2"><strong>{{info.surname}}</strong></h2>
      <p>{{info.description}}</p><br>
        <strong>Pour plus d'information</strong><br><small>{{info.email}}</small>
          <ion-button href="/reservation" type="submit" expand="block" color="primary">Réserver</ion-button>
        <h1>Horaires</h1>

        <div class="table-responsive">
          <table class="table">
            <thead>
            <tr>
              <th scope="col">Lun</th>
              <th scope="col">Mar</th>
              <th scope="col">Mer</th>
              <th scope="col">Jeu</th>
              <th scope="col">Ven</th>
              <th scope="col">Sam</th>
              <th scope="col">Dim</th>
            </tr>
            </thead>
            <tbody>
            <tr>
              <td>9h - 18h</td>
              <td>9h - 18h</td>
              <td>9h - 18h</td>
              <td>9h - 18h</td>
              <td>9h - 18h</td>
              <td class="text-muted"><em>Fermé</em></td>
              <td class="text-muted"><em>Fermé</em></td>
            </tr>
            </tbody>
          </table>
        </div>

        <Footer />

      </div>
    </ion-content>
  </ion-page>
</template>

<script>
  import Header from "@/components/Header";
  import Footer from "@/components/Footer";
  import { IonContent, IonPage, IonImg, IonButton } from '@ionic/vue';
  import { defineComponent } from 'vue';
  import axios from "axios";

  export default defineComponent({
    name: 'Home',
    components: {
        Footer,
        Header,
        IonContent,
        IonButton,
        IonImg,
        IonPage,
    },

    data () {
      return {
            info: ''
      }
    },

    mounted () {
      axios
              .get(`http://ose-resto.herokuapp.com/api/infos`)
              .then(( response) => {
                response.data
                this.info = response.data
                console.log(this.info)
              });
    }
  });
</script>

<style scoped>

  .table {
    --bs-table-bg: transparent;
    --bs-table-striped-color: #212529;
    --bs-table-striped-bg: rgba(0, 0, 0, 0.05);
    --bs-table-active-color: #212529;
    --bs-table-active-bg: rgba(0, 0, 0, 0.1);
    --bs-table-hover-color: #212529;
    --bs-table-hover-bg: rgba(0, 0, 0, 0.075);
    width: 100%;
    margin-bottom: 1rem;
    color: #212529;
    vertical-align: top;
    border-color: #dee2e6;
  }

  .table-responsive {
    overflow-x: auto;
  }

  .h1, .h2{
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
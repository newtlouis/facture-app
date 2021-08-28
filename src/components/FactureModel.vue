<template>
    <div @click="checkClick" class="facture">
        <form @submit.prevent="sendFacture">
            <h1>Nouvelle Facture:</h1>
            <!-- FROM -->
            <div class="from">
                <h3>Facture de:</h3>
                <div class="input">
                    <label for="billerAdress">Adresse</label>
                    <input id="billerAdress" v-model="billerAdress" required type="text">
                </div>
                <div class="locationDetail">
                    <div class="input">
                        <label for="billerCity">Ville</label>
                        <input id="billerCity" v-model="billerCity" required type="text">
                    </div>
                    <div class="input">
                         <label for="billerCP">Code Postal</label>
                        <input id="billerCP" v-model="billerCP" required type="text">
                    </div>
                    <div class="input">
                         <label for="billerCountry">Pays</label>
                         <input id="billerCountry" v-model="billerCountry" required type="text">
                    </div>
                </div>
            </div>
            <!-- TO -->
            <div class="to">
                <h3>Destinataire</h3>
                <div class="input">
                    <label for="clientName">Name</label>
                    <input id="clientName" v-model="clientName" required type="text">
                </div>
                <div class="input">
                    <label for="clientAdress">Adresse</label>
                    <input id="clientAdress" v-model="clientAdress" required type="text">
                </div>
                <div class="input">
                    <label for="clientEmail">Email</label>
                    <input id="clientEmail" v-model="clientEmail" required type="text">
                </div>

                <div class="locationDetail">
                    <div class="input">
                        <label for="clientCity">Ville</label>
                        <input id="clientCity" v-model="clientCity" required type="text">
                    </div>
                    <div class="input">
                         <label for="clientCP">Code Postal</label>
                        <input id="clientCP" v-model="clientCP" required type="text">
                    </div>
                    <div class="input">
                         <label for="clientCountry">Pays</label>
                         <input id="clientCountry" v-model="clientCountry" required type="text">
                    </div>
                </div>

            </div>

            <!-- Facture details -->
            <div class="facture__detail">
                <div class="input">
                    <label for="factureDate">Date de facture</label>
                    <input id="factureDate" v-model="factureDate" disabled type="text">
                </div>
                <div class="input">
                    <label for="paymentDueDate">Date butoire</label>
                    <input id="paymentDueDate" v-model="paymentDueDate" disabled type="text">
                </div>
                <div class="input">
                    <label for="productDescription">Description</label>
                    <input id="productDescription" v-model="productDescription" disabled type="text">
                </div>

                <h3>Liste des produits</h3>
                <table>
                    <tr class="table__heading">
                        <th class="designation">Designation</th>
                        <th class="qty">Quantité</th>
                        <th class="price">Prix</th>
                        <th class="total">Total</th>
                    </tr>
                    <tr class="talbe__item" v-for="(item, index) in factureList" :key="index">
                        <td class="designation"><input v-model="item.Designation" type="text"></td>
                        <td class="qty"><input v-model="item.qty" type="text"></td>
                        <td class="price"><input v-model="item.price" type="text"></td>
                        <td class="total">${{(item.total = item.qty * item.price) }}</td>
                        <div class="deleteInvoiceItem" @click="deleteFactureItem(item.id)">x</div>
                    </tr>
                </table>
                <div class="newItem" @click="addNewFactureItem">Ajouter un nouveau produit</div>
            </div>

            <!-- Save/Exit -->
            <div class="save">
                <button @click="closeFacture" class="closeFacture">Annuler</button>
                <div class="save__right">
                    <button class="save__draft">Enregister brouillon</button>
                    <button class="save__facture">Enregister facture</button>
                </div>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name:"factureModel",
    data(){
        return{
            billerAdress: null,
            billerCity: null,
            billerCP: null,
            billerCountry: null,
            clientName: null,
            clientEmail: null,
            clientAdress: null,
            clientCity: null,
            clientCP: null,
            clientCountry: null,
            factureDate: null,
            facturePending: null,
            factureDraft: null,
            factureList: [],
            factureTotal: 0,
            paymentDueDate: null,
            productDescription: null,


        }
    }

}
</script>
<template>
  <div class="col-xs-12 col-sm-6 col-lg-3 mb-2">
      <b-card style="border-radius: 7px;" class="item">
          <div v-if="itemData.sale" pill class="sale-badge"><strong>SALE</strong></div>
          <router-link :to="'/details/'+itemData.id"><img :src="itemData.image" alt="" width="100%"></router-link>
          <span class="name">
              <strong><router-link :to="'/details/'+itemData.id" class="no-link">{{ itemData.name }}</router-link> - </strong><span>{{ data.unit }}</span>
          </span>
          <span class="price"><strong>Rs. {{ itemData.price }}</strong></span>
          <div class="d-flex save-btn">
              <i v-if="itemData.saved" class="fas fa-bookmark ml-auto" @click="removeFromSaved"></i>
              <i v-else class="far fa-bookmark ml-auto" @click="makeSaved"></i>
          </div>
      </b-card>
  </div>
</template>

<script>
export default {
    name: 'Item',
    props:{
        data:{
            id:Number,
            sale: Boolean,
            name: String,
            price: String,
            unit: String,
            image: String,
            saved: Boolean
        }
    },
    data(){
        return{
            amount: 1,
            itemData: {}
        }
    },
    created(){
        this.itemData = this.data
    },
    methods:{
        removeFromSaved: function(){
            this.itemData.saved = !this.itemData.saved;
            console.log('unsave');
        },
        makeSaved: function(){
            this.itemData.saved = !this.itemData.saved;
            console.log('save');
        }
    }
}
</script>

<style scoped>
/* Global css */
@import url('../assets/css/styles.css');
.no-link{
    color: #343f49;
}

.item{
    transition: 0.1s;
    position: relative;
}
.item:hover{
    box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.473);
}

.sale-badge{
    width: fit-content;
    border-radius: 50px;
    background: #fed700;
    color: #343f49;
    padding: 0rem 0.5rem;
}
.sale-badge strong{
    font-size: 0.75rem;
    text-transform: uppercase;
    font-weight: 800;
}
.name{
    display: block;
}
.name strong:hover{
    text-decoration: underline;
}
.name strong{
    font-size: 1.2rem;
}
.price{
    display: block;
}
.price strong{
    font-size: 1.1rem;
    color: rgb(107, 107, 107);
}

.save-btn i{
    background: rgba(219, 219, 219, 0.452);
    width: 1.7rem;
    height: 1.7rem;
    display: grid;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    cursor: pointer;
    transition: 0.1s;
}
.save-btn i:hover{
    box-shadow: 1px 1px 7px black;
}
</style>
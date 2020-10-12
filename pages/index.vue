<template>
  <div>
    <v-carousel
      hide-delimiter-background
      delimiter-icon="remove"
      :show-arrows="false"
      cycle
      height="704px"
      class="slider hidden-sm-and-down"
    >
      <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src">
      </v-carousel-item>
    </v-carousel>
    <div class="overlay">
      <v-container fill-height>
        <v-layout row wrap justify-cente align-center>
          <v-flex md5>
            <v-card class="hero-card" :class="{'pa-12' : $vuetify.breakpoint.mdAndUp, 'pa-4' : $vuetify.breakpoint.smAndDown, 'pr-16' : $vuetify.breakpoint.mdAndUp}" flat>
              <h2>Explore our Showroom</h2>
              <p :class="{'mt-8' : $vuetify.breakpoint.mdAndUp, 'mt-4' : $vuetify.breakpoint.smAndDown}">
                Not sure of what you’re looking for? No worries,<br class="hidden-md-and-up"> use
                <em class="orange--text"> Lighting Xplorer</em> to see what you
                can get.
              </p>
              <v-btn class="cta"  :class="{'mt-8' : $vuetify.breakpoint.mdAndUp, 'mt-4' : $vuetify.breakpoint.smAndDown}" x-large>
                Proceed to Lighting Xplorer
                <img
                  src="../static/assets/arrow-right.svg"
                  class="ml-4"
                  alt=""
                />
              </v-btn>
            <v-divider  class="mt-8 orange hidden-md-and-up"></v-divider>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </div>
    <v-container class="space" :class="{'py-10' : $vuetify.breakpoint.mdAndUp}">
      <h5>Shop By Space <span class="ml-8" :class="{'text-right' : $vuetify.breakpoint.smAndDown}">View All</span></h5>
      <p>Select the type of apartment you want to light up.</p>
      <v-row align-content="bottom">
        <v-col cols="4">
          <v-img class="space-img" :src="require('../static/assets/1.png')">
            <v-card flat class="btn pa-3 orange--text white hidden-sm-and-down">HOME </v-card>
          </v-img>
          <p class="hidden-md-and-up"><b>Home</b></p>
        </v-col>
        <v-col cols="4">
          <v-img class="space-img" :src="require('../static/assets/2.png')">
            <v-card flat class="btn pa-3 orange--text white hidden-sm-and-down">OFFICE </v-card>
          </v-img>
          <p class="hidden-md-and-up"><b>Office</b></p>
        </v-col>
        <v-col cols="4">
          <v-img class="space-img" :src="require('../static/assets/2.png')">
            <v-card flat class="btn pa-3 orange--text white hidden-sm-and-down">HOTEL </v-card>
          </v-img>
          <p class="hidden-md-and-up"><b>Hotel</b></p>
        </v-col>
      </v-row>
    </v-container>
    <v-container fluid :class="{'space2' : $vuetify.breakpoint.mdAndUp, 'pr-0' : $vuetify.breakpoint.mdAndUp}" class="space py-1">
      <h5>Popular Categories <span :class="{'ml-8' :$vuetify.breakpoint.mdAndUp}">View all</span></h5>
      <v-row>
        <v-col md="7" sm="6" xs="6">
          <v-img
            class="space-img"
            height="496"
            :src="require('../static/assets/4.png')"
          >
            <v-card
              flat
              class="btn pa-4 orange--text white"
              style="width: 279px"
              >CEILING LAMPS
            </v-card>
          </v-img>
        </v-col>
        <v-col md="5" sm="6" xs="6">
          <v-carousel
            hide-delimiter
            hide-delimiters
            :show-arrows="false"
            cycle
            height="496"
            class="slider space-img"
          >
            <v-carousel-item
              v-for="(item, i) in items2"
              :key="i"
              :src="item.src"
            >
              <v-card
                flat
                class="btn pa-4 orange--text white"
                style="width: 279px"
                >CHANDELIERS
              </v-card>
            </v-carousel-item>
          </v-carousel>
          <div class="text-right">
            <v-btn text>
              <v-icon>fas fa-arrow-left</v-icon>
            </v-btn>
            <v-btn text>
              <v-icon>fas fa-arrow-right</v-icon>
            </v-btn>
          </div>
        </v-col>
      </v-row>
    </v-container>
    <v-container py-8>
      <v-card class="products-card">
        <div class="space pa-6" :class="{'px-12' : $vuetify.breakpoint.mdAndUp}">
          <h5>Popular Products <span class="ml-8">View All</span></h5>
        </div>
        <v-divider></v-divider>
        <v-row class="px-4 mt-2" :class="{'px-12' : $vuetify.breakpoint.mdAndUp}">
          <v-col md="3" sm="6" v-for="(i, index) in products" :key="index">
            <v-img :src="i.image">
              <v-chip class="discount pa-3 mt-7" v-if="i.discount">
                {{ i.discount }}
              </v-chip>
            </v-img>
            <p class="product-title mt-8">
              {{ i.title }}
            </p>
            <p class="product-price">{{ i.price }}</p>
          </v-col>
        </v-row>
      </v-card>

      <v-card class="products-card mt-16">
        <div class="space pa-6 px-12">
          <h5>Products on Sale</h5>
        </div>
        <v-divider></v-divider>
        <v-row class="px-12 mt-2">
          <v-col md="3" v-for="(i, index) in products" :key="index">
            <v-img :src="i.image">
              <v-chip class="discount pa-3 mt-7" v-if="i.discount">
                {{ i.discount }}
              </v-chip>
            </v-img>
            <p class="product-title mt-8">
              {{ i.title }}
            </p>
            <p class="product-price">{{ i.price }}</p>
          </v-col>
        </v-row>
      </v-card>

      <v-card color="#F2F2F2" flat class="mt-16 mailing">
        <v-layout row wrap px-4>
          <v-flex md6 pa-8>
            <v-row>
              <v-col cols="1">
                <img src="../static/assets/mail2.svg" alt="" />
              </v-col>
              <v-col class="pl-6 pt-4">
                <h5 class="title">Join our mailing list</h5>
              </v-col>
            </v-row>
            <p class="sub-title">
              Subscribe to our newsletter to get<br />
              updates on our latest offers!
            </p>
            <v-text-field label="Enter email address here" style="width: 60%">
            </v-text-field>
            <v-btn class="cta" x-large> Subscribe </v-btn>
          </v-flex>
          <v-flex md6>
            <v-img :src="require('../static/assets/mailing.svg')"> </v-img>
          </v-flex>
        </v-layout>
      </v-card>
    </v-container>

  </div>
</template>
<script>
export default {
  data() {
    return {
      valid: true,
      items: [
        {
          src: require('../static/assets/banner.png'),
        },
        {
          src: require('../static/assets/banner.png'),
        },
        {
          src: require('../static/assets/banner.png'),
        },
      ],
      items2: [
        {
          src: require('../static/assets/5.png'),
        },
        {
          src: require('../static/assets/2.png'),
        },
        {
          src: require('../static/assets/3.png'),
        },
        {
          src: require('../static/assets/4.png'),
        },
        {
          src: require('../static/assets/1.png'),
        },
      ],
      products: [
        {
          image: require('../static/assets/a.png'),
          title: 'Standing Lamp',
          price: 'N45,000',
        },
        {
          image: require('../static/assets/b.png'),
          title: 'Wooden Chandelier',
          price: 'N45,000',
          discount: '10% OFF',
        },
        {
          image: require('../static/assets/c.png'),
          title: 'Pendant Lamp',
          price: 'N15,000',
        },
        {
          image: require('../static/assets/a.png'),
          title: 'Standing Lamp',
          price: 'N425,000',
        },
        {
          image: require('../static/assets/a.png'),
          title: 'Standing Lamp',
          price: 'N45,000',
        },
        {
          image: require('../static/assets/a.png'),
          title: 'Standing Lamp',
          price: 'N45,000',
        },
        {
          image: require('../static/assets/c.png'),
          title: 'Pendant Lamp',
          price: 'N15,000',
        },
        {
          image: require('../static/assets/b.png'),
          title: 'Wooden Chandelier',
          price: 'N45,000',
          discount: '10% OFF',
        },
      ],
    }
  },
}
</script>
<style lang="scss" scoped>
.slider {
  position: absolute;
}
.overlay {
  height: 704px;
}
.hero-card {
  border-radius: 5px !important;
  h2 {
    font-family: Poppins !important;
    font-style: normal;
    font-weight: 600;
    font-size: 24px;
    line-height: 120%;
    /* or 29px */

    color: #000000;
  }
  p {
    font-family: Poppins !important;
    font-style: normal;
    font-weight: normal;
    font-size: 18px;
    line-height: 27px;

    color: #000000;
  }
  .cta {
    background: #000000 !important;
    border: 1px solid #000000 !important;
    box-sizing: border-box;
    border-radius: 5px !important;
    color: #f2f2f2 !important;
    font-size: 14px !important;
  }
}
.space2 {
  padding-left: 9.5%;
}
.space {
  h5 {
    font-family: Poppins !important;
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 120%;
    /* or 24px */

    display: flex;
    align-items: center;

    color: #000000;
    span {
      font-family: Poppins !important;
      font-style: normal;
      font-weight: normal;
      font-size: 14px;
      line-height: 120%;
      /* or 17px */

      display: flex;
      align-items: center;
      text-decoration-line: underline;

      /* TLH ORANGE */

      color: #f4811f;
    }
  }
  p {
    font-family: Poppins !important;
    font-style: normal;
    font-weight: 300;
    font-size: 18px;
    line-height: 27px;
    display: flex;
    align-items: center;

    color: #000000;
  }
}
.space-img {
  position: relative;
}
.btn {
  font-family: Poppins !important;
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  width: 159px;
  line-height: 120%;
  /* or 19px */

  display: flex;
  align-items: center;

  /* TLH ORANGE */

  color: #f4811f;
  position: absolute;
  bottom: 0;
  margin-bottom: 30px !important;
  margin-left: 30px !important;
}
.products-card {
  background: #ffffff;
  box-shadow: 0px 24px 44px rgba(0, 0, 0, 0.1) !important;
  border-radius: 5px !important;
}
.product-title {
  font-family: Poppins !important;
  font-style: normal;
  font-weight: normal;
  font-size: 12px;
  line-height: 120%;
  display: flex;
  align-items: center;

  color: #000000;
}
.product-price {
  font-family: Poppins !important;
  font-style: normal;
  font-weight: 600;
  font-size: 14px;
  line-height: 120%;
  /* or 17px */

  display: flex;
  align-items: center;

  color: #000000;
}
.discount {
  font-family: Poppins !important;
  font-style: normal;
  font-weight: 500;
  font-size: 19px;
  line-height: 120%;
  /* or 23px */

  display: flex;
  align-items: center;

  color: #ffffff !important;
  background: #000 !important;
  width: 101px !important;
  height: 43px;
  border-radius: 0 !important;
}
.mailing {
  .title {
    font-family: Poppins !important;
    font-style: normal;
    font-weight: 600;
    font-size: 18px;
    line-height: 120%;
    /* or 22px */

    // display: flex;
    // align-items: center;

    color: #000000;
  }
  .sub-title {
    font-family: Poppins !important;
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    line-height: 21px;

    color: #000000;
  }
  .cta {
    background: #000000 !important;
    border: 1px solid #000000 !important;
    box-sizing: border-box;
    border-radius: 5px !important;
    color: #f2f2f2 !important;
    font-size: 14px !important;
  }
}
@media only screen and (max-width: 768px){
  .overlay{
    height: auto !important;
  }
  .hero-card{
    h2{
      font-size: 18px;
    }
    p{
      font-size: 14px;
    }
  }
  .space{
    h5{
      font-size: 18px;
    }
    p{
      font-size: 14px;
    }
  }
  .space-img{
    height: 129px;
    border-radius: 5px;
  }
}
</style>

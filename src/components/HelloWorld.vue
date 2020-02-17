<template>
  <div>
    <!--ViewWrapper-->
    <mdb-view>
      <mdb-mask class="gradient d-flex justify-content-center align-items-center">
        <mdb-container>
          <mdb-row>
              <div class="white-text text-center text-md-left col-md-6 mt-xl-5 mb-5 animated fadeInLeft">
                <h1 class="h1-responsive font-weight-bold mt-sm-5">Make purchases with our app </h1>
                <hr class="hr-light"/>
                <h6 class="mb-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Rem repellendus quasi fuga nesciunt
                dolorum nulla magnam veniam sapiente, fugiat! Commodi sequi non animi ea dolor molestiae
                iste.</h6>
                <mdb-btn color="white">Download</mdb-btn>
                <mdb-btn outline="white">Learn More</mdb-btn>
              </div>
            <mdb-col md="6" xl="5" class="mt-xl-5 animated fadeInRight">
              <img src="https://picsum.photos/300/200?random" class="img-fluid"/>
            </mdb-col>
          </mdb-row>
        </mdb-container>
      </mdb-mask>
    </mdb-view>
    <!--/.ViewWrapper-->

    <mdb-container>
      <mdb-row class="py-5">
        <col md="12" class="text-center">
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
          </p>
      </mdb-row>
    </mdb-container>
  </div>
</template>

<script>
  import { mdbContainer, mdbRow, mdbCol, mdbView, mdbMask, mdbBtn } from 'mdbvue';
  export default {
    name: 'AppPage',
    components: {
      mdbContainer,
      mdbRow,
      mdbCol,
      mdbView,
      mdbMask,
      mdbBtn
    }
  }
</script>

<style>
  .navbar .md-form {
    margin: 0;
  }
  .top-nav-collapse {
    background-color: #424f95 !important;
  }
  @media (max-width: 990px){
    .navbar {
      background-color: #424f95 !important;
    }
  }
  .view {
    background-image: url('https://picsum.photos/1920/1080?random');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center center;
    height: calc(100vh - 60px);
  }
  .gradient {
    background: -moz-linear-gradient(45deg, rgba(42, 27, 161, 0.7), rgba(29, 210, 177, 0.7) 100%);
    background: -webkit-linear-gradient(45deg, rgba(42, 27, 161, 0.7), rgba(29, 210, 177, 0.7) 100%);
    background: -webkit-gradient(linear, 45deg, from(rgba(42, 27, 161, 0.7)), to(rgba(29, 210, 177, 0.7)));
    background: -o-linear-gradient(45deg, rgba(42, 27, 161, 0.7), rgba(29, 210, 177, 0.7) 100%);
    background: linear-gradient(45deg, rgba(42, 27, 161, 0.7), rgba(29, 210, 177, 0.7) 100%);
  }
  h6 {
    line-height: 1.7;
  }
</style>


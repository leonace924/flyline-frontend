<template>
  <div>
    <div class="page page--how-it-works page page--landing page--landing--web">
      <Navbar />
      <div class="full-width landing__wrapper landing__wrapper--1">
        <div class="terms__section">
          <div class="terms__title">FlyLine Terms of Use</div>
          <p class="terms__subtitle">
            Questions about our terms? Send us an email to hello@flyline.io
          </p>
          <hr />
          <div class="terms__content" id="scrollbar">
            <p>
              FlyLine, Inc., a Delaware corporation, doing business as Flyline
              (“Flyline”) operates the Flyline.com and Wanderift.com websites
              (“Sites”), the Flyline mobile application (“App”), and the travel
              booking membership services offered through our Sites and App
              (together with the App and the Sites, the “Services”).
            </p>
            <p>
              Flyline respects and protects the privacy of all individuals in
              our system. We maintain strict policies to ensure the privacy of
              those who use our Services (“End Users”) or those who may just be
              visiting our Site or whose data we hold as part of our service
              provider relationship with our clients (“Visitors”). This policy
              (“Privacy Policy”) describes the types of information we may
              collect from you and our practices for how we collect, use,
              maintain, protect, and disclose such information. The way that we
              collect and use your information depends on the way you access the
              Services (whether by Site or by App). This Privacy Policy also
              includes a description of certain rights that you may have over
              information that we may collect from you.
            </p>
            <p>
              By using the Services, you agree to this Privacy Policy. If you do
              not agree with our policies and practices, your choice is to not
              use our Services.
            </p>
            <p>
              FlyLine, Inc., a Delaware corporation, doing business as Flyline
              (“Flyline”) operates the Flyline.com and Wanderift.com websites
              (“Sites”), the Flyline mobile application (“App”), and the travel
              booking membership services offered through our Sites and App
              (together with the App and the Sites, the “Services”).
            </p>
            <p>
              Flyline respects and protects the privacy of all individuals in
              our system. We maintain strict policies to ensure the privacy of
              those who use our Services (“End Users”) or those who may just be
              visiting our Site or whose data we hold as part of our service
              provider relationship with our clients (“Visitors”). This policy
              (“Privacy Policy”) describes the types of information we may
              collect from you and our practices for how we collect, use,
              maintain, protect, and disclose such information. The way that we
              collect and use your information depends on the way you access the
              Services (whether by Site or by App). This Privacy Policy also
              includes a description of certain rights that you may have over
              information that we may collect from you.
            </p>
            <p>
              By using the Services, you agree to this Privacy Policy. If you do
              not agree with our policies and practices, your choice is to not
              use our Services.
            </p>
          </div>
        </div>
      </div>

      <Footer />

      <transition name="fade">
        <OverlayLanding
          @onClick="closeOverlay()"
          :overlayVisibility="overlayVisibility"
        ></OverlayLanding>
      </transition>
      <transition name="fade">
        <Construction
          @onClick="closeOverlay()"
          :overlayVisibility="constructionVisibility"
        ></Construction>
      </transition>
    </div>
    <div class="page--landing--mobile">
      <div class="mobile-navbar">
        <MobileNavbarLogo />
      </div>
      <MobileHomeContent />
      <img
        src="../assets/images/Illustrations.png"
        width="100%"
        height="100%"
      />
      <MobileFooter />
    </div>
  </div>
</template>
<script>
import OverlayLanding from "@/components/landing/overlayLanding";
import Navbar from "@/components/organisms/Navbar";
import Footer from "@/components/organisms/Footer";

import MobileFooter from "@/components/organisms/MobileFooter";
import MobileNavbarLogo from "@/components/molecules/MobileNavbarLogo";
import MobileHomeContent from "@/components/organisms/MobileHomeContent";
import Construction from "@/components/landing/Construction";

export default {
  name: "Landing",
  components: {
    Navbar,
    Footer,
    // Button,
    // Container,
    OverlayLanding,
    // SubFooter,
    MobileNavbarLogo,
    MobileHomeContent,
    MobileFooter,
    Construction
  },
  data() {
    let construction = process.env.VUE_APP_CONSTRUCTION
      ? process.env.VUE_APP_CONSTRUCTION.toLowerCase()
      : "false";
    let constructionVisibility = ["true", "1", "on"].includes(construction);
    return {
      overlayVisibility: false,
      constructionVisibility
    };
  },
  methods: {
    closeOverlay() {
      this.toggleOverlay();
    },
    toggleOverlay() {
      this.overlayVisibility = !this.overlayVisibility;
      if (this.overlayVisibility) {
        document.querySelector("body").classList.add("hide-scroll");
      } else {
        document.querySelector("body").classList.remove("hide-scroll");
      }
    },
    goTo(page) {
      this.$router.push({ name: page });
    }
  }
};
</script>
<style lang="scss">
.terms__section {
  padding-top: 130px;
  width: 660px;
  margin: 0 auto 94px;
  .terms__title {
    display: block;
    font-size: 40px;
    font-weight: bold;
    line-height: 0.9;
    letter-spacing: -0.8px;
    text-align: left;
    color: #0e3178;
    margin-bottom: 16px;
  }
  .terms__subtitle {
    display: block;
    font-size: 20px;
    font-weight: 600;
    line-height: 1.8;
    letter-spacing: -0.4px;
    text-align: left;
    color: #040404;
    opacity: 0.5;
  }
  .terms__content {
    position: sticky;
    max-height: 550px;
    overflow-y: scroll;
    padding-right: 40px;
    p {
      font-size: 18px;
      font-weight: 500;
      line-height: 1.67;
      text-align: left;
      color: #040404;
      opacity: 0.5;
    }
  }
  #scrollbar::-webkit-scrollbar-track {
    -webkit-box-shadow: inset 0 3px 6px 0 rgba(0, 0, 0, 0.16);
    background-color: #ffffff;
    border-radius: 30px;
  }
  #scrollbar::-webkit-scrollbar {
    width: 10px;
    background-color: #f5f5f5;
  }
  #scrollbar::-webkit-scrollbar-thumb {
    border-radius: 30px;
    -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
    background-color: #00aeef;
  }
}
</style>

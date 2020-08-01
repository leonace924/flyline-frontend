<template>
  <Container :padded="false">
    <footer class="footer">
      <section class="company">
        <img
          src="@/assets/images/FlylineSVG_Logotype.svg"
          alt="Flyline logo"
          class="company__logo"
        />
        <p class="company__slogan">
          We're on a mission to help <br />
          people spend less and travel more.
        </p>
      </section>
      <section class="sitemaps">
        <div class="sitemap">
          <h3 class="sitemap__title">Home</h3>
          <ul class="sitemap__links">
            <li class="sitemap__link">How it Works</li>
            <li class="sitemap__link">FlyLine Premium</li>
            <li class="sitemap__link">Get Started</li>
          </ul>
        </div>
        <div class="sitemap">
          <h3 class="sitemap__title">Product</h3>
          <ul class="sitemap__links">
            <li class="sitemap__link">Download App</li>
            <li class="sitemap__link">Different Fare Types</li>
            <li class="sitemap__link">FlyLine Blog</li>
            <li class="sitemap__link">Developer API</li>
          </ul>
        </div>
        <div class="sitemap">
          <h3 class="sitemap__title">Company</h3>
          <ul class="sitemap__links">
            <li class="sitemap__link">About</li>
            <li class="sitemap__link">FAQs</li>
            <li class="sitemap__link">Support</li>
            <li class="sitemap__link">Media Enquiries</li>
          </ul>
        </div>
        <div class="sitemap">
          <h3 class="sitemap__title">Legal</h3>
          <ul class="sitemap__links">
            <li class="sitemap__link">Terms of Use</li>
            <li class="sitemap__link">Privacy Policy</li>
          </ul>
        </div>
      </section>
      <div class="footer__misc">
        <div class="footer__copyright">
          © 2020 FlyLine. All right reserved.
        </div>
        <div class="footer__social">
          <a
            href="http://facebook.com"
            target="_blank"
            rel="noopener noreferrer"
            ><img src="@/assets/images/social/facebook.svg" alt=""
          /></a>
          <a
            href="http://instagram.com"
            target="_blank"
            rel="noopener noreferrer"
            ><img src="@/assets/images/social/instagram.svg" alt=""
          /></a>
          <a href="http://twitter.com" target="_blank" rel="noopener noreferrer"
            ><img src="@/assets/images/social/twitter.svg" alt=""
          /></a>
          <a
            href="https://medium.com/flyline"
            target="_blank"
            rel="noopener noreferrer"
            ><img src="@/assets/images/social/medium.svg" alt=""
          /></a>
          <a
            href="https://www.linkedin.com/company/flyline/?originalSubdomain=in"
            target="_blank"
            rel="noopener noreferrer"
            ><img src="@/assets/images/social/linkedin.svg" alt=""
          /></a>
        </div>
      </div>
    </footer>
  </Container>
</template>

<script>
import Container from "@/components/molecules/Container";

export default {
  name: "Footer",
  components: {
    Container
  }
};
</script>

<style lang="scss">
.footer {
  border-top: 1px solid #eef0f6;
  display: flex;
  justify-content: space-between;
  width: 100%;
  padding-top: 4rem;
  flex-wrap: wrap;

  &__misc {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 4rem 0 1rem 0;
  }

  &__copyright {
    opacity: 0.6;
    font-family: "Gilroy-Medium";
    font-size: 0.7rem;
  }

  &__social {
    display: inline-flex;
    align-items: center;
    justify-content: flex-end;

    > * {
      margin-right: 1.5rem;
    }

    > *:last-child {
      margin-right: 0;
    }

    img {
      height: 0.8rem;
    }
  }
}

.company {
  display: inline-flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;

  &__logo {
    padding-bottom: 2rem;
  }

  &__slogan {
    opacity: 0.6;
    line-height: 1.3;
    font-weight: 600;
    font-size: 0.7rem;
  }
}

.sitemaps {
  display: flex;
  justify-content: space-between;
  align-self: flex-start;
  flex-grow: 1;
  max-width: 60%;

  .sitemap {
    &__links {
      list-style: none;
      margin: 0;
      padding: 0;
    }

    &__title {
      font-family: "Gilroy-Bold";
      font-size: 1rem;
      padding-bottom: 10px;
    }

    &__link {
      opacity: 0.6;
      font-family: "Gilroy-Medium";
      font-size: 0.8rem;
      padding-bottom: 0.5rem;
    }
  }
}
</style>

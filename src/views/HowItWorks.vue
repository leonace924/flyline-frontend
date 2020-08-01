<template>
  <div class="page page--how-it-works">
    <Navbar />

    <Hero>
      <div slot="title" class="hero__title" style="font-family: gilroy-bold;">
        Leave the travel planning to us
      </div>
      <div
        slot="description"
        class="hero__description"
        style="font-family: gilroy-medium;"
      >
        Planning a trip can feel like a full-time job. Because it is. In olden
        times, people called “travel agents” would find and book your trips.
        FlyLine is your robo travel agent that never sleeps. Or eats. Or takes
        cigarette breaks. We just relentlessly pursue the perfect fares. Here’s
        how.
      </div>
    </Hero>

    <Container :dark="true" class="container--timeline">
      <section class="timeline-hiw">
        <h3 class="timeline__title" style="font-family: gilroy-bold;">
          What do I need to know?
        </h3>

        <div
          :class="{
            timeline__item: true,
            'timeline__item--reverse': i % 2 === 1
          }"
          v-for="(item, i) in timeline"
          :key="i"
        >
          <div class="timeline__item__img">
            <img :src="item.img" alt="Timeline image" />
          </div>
          <span class="timeline__item__bullet">
            <span class="icon" v-text="i + 1 < 10 ? `0${i + 1}` : i + 1"></span>
          </span>
          <div class="timeline__item__text">
            <h5 v-text="item.title"></h5>
            <p v-text="item.body"></p>
          </div>
        </div>
      </section>
    </Container>

    <Hero>
      <div slot="title" class="hero__title" style="font-family: gilroy-bold;">
        How does FlyLine score you such great deals?
      </div>
      <div
        slot="description"
        class="hero__description"
        style="font-family: gilroy-medium;"
      >
        We scour the darkest corners of the internet to locate ridiculously good
        bargains. Our search finds three main types of fares in order to find
        the best flights at the best prices.
      </div>
    </Hero>

    <Container>
      <section class="features-hiw">
        <div
          :class="{ feature: true, 'feature--reverse': i % 2 === 1 }"
          v-for="(feature, i) in features"
          :key="i"
        >
          <div
            class="feature__image"
            style="padding-top: 60px; padding-bottom: 20px;"
          >
            <img :src="feature.img" :alt="feature.heading" />
          </div>
          <div class="feature__details" style="padding-top: 60px;">
            <h3 class="feature__heading" v-text="feature.heading"></h3>
            <p class="feature__subheading" v-text="feature.subheading"></p>

            <p class="feature__description">
              {{ feature.body }}
              <a href="#" class="feature__link" v-text="feature.link_text"></a>
            </p>
          </div>
        </div>
      </section>

      <SubFooter />
    </Container>
    <Footer />
  </div>
</template>

<script>
import Hero from "@/components/molecules/Hero";
import Navbar from "@/components/organisms/Navbar";
import Footer from "@/components/organisms/Footer";
import Container from "@/components/molecules/Container";

export default {
  name: "HowItWorks",
  components: {
    Hero,
    Navbar,
    Footer,
    Container
  },
  computed: {
    timeline() {
      return [
        {
          title: "The best fares from everywhere",
          img: "/images/how-it-works/international-flights.svg",
          body:
            "Search fares from more than 250 airlines from a single place. Save all your traveler information so you can book with a click."
        },
        {
          title: "Get deals delivered",
          img: "/images/how-it-works/legacy-carriers.svg",
          body:
            "Set a few preferences and our army of internet robots will do the searching for you. We’ll alert you the second we find a great deal, which can be up to 60% off a standard fare."
        },
        {
          title: "Automatically book the best",
          img: "/images/how-it-works/major-cities.svg",
          body:
            "The best fares go fast. FlyLine can auto-book fares that meet your preferences so you won’t miss out. You’ll have 24 hours to confirm — if you don’t confirm you don’t pay."
        },
        {
          title: "Manage trips from your dedicated flightdeck (that’s us)",
          img: "/images/how-it-works/compare-the-fare.svg",
          body:
            "Use FlyLine to manage all the details of your flights, just like you would from the airlines’ sites. Select seats, make updates and cancellations, check upgrades, and more."
        },
        {
          title: "A subscription that pays for itself",
          img: "/images/how-it-works/deal-alerts.svg",
          body:
            "Everything’s included in your subscription fee, which most members earn back with just two bookings. No fare markups, no booking fees, no surprises."
        }
      ];
    },
    features() {
      return [
        {
          heading: "Direct bookings",
          subheading: "Exclusivity that saves you money",
          img: "/images/how-it-works/illustration_one.svg",
          body:
            "FlyLine Fares are sourced directly from more than 250 airlines with no markup. You can even earn up to 4% credit back to use for future travel."
        },
        {
          heading: "Meta searches",
          subheading: "Transparency that saves you time",
          img: "/images/how-it-works/illustration_two.svg",
          body:
            "We include results from meta search services like Kayak and TripAdvisor. Which means we’re kind of like a meta meta search. Not to brag."
        },
        {
          heading: "FlyLine Exclusives",
          subheading: "Expertise that saves you from missed discounts",
          img: "/images/how-it-works/illustration_three.svg",
          body:
            "Our exclusive AutoLink fares are discounted up to 60% by combining one-way tickets on different airlines. Connection times are factored in to make sure you — and your bags — can make the flight."
        }
      ];
    }
  }
};
</script>

<style lang="scss">
.page--how-it-works {
  font-family: "Gilroy-Regular", sans-serif;
  display: flex;
  flex-flow: column wrap;
  align-items: center;

  > .hero {
    margin-top: 1.5rem;
    padding: 2.5rem 3.5rem;
    width: 960px;
  }

  > .container {
    &--timeline {
      margin-top: 1.5rem;
    }

    &--padded {
      padding: 2.5rem;
    }
  }

  .features-hiw,
  .timeline-hiw {
    display: flex;
    align-items: center;
    flex-flow: column nowrap;
  }

  .timeline-hiw {
    .timeline {
      &__title {
        font-size: 0.8rem;
        font-family: "Gilroy-Medium";
        letter-spacing: 1.5px;
        text-transform: uppercase;
        color: #0e3178;
        margin-bottom: 1rem;
      }

      &__item {
        display: flex;
        align-items: flex-start;
        justify-content: center;
        flex-flow: row wrap;
        padding: 1rem 0;

        &--reverse {
          flex-flow: row-reverse wrap;

          .timeline__item {
            &__img {
              text-align: left;
            }

            &__text {
              text-align: right;
              border-top-left-radius: 1rem;
              border-top-right-radius: 0;
            }
          }
        }

        &__img,
        &__text {
          width: 40%;
        }

        &__img {
          text-align: right;
        }

        &__text {
          background-color: transparent;
          padding: 1.5rem;
          padding-top: 0;
          border-radius: 1rem;
          border-top-left-radius: 0;

          h5 {
            font-family: gilroy-bold;
            font-size: 1rem;
            font-weight: 600;
          }

          p {
            color: #7b7b7b;
            font-size: 0.8rem;
            margin-bottom: 0;
          }
        }

        &__bullet {
          display: flex;
          align-items: center;
          justify-content: center;
          padding: 0 3rem;
          position: relative;
          font-size: 0.6rem;

          &::after {
            position: absolute;
            content: "";
            top: 50%;
            height: 600%;
            width: 1px;
            background-color: #0e3178;
            z-index: 1;
            opacity: 0.1;
          }

          > .icon {
            display: inline-flex;
            border-radius: 5rem;
            width: 2rem;
            height: 2rem;
            border: 0.5px solid #dee2ee;
            justify-content: center;
            align-items: center;
            background-color: #ffffff;
            z-index: 2;
            color: #000000;
            font-weight: 600;
          }
        }
      }

      &__item:last-child {
        .timeline__item__bullet::after {
          height: 0;
        }
      }
    }
  }

  .features-hiw {
    .btn {
      border-radius: 30px !important;
      width: 6.5rem;
      height: auto;
      line-height: 2rem;
      font-size: 0.65rem;
    }

    .feature {
      display: flex;
      justify-content: center;
      align-items: center;

      &--reverse {
        flex-direction: row-reverse;
      }

      > * {
        padding: 1rem 0;
      }

      &__image {
        display: flex;
        flex-grow: 1;
        justify-content: center;
        align-items: center;
        width: 60%;
      }

      &__details {
        width: 40%;
        display: flex;
        flex-flow: column nowrap;
      }

      &__heading {
        color: #0e3178;
        font-size: 2.4rem;
        font-family: "Gilroy-Bold";
      }

      &__subheading {
        color: #333333;
        font-size: 1rem;
        position: relative;
        font-family: "Gilroy-SemiBold";

        &::after {
          content: "";
          width: 4.5rem;
          height: 0;
          border-bottom: 1.5px solid #0e3178;
          display: inline-block;
          position: absolute;
          bottom: -0.75rem;
          left: 0;
        }
      }

      &__line {
        color: #00aeef;
      }

      &__description {
        padding-top: 0.4rem;
        color: #7b7b7b;
        font-size: 0.8rem;
      }
    }
  }
}
</style>

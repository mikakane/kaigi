<template>
  <section>
    <footer class="p-footer">
      <div class="container">
        <div class="p-footer-items">
          <div class="p-footerLogo">
            <img class="p-footerLogo-logo" src="~/assets/images/textLogo-white.svg" alt="PHPerKaigi 2019">
            <div class="p-footerLogo-past">
              <span>
                過去の開催
              </span>
              <span class="p-footerLogo-baloon">
                <a href="https://phperkaigi.jp/2018/" target="_blank">2018</a>
              </span>
            </div>
          </div>
          <div class="p-footerLinks">
            <ul class="p-footerLinks-links">
              <li class="p-footerLinks-link">
                <a href="https://twitter.com/phperkaigi" target="_blank">お問い合わせ（twitter）</a>
              </li>
              <li class="p-footerLinks-link">
                <a href="" target="_blank">行動規範</a>
              </li>
            </ul>
          </div>
        </div>
        <div class="p-footerCredit">
          <div>Powered by</div>
          <img class="p-footerCredit-logo" src="~/assets/images/poweredBy.svg" alt="builderscon">
          <p class="p-footerCopyright">
            <small>©  PHPerKaigi 2019.</small>
          </p>
        </div>
      </div>
    </footer>
  </section>
</template>

<script>
  import VueScrollTo from "vue-scrollto"

  export default {
    name: "Footer",
    mounted() {},
    methods:{
      scroll(){
        VueScrollTo.scrollTo(document.getElementsByTagName("html"),500)
      }
    }
  }
</script>

<style lang="scss" scoped>
@import "~/assets/scss/library/_mixin.scss";
@import "~/assets/scss/library/_variable.scss";

$clr-footer:#2D2C2F;

.p-footer{
  background: $clr-footer;
  color: #FFF;
  overflow: hidden; // disable Collapsing Margins
  &-items{
    border-bottom: #7f828b 1px solid;
    margin-top: 5rem;
    padding-bottom: 5rem;
    margin-bottom: 5rem;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
}

.p-footerLogo,
.p-footerLinks{
  max-width: 100%;
  width: 45rem;
}

.p-footerLogo{
  @include media_desktop {
    padding: 0 11rem;
  }

  &-logo{
    width: 25rem;
  }
  &-past{
    margin: 2rem 0 3rem;
    text-align: center;

    @include media_desktop {
      text-align: left;
    }
  }
  &-baloon{
    position: relative;
    margin-left: 10px;
    padding: .5rem 1rem;
    border-radius: 0.5rem;
    background:
      -webkit-linear-gradient(45deg, transparent 4px, $clr-main 4px),
      -webkit-linear-gradient(135deg, transparent 4px, $clr-main 4px),
      -webkit-linear-gradient(225deg, transparent 4px, $clr-main 4px),
      -webkit-linear-gradient(315deg, transparent 4px, $clr-main 4px);
    background-position: bottom left, bottom right, top right, top left;
    background-size: 51% 51%;
    background-repeat: no-repeat;
    &::before {
      position: absolute;
      top: 50%;
      left: 0;
      width: 5px;
      height: 5px;
      background-color: $clr-main;
      transform: translate(-50%, -50%) rotateZ(45deg);
      content: '';
    }
    a{
      color: $clr-footer;
      text-decoration: underline;
      &:hover {
        text-decoration: none;
      }
    }
  }
}

.p-footerLinks{
  @include media_desktop {
    padding-left: 17rem;
  }
  &-links{
    list-style: none;
  }
  &-link{
    margin-bottom: 2rem;
    a{
      color: $clr-main;
      text-decoration: underline;
      &:hover {
        text-decoration: none;
      }
    }
  }
}

.p-footerCredit{
  font-size: 1.4rem;
  text-align: center;
  &-logo{
    display: block;
    width: 20rem;
    margin: 0 auto;
    margin-top: 1rem;
  }
}

.p-footerCopyright{
  margin: 4rem 0;
}
</style>

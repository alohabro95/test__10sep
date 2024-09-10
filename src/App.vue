<script setup lang="ts">
document.addEventListener("DOMContentLoaded", () => {
  function preloadImages(srcArray: string[]): void {
    srcArray.forEach((src: string) => {
      const img: HTMLImageElement = new Image();
      img.src = src;
    });
  }

  preloadImages([
    "public/desktop-images/hero-learn.webp",
    "public/desktop-images/hero-play.webp",
    "public/desktop-images/hero-watch.webp",
  ]);

  const buttons = document.querySelectorAll(".btn");
  const container = document.querySelector(".section-hero") as HTMLElement;
  const contentText = document.querySelector(".hero__caption") as HTMLElement;
  const minWidth = 768;
  if (window.innerWidth >= minWidth) {
    buttons.forEach((button) => {
      button.addEventListener("mouseenter", () => {
        const newImage = button.getAttribute("data-image");
        const newText = button.getAttribute("data-text");
        if (container && contentText) {
          container.style.backgroundImage = `url(${newImage})`;
          contentText.textContent = newText;
        }
      });
    });
  } else {
    container.style.backgroundImage = `url(/public/mobile-images/first-background.png)`;
  }

  const playElements =
    document.querySelectorAll<HTMLElement>(".categories__el");
  const playButtons = document.querySelectorAll<HTMLElement>(
    ".categories__button"
  );
  if (window.innerWidth >= minWidth) {
    playElements.forEach((playElement, index) => {
      playElement.addEventListener("mouseenter", () => {
        if (playButtons[index]) {
          playButtons[index].style.display = "flex";
        } else {
        }
      });

      playElement.addEventListener("mouseleave", () => {
        if (playButtons[index]) {
          playButtons[index].style.display = "none";
        }
      });
    });
  }
});
</script>

<template>
  <section class="section-header">
    <div class="header">
      <div class="header__menu">
        <img src="/public/icons/menu.png" alt="" />
        <span class="desktop-menu">МЕНЮ</span>
      </div>
      <ul class="desktop-list">
        <li>играть</li>
        <li>смотреть</li>
        <li>учиться</li>
        <li>мероприятия</li>
      </ul>
      <img class="header__logo" src="/public/icons/logo-text.png" alt="" />
      <div class="header__profile">
        <span class="desktop-profile">ГЕННАДИЙ П.</span>
        <img src="/public/icons/profile-image.png" alt="" />
      </div>
    </div>
  </section>
  <section class="section-hero">
    <div class="hero">
      <h1 class="hero__caption">
        НАЙДИ <span class="phrase">С КЕМ</span> ПОИГРАТЬ
        <span class="phrase">В БАСКЕТ</span>
      </h1>
      <div class="buttons">
        <button
          class="buttons__el btn"
          data-image="/public/desktop-images/hero-play.webp"
          data-text="НАЙДИ С КЕМ ПОИГРАТЬ В БАСКЕТ"
        >
          ИГРАЙ
        </button>
        <button
          class="buttons__el btn"
          data-image="/public/desktop-images/hero-learn.webp"
          data-text="ЗДЕСЬ ДОЛЖЕН БЫТЬ ТЕКСТ"
        >
          УЧИСЬ
        </button>
        <button
          class="buttons__el btn"
          data-image="/public/desktop-images/hero-watch.webp"
          data-text="И ЗДЕСЬ ДОЛЖЕН БЫТЬ"
        >
          СМОТРИ
        </button>
      </div>
    </div>
  </section>
  <section class="section-play">
    <div class="play">
      <section class="section-title_group">
        <div class="title-group learn-title-group">
          <h1 class="caption caption--black">ИГРАЙ</h1>
          <div class="orange-group">
            <h3 class="caption caption--orange">В РАЗДЕЛ</h3>
            <img
              class="orange__arrow"
              src="/public/desktop-images/right_arrow--orange.png"
              alt=""
            />
          </div>
        </div>
      </section>
      <div class="categories">
        <div id="categories__el" class="categories__el">
          <img
            id="categories__image"
            class="categories__image categories__image--kids"
            src="/public/mobile-images/categories-kids.jpg"
            alt=""
          />
          <div class="categories__container">
            <h2 class="categories__title">НАЙДИ СЕБЕ КОМАНДУ</h2>
            <p class="categories__description">
              Игры на районе - это возможность найти с кем поиграть в баскетбол
              в выходные, или создать свою игру и пригласить других игроков
              присоединиться.
            </p>
            <button class="categories__button buttons__el">ТЕКСТ КНОПКИ</button>
          </div>
        </div>
        <div id="categories__el" class="categories__el">
          <img
            id="ball"
            class="categories__image categories__image--ball"
            src="/public/mobile-images/categories-ball.jpg"
            alt=""
          />
          <div class="categories__container">
            <h2 class="categories__title">СОЗДАВАЙ КОМАНДЫ</h2>
            <p class="categories__description">
              Создавайте команды с друзьями. Делитесь фотографиями, делайте
              опросы и участвуйте в турнирах. Будьте активными и получайте
              ачивки для вашей команды.
            </p>
            <button class="categories__button buttons__el">ТЕКСТ КНОПКИ</button>
          </div>
        </div>
        <div id="categories__el" class="categories__el">
          <img
            id="categories__image"
            class="categories__image categories__image--mens"
            src="/public/mobile-images/categories-mens.jpg"
            alt=""
          />
          <div class="categories__container">
            <h2 class="categories__title">УЧАСТВУЙ В ТУРНИРАХ</h2>
            <p class="categories__description">
              Участвуйте в турнирах вместе с вашей командой. Будьте активными,
              побеждайте и получайте ачивки и призы от наших спонсоров.
            </p>
            <button class="categories__button buttons__el">ТЕКСТ КНОПКИ</button>
          </div>
        </div>
      </div>
    </div>
  </section>
  <section class="section-learn">
    <div class="title-group learn-title-group">
      <h1 class="caption caption--black">УЧИСЬ</h1>
      <div class="orange-group">
        <h3 class="caption caption--orange">В РАЗДЕЛ</h3>
        <img
          class="orange__arrow"
          src="/public/desktop-images/right_arrow--orange.png"
          alt=""
        />
      </div>
    </div>
    <div class="learn-desktop">
      <div class="learn">
        <div class="learn__el learn__el--first">
          <h2 class="learn__title">
            МЫ СОБРАЛИ СЕКЦИИ ДЛЯ ДЕТЕЙ ПО ВСЕМУ ГОРОДУ
          </h2>
          <button class="learn__button">
            <span>12 </span><span>СЕКЦИЙ ПО ВСЕМУ ГОРОДУ</span>
          </button>
        </div>
        <div class="learn__el learn__el--second">
          <h2 class="learn__title">ПОДБЕРИ ТРЕНЕРА ПОД СВОЙ УРОВЕНЬ</h2>
          <div class="learn__buttons">
            <button class="learn__button">ДЕТСКАЯ ТРЕНИРОВКА</button>
            <button class="learn__button">ДЛЯ НАЧИНАЮЩИХ</button>
            <button class="learn__button">СТРИТБОЛ</button>
            <button class="learn__button">ВЫЕЗД ТРЕНЕРА НА ДОМ</button>
            <button class="learn__button">12 ФИЛЬТРОВ</button>
          </div>
        </div>
      </div>
      <section class="section-other">
        <div class="other">
          <div class="other__el">
            <h3 class="other__title">ВИДЕОУРОКИ</h3>
            <div class="other__content other__content--first">
              <img
                class="other__img"
                src="/public/desktop-images/other-img.png"
                alt=""
              />
              <div class="other-first__block">
                <p class="other__text">
                  ЕВГЕНИЙ ВОРОНОВ: «БРОНЗОВЫЕ МЕДАЛИ - ОЦЕНКА ТРУДА НАШЕЙ
                  КОМАНДЫ»
                </p>
                <span class="other__date">26 октября</span>
              </div>
            </div>
          </div>
          <div class="other__el">
            <h3 class="other__title">СТАТЬИ</h3>
            <div class="other__content">
              <p class="other__text">
                ЕВГЕНИЙ ВОРОНОВ: «БРОНЗОВЫЕ МЕДАЛИ - ОЦЕНКА ТРУДА НАШЕЙ КОМАНДЫ»
              </p>
              <span class="other__date">26 октября</span>
            </div>
          </div>
          <div class="other__el">
            <h3 class="other__title">ТЕРМИНЫ</h3>
            <div class="terms">
              <span class="other__footer-el other__date">ТРЕХА</span>
              <span class="other__footer-el other__date"
                >ТРЕХОЧКОВЫЙ БРОСОК</span
              >
              <span class="other__footer-el other__date">36 ТЕРМИНОВ</span>
            </div>
          </div>
        </div>
      </section>
    </div>
  </section>
  <section class="section-footer">
    <div class="footer">
      <div class="footer__container">
        <div class="footer__main">
          <h2 class="footer__caption">
            ЕЩЕ БОЛЬШЕ ПОЛЕЗНЫХ МАТЕРИАЛОВ И ВИДЕОУРОКОВ В НАШЕМ ПРИЛОЖЕНИИ
          </h2>
          <div class="apps">
            <div class="app">
              <img
                class="app__img"
                src="/public/mobile-images/apple.png"
                alt=""
              />
              <span class="app__download"
                >Download on the <span class="brand">App Store</span></span
              >
            </div>
            <div class="app">
              <img
                class="app__img"
                src="/public/mobile-images/google.png"
                alt=""
              />
              <span class="app__download"
                >Get in on <span class="brand">Google Play</span></span
              >
            </div>
          </div>
        </div>
        <span class="xpage">СДЕЛАНО В XPAGE</span>
      </div>
      <div class="qr">
        <div class="qr__content">
          <img class="qr__img" src="/public/desktop-images/qr.png" alt="" />
          <div class="qr__block">
            <span class="qr__apps">IOS / Android</span>
            <p class="qr__text">
              НАВЕДИТЕ КАМЕРУ УСТРОЙСТВА НА QR-КОД, ЧТОБЫ СКАЧАТЬ
            </p>
          </div>
        </div>
      </div>
      <div class="footer__bg">
        <img
          class="footer__img"
          src="/public/desktop-images/desktop-footer-ball.png"
          alt=""
        />
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
$white: #fff;
$orange: #f36722;
$green: #2e8d43;
h1 {
  line-height: 31.2px;
  font-size: 26px;
}
h2 {
  font-size: 20px;
  line-height: 26px;
}
h3 {
  line-height: 19.6px;
  font-size: 16px;
}

.section-header {
  margin-bottom: 8px;
}
.header {
  display: flex;
  justify-content: space-between;
  padding: 8px 12px;
  background-color: $white;
  border-radius: 5px;
}
.desktop-list {
  display: none;
}
.desktop-menu {
  display: none;
}
.desktop-profile {
  display: none;
}
.section-hero {
  background-image: url(/public/mobile-images/first-background.png);
  transition: background-image 0.7s ease-in-out;
  background-image: linear-gradient(
    rgba(255, 255, 255, 0.5),
    rgba(255, 255, 255, 0.5)
  );
  background-repeat: no-repeat;
  background-size: cover;
  border-radius: 12px;
  margin-bottom: 42px;

  .hero {
    display: flex;
    flex-direction: column;
    height: 516px;
    justify-content: end;
    padding: 12px;

    &__caption {
      color: $white;
      font-weight: 700;
      margin-bottom: 12px;
    }

    .phrase {
      display: inline-block;
    }
  }
}

.buttons {
  display: flex;
  flex-direction: column;
  gap: 4px;

  &__el {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: $white;
    border-style: none;
    border-radius: 10px;
    height: 40px;
    text-align: start;
    padding: 0px 14px;
    font-family: "Druk-Bold", sans-serif;
    font-size: 17px;
    line-height: 19.6px;

    &::after {
      content: url(/public/mobile-images/arrow-right.png);
      margin-left: auto;
    }

    &:hover {
      color: $white;
      background-color: $orange;
    }
  }
}

.section-play {
  margin-bottom: 42px;
}
.section-title_group {
  margin-bottom: 22px;
}
.title-group {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
}
.caption {
  &--orange {
    color: $orange;
  }
}
.categories {
  display: flex;
  flex-direction: column;
  gap: 8px;
  &__el {
    display: flex;
    flex-direction: column;
    background-color: #fff;
    border-radius: 10px;
    font-size: 0px;
  }

  &__container {
    display: flex;
    flex-direction: column;
    gap: 8px;
    padding: 0px 12px 12px 12px;
  }
  &__image {
    border-radius: 10px 10px 150px 150px;
    width: 100%;
    &--ball {
      width: unset;
      display: flex;
      margin-left: auto;
      border-radius: unset;
    }
  }

  &__title {
    font-family: "Druk-Bold", sans-serif;
  }

  &__description {
    font-size: 14px;
    font-family: "Inter", serif;
    font-weight: 500;
    line-height: 19.6px;
  }
  &__button {
    background-color: $orange;
    color: $white;
    font-size: 16px;
    display: none;
  }
}
.section-learn {
  margin-bottom: 42px;
}
.learn-title-group {
  margin-bottom: 18px;
}
.learn {
  display: flex;
  flex-direction: column;
  gap: 8px;
  &__el {
    display: flex;
    flex-direction: column;
    padding: 12px;
    border-radius: 10px;
    &--first {
      gap: 220px;
      background-image: url(/public/mobile-images/learn-bg-image.jpg);
      text-align: left;
      background-size: 100%;
      background-repeat: no-repeat;
    }
    &--second {
      gap: 126px;
      background-color: $green;
    }
  }
  &__title {
    color: $white;
    text-align: left;
    max-width: 212px;
  }

  &__button {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    background-color: $white;
    border-style: none;
    border-radius: 20px;
    padding: 6px 12px;
    font-size: 10px;
    font-family: "Druk-Bold";
    font-weight: 700;
    line-height: 14px;
    color: $orange;

    span {
      flex-grow: 1;
      text-align: center;
    }
  }
  &__buttons {
    display: flex;
    flex-direction: column;
    gap: 4px;
    align-items: baseline;
  }
  &__buttons button {
    color: $white;
    font-size: 12px;
    width: unset;
    background-color: rgba(255, 255, 255, 0.2);
    &:hover {
      color: $green;
      background-color: rgba(255, 255, 255, 1);
    }
  }
}

.other {
  display: none;
}
.section-footer {
  border-top: 2px #202020 solid;
}
.footer,
.footer__container,
.footer__main,
.app {
  display: flex;
}
.footer {
  position: relative;
  padding: 20px 0px 25px 0px;
  &__caption {
    max-width: 260px;
  }
  &__main {
    flex-direction: column;
    gap: 32px;
  }
  &__container {
    flex-direction: column;
    gap: 165px;
  }
  &__bg {
    z-index: -1;
    position: absolute;
    bottom: 60px;
    right: -72px;
    .footer__img {
      width: 214px;
      height: 216px;
    }
  }
}

.apps {
  display: flex;
  flex-direction: column;
  gap: 24px;
}
.app {
  display: flex;
  gap: 14px;
  max-width: 146px;

  &__download {
    font-family: "Inter-regular", serif;
    font-size: 14px;

    .brand {
      font-weight: 700;
    }
  }
}
.xpage {
  font-size: 10px;
}
.orange__arrow {
  display: none;
}
.qr {
  display: none;
}
@media (min-width: 375px) {
  .categories__image {
    border-radius: 10px 10px 200px 200px;
  }
  .categories__image--ball {
    border-radius: unset;
  }
  .learn__button {
    display: block;
  }
  .orange__arrow {
    display: none;
  }
  .qr {
    display: none;
  }
}
@media (min-width: 425px) {
  .learn__button {
    display: block;
  }
  .orange__arrow {
    display: none;
  }
  .qr {
    display: none;
  }
}
@media (min-width: 768px) {
  .header {
    height: 56px;
    align-items: center;
    border-radius: 20px;

    .desktop-list {
      list-style: none;
      font-size: 10px;
      order: 2;
      display: flex;
      gap: 12px;
      padding: 0;
    }
    &__logo {
      order: 1;
      margin-right: 20px;
    }
    &__menu {
      margin: 0px 10px 0px auto;
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 10px;
      order: 3;
      .desktop-menu {
        display: block;
      }
      img {
        max-height: 20px;
      }
    }
    &__profile {
      padding: 6px 3px 6px 12px;
      border-radius: 20px;
      background-color: #efefef;
      display: flex;
      align-items: center;
      gap: 10px;
      order: 4;
      .desktop-profile {
        font-size: 10px;
        display: block;
      }
    }
  }
  .section-hero {
    background-image: url(/public/desktop-images/hero-play.webp);
    background-size: cover;
    background-repeat: no-repeat;
    margin-bottom: 80px;
    .hero {
      height: unset;
      &__caption {
        font-size: 32px;
        margin-top: 220px;
        max-width: 530px;
        line-height: 36px;
      }
      .buttons {
        flex-direction: row;
        justify-content: space-between;
        &__el {
          width: 100%;
          font-size: 14px;
        }
      }
    }
  }
  .caption {
    font-size: 32px;
    &--orange {
      font-size: 16px;
      display: inline-flex;
      align-items: center;
    }
  }
  .orange-group {
    display: flex;
    gap: 8px;
  }
  .orange__arrow {
    display: block;
  }
  .categories {
    flex-direction: row;
    &__el {
      height: 420px;
      flex-grow: 1;
      width: 100%;
      flex: 1;
      justify-content: space-between;
      transition: 0.5s ease;
      &:hover {
        background-color: #000000;
        color: #fff;
        .categories__image {
          max-height: 170px;
        }
      }
    }
    &__image {
      max-height: 188px;
      transition: max-height 0.7s ease;
      height: auto;
      &--kids {
        content: url(/public/desktop-images/play-kids-desktop.png);
      }
      &--ball {
        content: url(/public/desktop-images/desktop-play-ball.png);
      }
      &--mens {
        content: url(/public/desktop-images/play-mens-desktop.png);
      }
    }
    &__container {
      justify-content: flex-start;
    }
    &__title {
      font-size: 20px;
    }
    &__description {
      font-size: 12px;
    }
    &__button {
      cursor: pointer;
      height: 34px;
      font-size: 12px;
      &:hover {
      }
    }
  }
  .section-learn {
    background-color: $white;
    padding: 16px;
    border-radius: 20px;
  }
  .learn {
    display: flex;
    flex-direction: column;
    flex-basis: 65%;
    gap: 14px;
    &__el {
      &--first {
        justify-content: space-between;
        flex-basis: 62%;
        background-image: url(/public/desktop-images/desktop-kids.png);
        background-size: cover;
        background-position-x: -290px;
      }
      &--second {
        justify-content: space-between;
        gap: unset;
        flex-basis: 38%;
        background-color: $green;
      }
    }
    &__title {
      color: $white;
      text-align: left;
      font-size: 24px;
      max-width: fit-content;
      line-height: 27px;
    }

    &__button {
      width: fit-content;
    }
    &__buttons {
      flex-direction: row;
      max-width: fit-content;
      flex-wrap: wrap;
    }
  }
  .learn-desktop {
    display: flex;
    gap: 10px;
  }
  .section-other {
    flex-basis: 35%;
    border-left: 1px #c4c4c4 solid;
    .other {
      display: flex;
      flex-direction: column;
      padding-left: 12px;
      &__el {
        border-bottom: 1px #c4c4c4 solid;
        padding-bottom: 20px;
      }

      &__title {
        margin-bottom: 20px;
      }
      .other__el:nth-child(2) .other__title,
      .other__el:nth-child(3) .other__title {
        padding-top: 8px;
      }
      &__content {
        display: flex;
        flex-direction: column;
        gap: 10px;
      }
      .other-first__block {
        display: flex;
        flex-direction: column;
        gap: 10px;
      }
      .terms {
        display: flex;
        flex-wrap: wrap;
        gap: 5px;
      }
      &__date {
        width: fit-content;
        border-radius: 38px;
        background-color: #efefef;
        padding: 8px 12px;
      }

      &__footer-el {
        padding: 6px 10px;
        font-size: 10px;
      }
    }
  }
  .section-footer {
    .footer {
      padding: 20px;
      justify-content: space-between;
      display: flex;
      flex-direction: row;
      overflow: hidden;
      margin-bottom: unset;
      &__caption {
        max-width: 470px;
        font-size: 36px;
        line-height: 47px;
      }
      &__bg {
        z-index: -1;
        position: absolute;
        right: -630px;
        top: 42px;
        bottom: unset;
        .footer__img {
          width: 100%;
          height: 100%;
        }
      }
    }
    .apps {
      flex-direction: row;
    }
    .xpage {
    }
    .qr {
      margin-top: 28px;
      display: block;
      background-color: $white;
      border-radius: 30px;
      height: fit-content;
      width: 214px;
      &__content {
        padding: 20px;
        height: fit-content;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        gap: 30px;
      }
      &__img {
        font-size: 0px;
        width: 100px;
      }
      &__block {
        display: flex;
        flex-direction: column;
        gap: 10px;
      }
      &__apps {
        font-family: "Inter", serif;
        font-size: 16px;
        color: #747474;
      }
      &__text {
        font-size: 14px;
      }
    }
  }
}
@media (min-width: 1024px) {
  .header {
    height: 64px;
    &__menu,
    .desktop-profile,
    .desktop-list {
      font-size: 14px;
    }
    &__logo {
      margin-right: 64px;
    }
    &__menu {
      margin-right: 22px;
    }
  }
  .section-hero {
    background-position-x: -250px;
    transition: 1s ease;

    .hero {
      &__caption {
        font-size: 52px;
        line-height: 70px;
        max-width: unset;
        margin-top: 294px;
        margin-bottom: 48px;
      }
    }
  }
  .buttons {
    gap: 8px;
    &__el {
      cursor: pointer;
      font-size: 16px;
      height: 64px;
      padding: 20px 24px;
      border-radius: 20px;
      transition: 1s ease;
    }
  }
  .section-play {
    .play {
      .section-title_group {
        margin-bottom: 64px;
        .caption {
          &--black {
            font-size: 50px;
          }
          &--orange {
            font-size: 20px;
          }
        }
      }
      .categories {
        &__el {
          height: 480px;
          &:hover {
            .categories__image {
              max-height: 230px;
            }
          }
        }
        &__image {
          max-height: 246px;
        }
        &__description {
          min-height: 78px;
        }
        &__button {
          height: 44px;
        }
      }
    }
  }
  .learn-title-group {
    .caption {
      &--black {
        font-size: 50px;
        line-height: 96px;
      }
      &--orange {
        font-size: 20px;
      }
    }
  }
  .learn__el {
    background-position: -186px;
    gap: unset;
    justify-content: space-between;
    height: 100%;
  }
  .learn__title {
    max-width: 382px;
  }

  .section-footer {
    .footer {
      justify-content: unset;
      gap: 60px;
      &__container {
        gap: 307px;
      }
      .qr {
        width: 352px;
        height: 401px;
        &__img {
          width: 180px;
        }
        &__content {
          padding: 40px;
        }
      }
      &__bg {
        top: 168px;
        right: -512px;
      }
    }
  }
}
@media (min-width: 1037px) {
  .section-hero {
    background-position-x: unset;
  }
}
@media (min-width: 1340px) {
  .section-hero {
    background-position: unset;
    .hero {
      &__caption {
        font-size: 80px;
        line-height: 96px;
        max-width: 1338px;
      }
    }
  }
  .section-play {
    .play {
      .categories {
        &__el {
          height: 784px;
          transition: max-height 0.7s ease;
          &:hover {
            & .categories__image {
              max-height: 420px;
            }
          }
        }
        &__image {
          max-height: 446px;
          height: 100%;
          border-radius: 20px 20px 640px 640px;
          transition: max-height 0.5s ease;
          &--ball {
            border-radius: unset;
          }
        }
        &__container {
          gap: 16px;
        }
        &__title {
          font-size: 32px;
          line-height: 41.6px;
        }
        &__description {
          min-height: 102px;
          font-size: 16px;
          line-height: 25.6px;
        }
        &__button {
          height: 64px;
        }
      }
    }
  }
  .learn__el {
    &--first {
      flex-basis: 75%;
      background-position: unset;
    }
    &--second {
      flex-basis: 25%;
    }
  }
  .learn__buttons {
    max-width: 572px;
  }
  .section-footer {
    .footer {
      gap: 121px;
      .footer__caption {
        max-width: 1138px;
      }
      &__bg {
        top: 92px;
        right: -346px;
      }
      .qr {
        &__content {
          padding: 40px;
        }
        &__img {
          width: 180px;
        }
      }
    }
  }
}
@media (min-width: 1700px) {
  .section-hero .hero {
    height: 920px;
    margin-bottom: 120px;
  }
  .section-play {
    margin-bottom: 120px;
    .play {
      .section-title_group {
        .title-group {
          .caption {
            &--black {
              font-size: 80px;
              line-height: 96px;
            }
            &--orange {
              font-size: 20px;
              line-height: 26px;
            }
          }
        }
      }
    }
  }
  #categories__el {
    padding-bottom: 24px;
    &:hover {
      .categories__image {
        max-height: 470px;
      }
    }
  }
  #categories__image {
    transition: max-height 1s ease;
    border-radius: 20px 20px 640px 640px;
    max-height: 520px;
    height: 100%;
    &:hover {
      max-height: 480px;
    }
  }
  #ball {
    max-width: 100%;
    max-height: 520px;
    content: url(/public/desktop-images/desktop-play-ball.png);
    border-radius: unset;
  }
  .categories__title {
    font-size: 32px;
    line-height: 41.6px;
    max-width: 500px;
  }
  .categories__description {
    font-size: 16px;
    max-width: 478px;
  }
  .section-learn {
    margin-bottom: 120px;
    padding: 32px;
    .learn-title-group {
      margin-bottom: 64px;
      .caption {
        &--black {
          font-size: 80px;
          line-height: 96px;
        }
        &--orange {
          font-size: 20px;
          line-height: 26px;
        }
      }
      .orange-group {
      }
    }
    .learn-desktop {
      .learn {
        &__el {
          &--first {
            background-position-x: -274px;
          }
        }
        &__title {
          max-width: 772px;
          font-size: 48px;
          line-height: 57.6px;
        }
        &__button {
          padding: 8px 12px;
          font-size: 12px;
        }
      }
    }
  }
  .section-other {
    .other h3 {
      font-size: 20px;
    }
    .other {
      &__el {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        height: 318px;
      }
      &__content {
        gap: 16px;
        &--first {
          flex-direction: row;
          gap: 20px;
        }
        .other-first__block {
          justify-content: space-between;
        }
      }
      .other__el:nth-child(2) .other__title,
      .other__el:nth-child(3) .other__title {
        padding-top: 20px;
      }
      &__date {
        font-size: 12px;
        padding: 8px 12px;
      }
    }
  }
  .section-footer {
    .footer {
      &__caption {
        font-size: 48px;
        max-width: 955px;
      }
    }
  }
}
</style>

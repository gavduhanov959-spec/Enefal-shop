<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#111111">

<title>Enefal Shop — Мужская одежда</title>

<style>
:root{
    --black:#0d0d0d;
    --white:#ffffff;
    --gray:#777;
    --light:#f4f4f2;
    --border:#e8e8e8;
}

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:-apple-system,BlinkMacSystemFont,"Helvetica Neue",Arial,sans-serif;
    color:var(--black);
    background:var(--white);
    overflow-x:hidden;
}

button,
input,
select{
    font:inherit;
}

button{
    cursor:pointer;
}

a{
    color:inherit;
    text-decoration:none;
}

/* HEADER */

.header{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:70px;
    z-index:100;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:0 20px;
    color:white;
    transition:.4s ease;
}

.header.scrolled{
    background:rgba(255,255,255,.94);
    backdrop-filter:blur(15px);
    color:#111;
    border-bottom:1px solid var(--border);
}

.logo{
    font-size:20px;
    font-weight:800;
    letter-spacing:5px;
}

.header-actions{
    display:flex;
    gap:16px;
    align-items:center;
}

.header-btn{
    border:0;
    background:none;
    color:inherit;
    font-size:21px;
    position:relative;
}

.cart-number{
    position:absolute;
    right:-8px;
    top:-8px;
    background:#111;
    color:white;
    width:18px;
    height:18px;
    border-radius:50%;
    font-size:10px;
    display:flex;
    align-items:center;
    justify-content:center;
}

/* HERO */

.hero{
    height:100svh;
    min-height:650px;
    position:relative;
    overflow:hidden;
    background:#111;
}

.hero-image{
    position:absolute;
    inset:0;
    background:
        linear-gradient(180deg,rgba(0,0,0,.1),rgba(0,0,0,.68)),
        url("https://images.unsplash.com/photo-1617127365659-c47fa864d8bc?auto=format&fit=crop&w=1800&q=90")
        center/cover;
    transform:scale(1.08);
    transition:transform .15s linear;
}

.hero-content{
    position:absolute;
    left:22px;
    right:22px;
    bottom:60px;
    color:white;
}

.hero-small{
    font-size:12px;
    letter-spacing:4px;
    margin-bottom:18px;
    opacity:0;
    animation:fadeUp 1s .2s forwards;
}

.hero h1{
    font-size:clamp(55px,16vw,110px);
    line-height:.82;
    letter-spacing:-5px;
    font-weight:800;
    opacity:0;
    animation:fadeUp 1s .35s forwards;
}

.hero-text{
    margin-top:25px;
    font-size:15px;
    opacity:0;
    animation:fadeUp 1s .5s forwards;
}

.hero-button{
    display:inline-flex;
    margin-top:28px;
    padding:17px 25px;
    background:white;
    color:#111;
    font-weight:700;
    opacity:0;
    animation:fadeUp 1s .65s forwards;
    transition:.3s;
}

.hero-button:active{
    transform:scale(.96);
}

@keyframes fadeUp{
    from{
        opacity:0;
        transform:translateY(30px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}

/* SECTIONS */

.section{
    padding:90px 20px;
}

.section-head{
    display:flex;
    justify-content:space-between;
    align-items:end;
    margin-bottom:30px;
}

.section-label{
    font-size:11px;
    letter-spacing:3px;
    color:#888;
    margin-bottom:8px;
}

.section-title{
    font-size:34px;
    letter-spacing:-1.5px;
}

.section-link{
    font-size:13px;
    border-bottom:1px solid #111;
    padding-bottom:3px;
}

/* PRODUCTS */

.products{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:18px 10px;
}

.product{
    opacity:0;
    transform:translateY(50px);
    transition:
        opacity .8s ease,
        transform .8s ease;
}

.product.visible{
    opacity:1;
    transform:translateY(0);
}

.product-image{
    aspect-ratio:3/4;
    overflow:hidden;
    background:#eee;
    position:relative;
}

.product-image img{
    width:100%;
    height:100%;
    object-fit:cover;
    transition:transform .8s cubic-bezier(.2,.7,.2,1);
}

.product:active img{
    transform:scale(1.04);
}

.product-info{
    padding:13px 2px 10px;
}

.product-name{
    font-size:14px;
    margin-bottom:6px;
}

.product-category{
    font-size:11px;
    color:#999;
    margin-bottom:8px;
}

.product-price{
    font-size:14px;
    font-weight:700;
}

/* STORY */

.story{
    min-height:90svh;
    position:relative;
    overflow:hidden;
    display:flex;
    align-items:flex-end;
    color:white;
    background:#111;
}

.story-image{
    position:absolute;
    inset:0;
    background:
        linear-gradient(180deg,rgba(0,0,0,.05),rgba(0,0,0,.75)),
        url("https://images.unsplash.com/photo-1529139574466-a303027c1d8b?auto=format&fit=crop&w=1600&q=90")
        center/cover;
    transform:scale(1.05);
}

.story-content{
    position:relative;
    padding:40px 22px;
    z-index:2;
    opacity:0;
    transform:translateY(50px);
    transition:1s ease;
}

.story-content.visible{
    opacity:1;
    transform:translateY(0);
}

.story-content .label{
    font-size:11px;
    letter-spacing:4px;
    margin-bottom:15px;
}

.story-content h2{
    font-size:52px;
    line-height:.9;
    letter-spacing:-3px;
    margin-bottom:20px;
}

.story-content p{
    color:#ddd;
    line-height:1.6;
    max-width:420px;
}

/* CATEGORIES */

.categories{
    display:flex;
    overflow-x:auto;
    gap:12px;
    margin:0 -20px;
    padding:0 20px 15px;
    scrollbar-width:none;
}

.categories::-webkit-scrollbar{
    display:none;
}

.category{
    min-width:78vw;
    height:390px;
    position:relative;
    overflow:hidden;
    display:flex;
    align-items:flex-end;
    padding:24px;
    color:white;
    background-size:cover;
    background-position:center;
}

.category:after{
    content:"";
    position:absolute;
    inset:0;
    background:linear-gradient(transparent,rgba(0,0,0,.7));
}

.category-content{
    position:relative;
    z-index:2;
}

.category-number{
    font-size:11px;
    letter-spacing:3px;
    opacity:.7;
}

.category h3{
    font-size:32px;
    margin-top:8px;
}

/* BENEFITS */

.benefits{
    background:var(--light);
}

.benefit{
    padding:25px 0;
    border-bottom:1px solid #ddd;
    display:flex;
    justify-content:space-between;
    gap:20px;
}

.benefit:last-child{
    border-bottom:0;
}

.benefit-number{
    font-size:12px;
    color:#999;
}

.benefit h3{
    font-size:18px;
    margin-bottom:7px;
}

.benefit p{
    color:#777;
    font-size:13px;
    line-height:1.5;
}

/* NEWSLETTER */

.newsletter{
    text-align:center;
}

.newsletter h2{
    font-size:40px;
    letter-spacing:-2px;
    margin-bottom:15px;
}

.newsletter p{
    color:#777;
    font-size:14px;
    line-height:1.6;
    margin-bottom:25px;
}

.email-box{
    display:flex;
    border-bottom:1px solid #111;
    max-width:500px;
    margin:auto;
}

.email-box input{
    border:0;
    outline:0;
    padding:16px 5px;
    flex:1;
}

.email-box button{
    border:0;
    background:none;
    font-weight:700;
}

/* FOOTER */

footer{
    background:#111;
    color:white;
    padding:60px 20px 35px;
}

.footer-logo{
    font-size:26px;
    letter-spacing:6px;
    font-weight:800;
    margin-bottom:45px;
}

.footer-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:35px;
}

.footer-column h4{
    font-size:12px;
    letter-spacing:2px;
    margin-bottom:18px;
}

.footer-column a{
    display:block;
    color:#999;
    font-size:13px;
    margin-bottom:12px;
}

.copyright{
    margin-top:60px;
    color:#555;
    font-size:11px;
}

/* CART */

.cart-panel{
    position:fixed;
    z-index:300;
    right:0;
    top:0;
    width:min(420px,100%);
    height:100svh;
    background:white;
    transform:translateX(100%);
    transition:.45s cubic-bezier(.2,.7,.2,1);
    box-shadow:-10px 0 40px rgba(0,0,0,.15);
    display:flex;
    flex-direction:column;
}

.cart-panel.open{
    transform:translateX(0);
}

.cart-header{
    height:70px;
    padding:0 20px;
    border-bottom:1px solid #eee;
    display:flex;
    justify-content:space-between;
    align-items:center;
}

.cart-header h2{
    font-size:18px;
}

.close-cart{
    border:0;
    background:none;
    font-size:24px;
}

.cart-items{
    flex:1;
    overflow:auto;
    padding:20px;
}

.empty-cart{
    text-align:center;
    padding-top:80px;
    color:#888;
}

.cart-item{
    display:flex;
    gap:14px;
    padding-bottom:20px;
    margin-bottom:20px;
    border-bottom:1px solid #eee;
}

.cart-item img{
    width:90px;
    height:115px;
    object-fit:cover;
}

.cart-item-info{
    flex:1;
}

.cart-item-info h3{
    font-size:14px;
    margin-bottom:8px;
}

.cart-item-info p{
    font-size:13px;
    color:#777;
}

.remove{
    margin-top:15px;
    border:0;
    background:none;
    text-decoration:underline;
    font-size:12px;
}

.cart-footer{
    padding:20px;
    border-top:1px solid #eee;
}

.total{
    display:flex;
    justify-content:space-between;
    font-weight:700;
    margin-bottom:15px;
}

.checkout{
    width:100%;
    border:0;
    background:#111;
    color:white;
    padding:17px;
    font-weight:700;
}

/* MODAL */

.modal{
    position:fixed;
    inset:0;
    background:rgba(0,0,0,.55);
    z-index:400;
    display:flex;
    align-items:flex-end;
    opacity:0;
    pointer-events:none;
    transition:.3s;
}

.modal.open{
    opacity:1;
    pointer-events:auto;
}

.modal-box{
    background:white;
    width:100%;
    max-height:90svh;
    overflow:auto;
    padding:30px 20px;
    transform:translateY(100%);
    transition:.4s;
}

.modal.open .modal-box{
    transform:translateY(0);
}

.modal-head{
    display:flex;
    justify-content:space-between;
    margin-bottom:25px;
}

.modal-head h2{
    font-size:25px;
}

.close-modal{
    border:0;
    background:none;
    font-size:24px;
}

.form-group{
    margin-bottom:18px;
}

.form-group label{
    display:block;
    font-size:12px;
    color:#777;
    margin-bottom:7px;
}

.form-group input,
.form-group select{
    width:100%;
    padding:14px;
    border:1px solid #ddd;
    outline:none;
}

.order-button{
    width:100%;
    border:0;
    background:#111;
    color:white;
    padding:17px;
    font-weight:700;
    margin-top:5px;
}

/* TOAST */

.toast{
    position:fixed;
    z-index:500;
    bottom:25px;
    left:20px;
    right:20px;
    background:#111;
    color:white;
    padding:16px;
    text-align:center;
    transform:translateY(120px);
    opacity:0;
    transition:.4s;
}

.toast.show{
    transform:translateY(0);
    opacity:1;
}

/* DESKTOP */

@media(min-width:800px){

    .header{
        padding:0 45px;
    }

    .hero-content{
        left:60px;
        bottom:80px;
    }

    .section{
        padding:120px 60px;
    }

    .products{
        grid-template-columns:repeat(4,1fr);
        gap:20px;
    }

    .category{
        min-width:300px;
    }

    .categories{
        overflow:visible;
    }

    .footer-grid{
        grid-template-columns:repeat(4,1fr);
    }
}
</style>
</head>

<body>

<header class="header" id="header">
    <a class="logo" href="#">ENEfal</a>

    <div class="header-actions">
        <button class="header-btn" onclick="openCart()" aria-label="Корзина">
            ♡
        </button>

        <button class="header-btn" onclick="openCart()" aria-label="Корзина">
            🛒
            <span class="cart-number" id="cartNumber">0</span>
        </button>
    </div>
</header>


<!-- HERO -->

<section class="hero">

    <div class="hero-image" id="heroImage"></div>

    <div class="hero-content">

        <div class="hero-small">
            ENEFAL / 2026 COLLECTION
        </div>

        <h1>
            NEW<br>
            SEASON
        </h1>

        <div class="hero-text">
            Мужская одежда нового поколения.
        </div>

        <a href="#catalog" class="hero-button">
            СМОТРЕТЬ КОЛЛЕКЦИЮ
        </a>

    </div>

</section>


<!-- PRODUCTS -->

<section class="section" id="catalog">

    <div class="section-head">

        <div>
            <div class="section-label">
                ENEFAL / 01
            </div>

            <h2 class="section-title">
                Новинки
            </h2>
        </div>

        <a href="#categories" class="section-link">
            Все категории
        </a>

    </div>


    <div class="products">


        <article class="product">

            <div class="product-image">
                <img
                loading="lazy"
                src="https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?auto=format&fit=crop&w=800&q=85">
            </div>

            <div class="product-info">

                <div class="product-category">
                    T-SHIRTS
                </div>

                <div class="product-name">
                    Essential White
                </div>

                <div class="product-price">
                    4 990 ₽
                </div>

                <button
                    style="margin-top:12px;border:0;background:#111;color:white;padding:10px 13px;font-size:12px"
                    onclick="addProduct('Essential White','4 990 ₽','https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?auto=format&fit=crop&w=800&q=85')">
                    ДОБАВИТЬ
                </button>

            </div>

        </article>


        <article class="product">

            <div class="product-image">
                <img
                loading="lazy"
                src="https://images.unsplash.com/photo-1556821840-3a63f95609a7?auto=format&fit=crop&w=800&q=85">
            </div>

            <div class="product-info">

                <div class="product-category">
                    HOODIES
                </div>

                <div class="product-name">
                    Heavy Hoodie
                </div>

                <div class="product-price">
                    8 990 ₽
                </div>

                <button
                    style="margin-top:12px;border:0;background:#111;color:white;padding:10px 13px;font-size:12px"
                    onclick="addProduct('Heavy Hoodie','8 990 ₽','https://images.unsplash.com/photo-1556821840-3a63f95609a7?auto=format&fit=crop&w=800&q=85')">
                    ДОБАВИТЬ
                </button>

            </div>

        </article>


        <article class="product">

            <div class="product-image">
                <img
                loading="lazy"
                src="https://images.unsplash.com/photo-1542272604-787c3835535d?auto=format&fit=crop&w=800&q=85">
            </div>

            <div class="product-info">

                <div class="product-category">
                    DENIM
                </div>

                <div class="product-name">
                    Classic Denim
                </div>

                <div class="product-price">
                    7 490 ₽
                </div>

                <button
                    style="margin-top:12px;border:0;background:#111;color:white;padding:10px 13px;font-size:12px"
                    onclick="addProduct('Classic Denim','7 490 ₽','https://images.unsplash.com/photo-1542272604-787c3835535d?auto=format&fit=crop&w=800&q=85')">
                    ДОБАВИТЬ
                </button>

            </div>

        </article>


        <article class="product">

            <div class="product-image">
                <img
                loading="lazy"
                src="https://images.unsplash.com/photo-1548126032-079a0fb0099d?auto=format&fit=crop&w=800&q=85">
            </div>

            <div class="product-info">

                <div class="product-category">
                    JACKETS
                </div>

                <div class="product-name">
                    Urban Jacket
                </div>

                <div class="product-price">
                    12 990 ₽
                </div>

                <button
                    style="margin-top:12px;border:0;background:#111;color:white;padding:10px 13px;font-size:12px"
                    onclick="addProduct('Urban Jacket','12 990 ₽','https://images.unsplash.com/photo-1548126032-079a0fb0099d?auto=format&fit=crop&w=800&q=85')">
                    ДОБАВИТЬ
                </button>

            </div>

        </article>

    </div>

</section>


<!-- STORY -->

<section class="story">

    <div class="story-image" id="storyImage"></div>

    <div class="story-content reveal">

        <div class="label">
            ENEFAL / PHILOSOPHY
        </div>

        <h2>
            LESS.<br>
            BETTER.
        </h2>

        <p>
            Мы создаём вещи, которые не требуют лишних слов.
            Чистые формы, спокойные цвета и вещи,
            которые легко становятся частью твоего ежедневного стиля.
        </p>

    </div>

</section>


<!-- CATEGORIES -->

<section class="section" id="categories">

    <div class="section-head">

        <div>

            <div class="section-label">
                ENEFAL / 02
            </div>

            <h2 class="section-title">
                Категории
            </h2>

        </div>

    </div>


    <div class="categories">

        <div class="category"
        style="background-image:url('https://images.unsplash.com/photo-1523398002811-999ca8dec234?auto=format&fit=crop&w=1000&q=85')">

            <div class="category-content">

                <div class="category-number">
                    01
                </div>

                <h3>
                    Футболки
                </h3>

            </div>

        </div>


        <div class="category"
        style="background-image:url('https://images.unsplash.com/photo-1556821840-3a63f95609a7?auto=format&fit=crop&w=1000&q=85')">

            <div class="category-content">

                <div class="category-number">
                    02
                </div>

                <h3>
                    Худи
                </h3>

            </div>

        </div>


        <div class="category"
        style="background-image:url('https://images.unsplash.com/photo-1551488831-00ddcb6c6bd3?auto=format&fit=crop&w=1000&q=85')">

            <div class="category-content">

                <div class="category-number">
                    03
                </div>

                <h3>
                    Куртки
                </h3>

            </div>

        </div>


        <div class="category"
        style="background-image:url('https://images.unsplash.com/photo-1624378439575-d8705ad7ae80?auto=format&fit=crop&w=1000&q=85')">

            <div class="category-content">

                <div class="category-number">
                    04
                </div>

                <h3>
                    Брюки
                </h3>

            </div>

        </div>

    </div>

</section>


<!-- BENEFITS -->

<section class="section benefits">

    <div class="section-head">

        <div>

            <div class="section-label">
                ENEFAL / 03
            </div>

            <h2 class="section-title">
                Наш подход
            </h2>

        </div>

    </div>


    <div class="benefit">

        <div class="benefit-number">
            01
        </div>

        <div>
            <h3>
                Качество
            </h3>

            <p>
                Отбираем материалы и модели,
                ориентируясь на ежедневную носку.
            </p>
        </div>

    </div>


    <div class="benefit">

        <div class="benefit-number">
            02
        </div>

        <div>
            <h3>
                Минимализм
            </h3>

            <p>
                Никакой визуальной перегрузки.
                Только необходимые детали.
            </p>
        </div>

    </div>


    <div class="benefit">

        <div class="benefit-number">
            03
        </div>

        <div>
            <h3>
                Доставка
            </h3>

            <p>
                Отправляем заказы по России
                и другим направлениям.
            </p>
        </div>

    </div>

</section>


<!-- NEWSLETTER -->

<section class="section newsletter">

    <div class="section-label">
        ENEFAL / COMMUNITY
    </div>

    <h2>
        Будь первым.
    </h2>

    <p>
        Новости коллекций, новые поступления
        и специальные предложения.
    </p>

    <div class="email-box">

        <input
        type="email"
        placeholder="Ваш email">

        <button onclick="subscribe()">
            →
        </button>

    </div>

</section>


<!-- FOOTER -->

<footer>

    <div class="footer-logo">
        ENEFAL
    </div>

    <div class="footer-grid">

        <div class="footer-column">

            <h4>
                SHOP
            </h4>

            <a href="#catalog">
                Новинки
            </a>

            <a href="#categories">
                Категории
            </a>

        </div>


        <div class="footer-column">

            <h4>
                INFO
            </h4>

            <a href="#">
                Доставка
            </a>

            <a href="#">
                Оплата
            </a>

            <a href="#">
                Возврат
            </a>

        </div>


        <div class="footer-column">

            <h4>
                SOCIAL
            </h4>

            <a href="#">
                Telegram
            </a>

            <a href="#">
                Instagram
            </a>

        </div>


        <div class="footer-column">

            <h4>
                CONTACT
            </h4>

            <a href="mailto:hello@enefal.ru">
                hello@enefal.ru
            </a>

        </div>

    </div>


    <div class="copyright">
        © 2026 ENEFAL SHOP
    </div>

</footer>


<!-- CART -->

<div class="cart-panel" id="cartPanel">

    <div class="cart-header">

        <h2>
            Корзина
        </h2>

        <button class="close-cart" onclick="closeCart()">
            ×
        </button>

    </div>


    <div class="cart-items" id="cartItems">

        <div class="empty-cart">
            Корзина пока пуста.
        </div>

    </div>


    <div class="cart-footer">

        <div class="total">

            <span>
                Итого
            </span>

            <span id="total">
                0 ₽
            </span>

        </div>

        <button class="checkout" onclick="openCheckout()">
            ОФОРМИТЬ ЗАКАЗ
        </button>

    </div>

</div>


<!-- CHECKOUT -->

<div class="modal" id="checkoutModal">

    <div class="modal-box">

        <div class="modal-head">

            <h2>
                Оформление
            </h2>

            <button class="close-modal" onclick="closeCheckout()">
                ×
            </button>

        </div>


        <div class="form-group">

            <label>
                ИМЯ
            </label>

            <input
            id="name"
            type="text"
            placeholder="Ваше имя">

        </div>


        <div class="form-group">

            <label>
                ТЕЛЕФОН
            </label>

            <input
            id="phone"
            type="tel"
            placeholder="+7 900 000-00-00">

        </div>


        <div class="form-group">

            <label>
                РАЗМЕР
            </label>

            <select id="size">

                <option>
                    S
                </option>

                <option>
                    M
                </option>

                <option>
                    L
                </option>

                <option>
                    XL
                </option>

            </select>

        </div>


        <div class="form-group">

            <label>
                АДРЕС ДОСТАВКИ
            </label>

            <input
            id="address"
            type="text"
            placeholder="Город, улица, дом">

        </div>


        <button class="order-button" onclick="submitOrder()">
            ОТПРАВИТЬ ЗАКАЗ
        </button>

    </div>

</div>


<!-- TOAST -->

<div class="toast" id="toast">
    Товар добавлен в корзину
</div>


<script>

/* HEADER */

const header = document.getElementById("header");
const heroImage = document.getElementById("heroImage");
const storyImage = document.getElementById("storyImage");

window.addEventListener("scroll", () => {

    const scroll = window.scrollY;

    if(scroll > 60){
        header.classList.add("scrolled");
    }else{
        header.classList.remove("scrolled");
    }

    heroImage.style.transform =
        "scale(1.08) translateY(" + scroll * 0.08 + "px)";

    const storyTop =
        document.querySelector(".story").offsetTop;

    const storyOffset =
        scroll - storyTop;

    if(storyOffset > -700 && storyOffset < 1000){
        storyImage.style.transform =
            "scale(1.08) translateY(" + storyOffset * 0.06 + "px)";
    }

});


/* SCROLL ANIMATIONS */

const observer = new IntersectionObserver(
    entries => {

        entries.forEach(entry => {

            if(entry.isIntersecting){

                entry.target.classList.add("visible");

                observer.unobserve(entry.target);

            }

        });

    },
    {
        threshold:.12
    }
);


document.querySelectorAll(".product, .reveal")
.forEach(el => observer.observe(el));


/* CART */

let cart = [];


function addProduct(name,price,image){

    cart.push({
        name:name,
        price:price,
        image:image
    });

    updateCart();

    showToast();

}


function updateCart(){

    const container =
        document.getElementById("cartItems");

    const number =
        document.getElementById("cartNumber");

    const total =
        document.getElementById("total");


    number.textContent = cart.length;


    if(cart.length === 0){

        container.innerHTML =
            '<div class="empty-cart">Корзина пока пуста.</div>';

        total.textContent = "0 ₽";

        return;

    }


    let sum = 0;


    container.innerHTML = cart.map((item,index) => {

        const numericPrice =
            parseInt(item.price.replace(/\D/g,""));

        sum += numericPrice;


        return `

        <div class="cart-item">

            <img src="${item.image}">

            <div class="cart-item-info">

                <h3>
                    ${item.name}
                </h3>

                <p>
                    ${item.price}
                </p>

                <button
                    class="remove"
                    onclick="removeProduct(${index})">
                    Удалить
                </button>

            </div>

        </div>

        `;

    }).join("");


    total.textContent =
        sum.toLocaleString("ru-RU") + " ₽";

}


function removeProduct(index){

    cart.splice(index,1);

    updateCart();

}


function openCart(){

    document
        .getElementById("cartPanel")
        .classList.add("open");

}


function closeCart(){

    document
        .getElementById("cartPanel")
        .classList.remove("open");

}


/* CHECKOUT */

function openCheckout(){

    if(cart.length === 0){

        showToast("Сначала добавьте товар");

        return;

    }

    document
        .getElementById("checkoutModal")
        .classList.add("open");

}


function closeCheckout(){

    document
        .getElementById("checkoutModal")
        .classList.remove("open");

}


function submitOrder(){

    const name =
        document.getElementById("name").value.trim();

    const phone =
        document.getElementById("phone").value.trim();

    const address =
        document.getElementById("address").value.trim();


    if(!name || !phone || !address){

        showToast("Заполните все поля");

        return;

    }


    alert(
        "Спасибо, " +
        name +
        "! Заявка сохранена в демо-режиме."
    );


    cart = [];

    updateCart();

    closeCheckout();

    closeCart();

}


/* TOAST */

function showToast(message){

    const toast =
        document.getElementById("toast");

    toast.textContent =
        message || "Товар добавлен в корзину";

    toast.classList.add("show");


    setTimeout(() => {

        toast.classList.remove("show");

    },2200);

}


/* NEWSLETTER */

function subscribe(){

    showToast("Спасибо! Вы подписались.");

}

</script>

</body>
</html>

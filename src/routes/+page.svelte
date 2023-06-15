<script>
    import { onMount } from 'svelte';
    import { fade } from 'svelte/transition';
    import { fly } from 'svelte/transition';
    import {checkpage} from './store.js';

    checkpage.update(n => 1);
    let ready = false;
    let y = 0;
    let pagenum = 1;
    let techstackpage = 1;

    $:console.log(y);
    onMount(() => ready = true);

    const nextpage = () =>{
        if(pagenum < 4)
        {
            pagenum += 1;
        }
        else{
            pagenum = 1;
        }
    }
    const perviouspage = () =>{
        if(pagenum > 1)
        {
            pagenum -= 1;
        }
        else{
            pagenum =4;
        }
    }
    const settechstack = (page) =>{
        techstackpage = page;
    }

</script>

<svelte:window bind:scrollY={y}/>

{#if ready}
<section class="present">
<div class="header-video">
<video autoplay muted loop in:fade={{duration:1000}} out:fade>
        <source src="homevideo4.mp4" type="video/mp4">
</video>
</div>
<header class="viewport-header" in:fade={{duration:1000}} out:fade>
    <div class="header-caption" in:fly={{y:200, duration:3000}} out:fly>
        <img class="header-logo" width="160px" src="/logo.png" alt="logo">
        <h1>Import Star</h1>
        <h2>High-quality web application that can support all of your needs.</h2>
        <h2>ให้บริการ Software Development ระดับมืออาชีพ พร้อมจะนำเสนอ Software ให้กับ ทุกไอเดียธุรกิจของคุณ ให้เกิดขึ้นจริง</h2>
    </div>
  </header>
</section>
{/if}

<section class="cardsection">
    {#if ready && y > 100}
    <div class="cardboard" in:fly={{y:200, duration:3000}} out:fly>
        <div class="card">
            <img src="application.png" alt="" srcset="">
            <h2>Web Application</h2>
            <p>ออกแบบและพัฒนาเว็บแอปพลิเคชันที่ตอบสนองทุกความต้องการของธุรกิจของคุณ</p>
        </div>
        <div class="card">
            <img src="web-design.png" alt="" srcset="">
            <h2>UI / UX Design</h2>
            <p>ออกแบบและสร้างสรรค์เว็บไซต์ให้โดดเด่นกว่าคู่แข่งของคุณและใช้งานง่ายไม่ว่าเว็บรูปแบบไหนเราก็พร้อมดีไซน์</p>
        </div>
        <div class="card">
            <img src="mobile-app.png" alt="" srcset="">
            <h2>Mobile Application</h2>
            <p>ส่งมอบแอปพลิเคชันเพิ่ใความสะดวกสบายและช่องทางการเข้าถึงธุรกิจของคุณให้ครบถ้วนทุกแพลตฟอร์ม</p>
        </div>
        <div class="card">
            <img src="line.png" alt="" srcset="">
            <h2>Line OA</h2>
            <p>Messaging API ให้การสื่อสารระหว่างธุรกิจกับลูกค้าของคุณง่ายขึ้นเพื่อไม่ให้พลาดทุกข่าวสารโปรโมชั่นช่วยให้ธุรกิจและแบรนด์สร้าง Conversion ได้ดีขึ้น</p>
        </div>
    </div>
{/if}
</section>

{#if ready && y > 400}
<section class="webheadersection" in:fade={{duration:2000}} out:fade>
    <div class="webheader">
        <p>Web application</p>
        <h2>เราเข้าใจทุกธุรกิจมีความต้องการที่แตกต่างกัน</h2>
        <h2>เราสามารถออกแบบให้ตรงตาม Requirements ที่เหมาะสมในแต่ละธุรกิจโดยเฉพาะ</h2>
    </div>
</section>
{/if}

    
    <section class="slideshowsection">
        {#if ready && y > 1200}
        <div class="slideshow" in:fade={{duration:1000}} out:fade>
            <div class="previous-container">
                <button class="changepage" on:click={perviouspage}>&lt;</button>
            </div>
            {#if pagenum == 1}
            <div class="slidecontent" in:fade={{duration:2000}}>
                <div class="slidecontent-img">
                    <img src="application.png" alt="" srcset="">
                </div>
                <div class="slidecontent-caption">
                    <h2>content Management system</h2>
                    <p>
                        เพิ่มความสะดวกสบาย ด้วย User-friendly interface
                        ในการใช้งานทั้งลูกค้าและผู้ดูแลระบบ ดูแลจัดการสินค้าง่ายขึ้น
                        ด้วยระบบ Product management พร้อมเพิ่มความปลอดภัย
                        Payment gateways and Securit ของเรา
                    </p>
                </div>
            </div>
            {:else if pagenum == 2}
            <div class="slidecontent" in:fade={{duration:2000}}>
                <div class="slidecontent-img">
                    <img src="web-design.png" alt="" srcset="">
                </div>
                <div class="slidecontent-caption">
                    <h2>E-commerce platforms</h2>
                    <p>
                        เพิ่มความสะดวกสบาย ด้วย User-friendly interface
                        ในการใช้งานทั้งลูกค้าและผู้ดูแลระบบ ดูแลจัดการสินค้าง่ายขึ้น
                        ด้วยระบบ Product management พร้อมเพิ่มความปลอดภัย
                        Payment gateways and Securit ของเรา
                    </p>
                </div>
            </div>
            {:else if pagenum == 3}
            <div class="slidecontent" in:fade={{duration:2000}}>
                <div class="slidecontent-img">
                    <img src="mobile-app.png" alt="" srcset="">
                </div>
                <div class="slidecontent-caption">
                    <h2>booking and integration</h2>
                    <p>
                        ระบบการจอง ไม่ว่าจะเป็น การจองโรงแรม ระบบจองโต๊ะร้านอาหาร
                        หรือ แม้แต่จองคิวล้างรถ หากต้องการ Feature เหล่านี้
                        Import star สามารถออกแบบให้ตรงตามความต้องการได้
                    </p>
                </div>
            </div>
            {:else if pagenum == 4}
            <div class="slidecontent" in:fade={{duration:2000}}>
                <div class="slidecontent-img">
                    <img src="line.png" alt="" srcset="">
                </div>
                <div class="slidecontent-caption">
                    <h2>API Development Services</h2>
                    <p>
                        ประสานแอปพลิเคชันใหม่เข้ากับระบบซอฟต์แวร์ที่มีอยู่เดิมเพื่อ
                        ตอบสนองความต้องการใหม่ๆของลูกค้าในแพลตฟอร์มต่างๆ
                    </p>
                </div>
            </div>
            {/if}
            <div class="next-container">
                <button class="changepage" on:click={nextpage}>&gt;</button>
            </div>
        </div>
        {/if}
    </section>
    
    <section class="contentimagesection">
        {#if ready && y > 2200}
        <div class="contentimage-container" in:fly={{y:200 ,duration:2000}} out:fade>
            <div class="contentimage-caption">
                <h2>UI/UX Design</h2>
                <p>
                    ออกแบบและสร้างสรรค์เว็บไซต์ให้โดดเด่น
                    มีประสิทธิภาพกว่าคู่แข่งของคุณ
                    ใส่ใจทุกรายละเอียดเพื่อให้มั่นใจ
                    ว่าคุณจะได้รับประสบการณ์ที่ดีที่สุดในการใช้งาน
                </p>
            </div>
            <div class="contentimage-image">
                <img src="uiuxdesign.jpg" alt="" srcset="">
            </div>
        </div>
        {/if}
    </section>

{#if ready && y > 2600}
<section class="webheadersection" in:fade={{duration:2000}} out:fade>
    <div class="webheader">
        <p>Mobile application development</p>
        <h2>ให้ธุรกิจสามารถ เชื่อมต่อเข้ากับลูกค้าของคุณ</h2>
        <h2>ส่งมอบ APPs เพิ่มความสะดวกสบายและช่องทางการเข้าถึงธุรกิจของคุณ ครบถ้วนทุกแพลตฟอร์ม</h2>
    </div>
</section>
{/if}

<section class="cardsection">
{#if ready && y > 3000}
    <div class="cardboard boardcenter" in:fly={{y:200, duration:3000}} out:fly>
        <div class="card longsize">
            <img src="application.png" alt="" srcset="">
            <h2>Cross-platform / Hybrid Apps</h2>
            <p>ครอบคุมทุกช่องทางจะเป็น iOS หรือ Android ให้ทุกการเชื่อมต่อไหลลื่นทุกระบบการใช้งาน</p>
        </div>
        <div class="card longsize">
            <img src="web-design.png" alt="" srcset="">
            <h2>Enterprise Mobile Solutions</h2>
            <p>ตอบโจทย์ B2B และ B2C mobile solutions สำหรับภายในองค์กรหรือสำหรับลูกค้าขององค์กรเพื่อความปลอดภัยและประสบการณ์การใช้งานที่ดีที่สุด</p>
        </div>
    </div>
{/if}
</section>

{#if ready && y > 3500}
<section class="webheadersection" in:fade={{duration:2000}} out:fade>
    <div class="webheader">
        <p>Line OA</p>
        <h2>ให้การสร้างธุรกิจและแบรนด์ง่ายขึ้น</h2>
    </div>
</section>
{/if}

<section class="contentimagesection">
    {#if ready && y > 4200}
    <div class="contentimage-container" in:fly={{y:200 ,duration:2000}} out:fade>
        <div class="contentimage-caption">
            <h2>Line OA</h2>
            <p>
                ทางเราสามารถทำ Messaging API ทำให้การสื่อสารระหว่างธุรกิจกับลูกค้าของคุณง่ายขึ้น เพื่อไม่ให้พลาดทุกข่าวสารโปรโมชั่น ช่วยให้ธุรกิจและแบรนด์สร้าง Conversion ได้ดีขึ้น
            </p>
        </div>
        <div class="contentimage-image">
            <img src="Lineoa.jpg" alt="" srcset="">
        </div>
    </div>
    {/if}
</section>

<section class="techstacksection">
    {#if ready && y > 5500}
    <div class="techstack" in:fly={{y:200 ,duration:2000}} out:fade>
        <h2>TECHNOLOGY STACK</h2>
        <h1>Technologies we work with</h1>
        <ul class="techstack-menu">
            <!-- svelte-ignore a11y-invalid-attribute -->
            <li><a href="#" on:click={() =>{settechstack(1)}}>Framework</a></li>
            <!-- svelte-ignore a11y-invalid-attribute -->
            <li><a href="#" on:click={() =>{settechstack(2)}}>Frontend</a></li>
            <!-- svelte-ignore a11y-invalid-attribute -->
            <li><a href="#" on:click={() =>{settechstack(3)}}>Backend</a></li>
            <!-- svelte-ignore a11y-invalid-attribute -->
            <li><a href="#" on:click={() =>{settechstack(4)}}>Data</a></li>
            <!-- svelte-ignore a11y-invalid-attribute -->
            <li><a href="#" on:click={() =>{settechstack(5)}}>Linting/Testing</a></li>
            <!-- svelte-ignore a11y-invalid-attribute -->
            <li><a href="#" on:click={() =>{settechstack(6)}}>Infrastructure</a></li>
            <!-- svelte-ignore a11y-invalid-attribute -->
            <li><a href="#" on:click={() =>{settechstack(7)}}>Management</a></li>
        </ul>
        <div class="techstack-image">
            {#if techstackpage == 1}
            <img src="/techstack/svelte-kit.png" alt="" srcset="" in:fly={{y:200 ,duration:1000}}>
            <img src="/techstack/strapi.jpg" alt="" srcset="" in:fly={{y:200 ,duration:1300}}>
            {/if}
            {#if techstackpage == 2}
            <img src="/techstack/svelte-logo.png" alt="" srcset="" in:fly={{y:200 ,duration:1000}}> 
            <img src="/techstack/tailwind-css-logo-vector.png" alt="" srcset="" in:fly={{y:200 ,duration:1300}}>
            <img src="/techstack/alpine-js.jpg" alt="" srcset="" in:fly={{y:200 ,duration:1600}}>
            <img src="/techstack/jinja.png" alt="" srcset="" in:fly={{y:200 ,duration:1900}}>
            {/if}
            {#if techstackpage == 3}
            <img src="/techstack/flask.png" alt="" srcset="" in:fly={{y:200 ,duration:1000}}>
            <img src="/techstack/fastapi.jpg" alt="" srcset="" in:fly={{y:200 ,duration:1300}}>
            <img src="/techstack/Python-Logo.png" alt="" srcset="" in:fly={{y:200 ,duration:1600}}>
            {/if}
            {#if techstackpage == 4}
            <img src="/techstack/PostgreSQL-Logo.png" alt="" srcset="" in:fly={{y:200 ,duration:1000}}>
            <img src="/techstack/Logo-redis.svg.png" alt="" srcset="" in:fly={{y:200 ,duration:1300}}>
            <img src="/techstack/MongoDB-Logo.jpg" alt="" srcset="" in:fly={{y:200 ,duration:1600}}>
            {/if}
            {#if techstackpage == 5}
            <img src="/techstack/prettier.png" alt="" srcset="" in:fly={{y:200 ,duration:1000}}>
            <img src="/techstack/es.png" alt="" srcset="" in:fly={{y:200 ,duration:1300}}>
            <img src="/techstack/getpostman-ar21.png" alt="" srcset="" in:fly={{y:200 ,duration:1600}}>
            {/if}
            {#if techstackpage == 6}
            <img src="/techstack/Docker-Logo-2017-present.jpg" alt="" srcset="" in:fly={{y:200 ,duration:1000}}>
            <img src="/techstack/NGINX-logo-rgb-large.png" alt="" srcset="" in:fly={{y:200 ,duration:1300}}>
            <img src="/techstack/gunicorn.jpeg" alt="" srcset="" in:fly={{y:200 ,duration:1600}}>
            <img src="/techstack/uvicorn.png" alt="" srcset="" in:fly={{y:200 ,duration:1900}}>
            <img src="/techstack/uptime.png" alt="" srcset="" in:fly={{y:200 ,duration:2200}}>
            {/if}
            {#if techstackpage == 7}
            <img src="/techstack/notion1411.jpg" alt="" srcset="" in:fly={{y:200 ,duration:1000}}>
            <img src="/techstack/Discord-logo.png" alt="" srcset="" in:fly={{y:200 ,duration:1300}}>
            {/if}
        </div>
    </div>
    {/if}
</section>

<style>
     @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@600&display=swap');
    div.header-video{
        padding-top: 0px;
    }
    video{
        object-fit: cover;
        position: absolute;
        width: 100%;
        height: 100vh;
    }
    .viewport-header {
        color: white;
        position: relative;
        background: rgba(0, 0, 0, 0.979);
        background: radial-gradient(circle, rgba(0, 0, 0, 0.123) 0%, rgba(41, 41, 41, 0.651) 75%);
        height: 100vh;
        text-align: center;
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: center;
        z-index: 0;
}
.header-caption{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
}
.header-logo{
    border-radius: 10px;
}
.header-caption > h1{
    width: 90%;

}
.card > h2{
    margin: 0;
    width: 100%;
}
.card > p{
    width: 80%;
}
.header-caption > h1
{
    width: 100%;
}
.header-caption > h2
{
    margin-top: 0;
    width: 100%;
}
.cardsection{
    height: 50vh;
}
.cardboard{
    display: flex;
    justify-content: space-around;
    align-items: center;
    height: 50vh;
}
.card{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-content: center;
    border-radius: 10px;
    width: 20%;
    box-shadow: rgba(17, 17, 26, 0.1) 0px 4px 16px, rgba(17, 17, 26, 0.1) 0px 8px 24px, rgba(17, 17, 26, 0.1) 0px 16px 56px;
    text-align: center;
    height: 300px;
    transition: transform 0.6s,background-color 0.6s,color 0.6s;
    cursor: pointer;
}
.card:hover{
    transform: translateY(10px);
    color: white;
    background-color: #3b2e5a;
}
.card > img{
    width: 100px;
}

.webheadersection{
    height: 50vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background-size: 300% 300%;
  background-image: linear-gradient(90deg, #9d02fd 0%, #515ada 100%, #510c8a 100%);
  -webkit-animation: AnimateBG 10s ease infinite;
          animation: AnimateBG 10s ease infinite;
}

@-webkit-keyframes AnimateBG {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

@keyframes AnimateBG {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}


.webheader{
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    height: 25vh;
    
}
.webheader > h2{
    text-align: center;
    margin: 0;
    width: 60%;
    color: white;
}
.webheader > p{
    font-family: 'Open Sans', sans-serif;
    text-align: center;
    margin: 0;
    width: 60%;
    font-size: 3rem;
    color: #fff48f;
}

.slideshowsection{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}
.slideshow{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
}
.slidecontent{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 80%;
}
.slidecontent-img{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 40%;
}
.slidecontent-img > img{
    width: 80%;
}
.slidecontent-caption{
    width: 40%;
    height: 100%;
}
.slidecontent-caption > h2{
    width: 100%;
}
.slidecontent-caption > p{
    width: 100%;
}
.changepage {
  background-color: #ddd;
  color: #000000;
  border-radius: 50%;
  padding: 15px 20px 15px 20px;
  border: none;
  font-weight: 600;
  transition: all 0.4s;
}
.changepage:hover {
  background-color: #3b2e5a;
  color: #fff48f;
}

.contentimagesection{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.contentimage-container{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 80%;
    box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    background-color: white;
    border-radius: 15px;
    transition: all 0.5s;
}
.contentimage-container:hover{
    transform: translateY(10px);
}

.contentimage-caption{
    display: flex;
    justify-content: flex-start;
    flex-wrap: wrap;
    width: 30%;
}
.contentimage-caption > h2{
    font-size: 3rem;
    margin: 0 0 0 0;
    padding-left: 50px;
}
.contentimage-caption > p{
    font-size: 1.2rem;
    padding-left: 50px;
    padding-right: 80px;
}
.contentimage-image{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 70%;
    
}
.contentimage-image > img{
    width: 100%;
    border-top-right-radius: 15px;
    border-bottom-right-radius: 15px;
}

.techstacksection{
    display: flex;
    justify-content: center;
    align-items: flex-start;
    height: 80vh;
}
.techstack{
    text-align: center;
    width: 60%;
}
.techstack > h2{
    font-size: 2rem;
    color: #530ef3;
}
.techstack > h1{
    font-size: 3rem;
}
.techstack-menu{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    list-style-type: none;
}
.techstack-menu::after{
    content: '';
    display: block;
    width: 100%;
    height: 1px;
    background: #4b4b4b;
}

.techstack-menu > li{
    list-style-type: none;
    margin-left: 20px;
    margin-right: 20px;
}
.techstack-menu > li > a{
    text-align: center;
    list-style-type: none;
    display: inline-block;
    color: #000;
    text-decoration: none;
    cursor: pointer;

}
.techstack-menu > li > a::after{
    content: '';
    display: block;
    width: 0;
    height: 3px;
    background: #3b2e5a;
    transition: width .3s;
}
.techstack-menu > li > a:hover::after{
    width: 100%;
}
.techstack-menu > li > a:focus::after{
    width: 100%;
}
.techstack-image{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    width: 100%;
}
.techstack-image > img{
    width: 20%;
    height: 150px;
    box-shadow: rgba(50, 50, 93, 0.25) 0px 13px 27px -5px, rgba(0, 0, 0, 0.3) 0px 8px 16px -8px;
    margin: 20px;
    transition: all 0.5s;
}
.techstack-image > img:hover{
    transform: scale(1.2);
}

.boardcenter{
    justify-content: center;
}
.longsize{
    width: 25%;
    margin-right: 50px;
}
</style>
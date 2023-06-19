<script>
  import { onMount } from "svelte";
  import { fade } from "svelte/transition";
  import { checkpage } from "./store.js";

  let ready = false;
  let check;
  let hamburger = 1;
  let y = 0;
  onMount(() => (ready = true));

  checkpage.subscribe((value) => {
    check = value;
  });


</script>

<svelte:window bind:scrollY={y} />

<nav>
  {#if ready && y == 0 && check == 1}
    <div class="navbar" transition:fade={{ duration: 500 }}>
      <div class="navbar-logo-container">
        <img
          class="navbar-logo"
          width="50px"
          height="50px"
          src="/logo.png"
          alt="logo"
        />
        <p>Import star</p>
      </div>
      <div class="hamburger">
        {#if ready && hamburger == 1}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <p on:click={()=>{
          hamburger = 0;
          console.log(y);
        }}>☰</p>
        {:else}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <p on:click={()=>{
          hamburger = 1;
          console.log(y);
        }}>X</p>
        {/if}
      </div>
      <ul class="menu">
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="/">Home</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="/about">About</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="/Service">Service</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="Portfolio">Portfolio</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="Contactus">Contact Us</a></li>
      </ul>
    </div>

  {:else if ready && y > 10}
    <div class="navbar-white" transition:fade={{ duration: 500 }}>
      <div class="navbar-logo-container">
        <img
          class="navbar-logo"
          width="50px"
          height="50px"
          src="/logo.png"
          alt="logo"
        />
        <p>Import star</p>
      </div>
      <div class="hamburger">
        {#if ready && hamburger == 1}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <p on:click={()=>{
          hamburger = 0;
          console.log(y);
        }}>☰</p>
        {:else}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <p on:click={()=>{
          hamburger = 1;
          console.log(y);
        }}>X</p>
        {/if}
      </div>
      <ul class="menu">
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="/">Home</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="/about">About</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="/Service">Service</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="Portfolio">Portfolio</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="Contactus">Contact Us</a></li>
      </ul>
    </div>
  {:else}
    <div class="navbar-white" transition:fade={{ duration: 500 }}>
      <div class="navbar-logo-container">
        <img
          class="navbar-logo"
          width="50px"
          height="50px"
          src="/logo.png"
          alt="logo"
        />
        <p>Import star</p>
      </div>
      <div class="hamburger">
        {#if ready && hamburger == 1}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <p on:click={()=>{
          hamburger = 0;
        }}>☰</p>
        {:else}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <p on:click={()=>{
          hamburger = 1;
        }}>X</p>
        {/if}
      </div>
      <ul class="menu">
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="/">Home</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="/about">About</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="/Service">Service</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="Portfolio">Portfolio</a></li>
        <li class="menu-li"><a on:click={()=>{hamburger = 1}} href="Contactus">Contact Us</a></li>
      </ul>
    </div>
  {/if}
</nav>

{#if hamburger == 0}
<ul class="menu-hamburger" transition:fade={{ duration: 500 }}>
  <li class="ham-li"><a href="/" on:click={()=>{hamburger = 1}}>Home</a></li>
  <li class="ham-li"><a href="/about" on:click={()=>{hamburger = 1}}>About</a></li>
  <li class="ham-li"><a href="/Service" on:click={()=>{hamburger = 1}}>Service</a></li>
  <li class="ham-li"><a href="Portfolio" on:click={()=>{hamburger = 1}}>Portfolio</a></li>
  <li class="ham-li"><a href="Contactus" on:click={()=>{hamburger = 1}}>Contact Us</a></li>
</ul>
{/if}

<slot class="xxx" />

<footer>
  {#if ready}
    <div class="footer" transition:fade={{ duration: 2000 }}>
      <div class="footer-leftside">
        <ul class="footer-navigator">
          <li class="footer-li"><a href="/">Home</a></li>
          <li class="footer-li"><a href="/about">About</a></li>
          <li class="footer-li"><a href="/service">Service</a></li>
          <li class="footer-li"><a href="/portfolio">Portfolio</a></li>
          <li class="footer-li"><a href="/blog">Blog</a></li>
          <li class="footer-li"><a href="/contactus">Contact Us</a></li>
        </ul>
        <div class="footer-detail">
          <h2>IMPORT STAR CO., LTD.</h2>
          <h2>ADDRESS:</h2>
          <p>49/12 Nipatsongkrew 1 soi 6 Rd,Hatyai, Hatyai, Songkhla 90110</p>
          <h2>CUSTOMER SERVICE:</h2>
          <p>++66830143609</p>
          <h2>EMAIL:</h2>
          <p>contact@importstar.dev</p>
        </div>
      </div>
      <div class="footer-rightside">
        <div class="footer-logo">
          <img src="logo.png" alt="" srcset="" />
        </div>
        <p>© 2010 - 2020 Privacy - Terms</p>
      </div>
    </div>
  {/if}
</footer>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Kanit:wght@300;600&display=swap");
  

  /* width */
  :global(::-webkit-scrollbar) {
    width: 10px;
  }

  /* Track */
  :global(::-webkit-scrollbar-track) {
    background: #f1f1f1;
  }

  /* Handle */
  :global(::-webkit-scrollbar-thumb) {
    background: #888;
  }

  /* Handle on hover */
  :global(::-webkit-scrollbar-thumb:hover) {
    background: #555;
  }

  :global(body) {
    font-family: "Kanit", sans-serif;
    margin: 0;
    padding: 0;
  }

  div.navbar {
    color: white;
    position: fixed;
    background-color: transparent;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    align-items: center;
    width: 100%;
    height: 100px;
    z-index: 3;
  }
  div.navbar-white {
    color: rgb(0, 0, 0);
    position: fixed;
    background-color: white;
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    height: 100px;
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    z-index: 3;
  }
  .navbar-logo-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .navbar-logo-container > p {
    margin-left: 10px;
  }
  .navbar-logo {
    border-radius: 5px;
  }
  div.hamburger{
    cursor: pointer;
    display: none;
  }
  ul.menu-hamburger{
    display: none;
    background-color: black;
    position: fixed;
    list-style-type: none;
    z-index: 2;
    width: 100%;
    margin: 0;
    padding-top: 100px;
    padding-left: 0;
    text-align: center;
    height: 100vh;
  }
  ul.menu-hamburger > li{
  margin-top: 10px;
  }
  ul.menu-hamburger > li:last-child{
  padding-bottom: 10px;
  }
  ul.menu-hamburger > li > a{
  color: white;
  border-bottom: 1px solid white;
  }
  ul.menu-hamburger > li > a:hover{
  color: #fdf28e;
  border-bottom: 1px solid #fdf28e;
  }
  div.footer {
    background-color: rgb(255, 255, 255);
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 160px;
  }
  li.footer-li > a {
    color: black;
    transition: all 0.3s;
  }
  li.footer-li > a:hover {
    color: rgb(150, 150, 150);
  }
  ul.footer-navigator {
    display: flex;
    font-size: 0.8rem;
    flex-direction: column;
    justify-content: center;
    list-style-type: none;
    padding-left: 0;
    margin: 0;
  }
  .footer-leftside {
    display: flex;
    justify-content: space-around;
    width: 30%;
    border-right: 1px solid;
  }
  .footer-detail {
    margin-left: 20px;
    font-size: 0.3rem;
  }
  .footer-detail > h2 {
    font-size: 0.5rem;
  }
  .footer-rightside {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 30%;
  }
  .footer-logo > img {
    width: 80px;
  }

  ul.menu {
    display: flex;
    justify-content: center;
    padding: 0;
    margin: 0;
    list-style-type: none;
  }
  li.menu-li {
    margin-left: 30px;
  }
  li.menu-li:hover {
    text-decoration: underline;
  }
  a {
    text-decoration: none;
    color: rgb(255, 255, 255);
  }

  
  @media screen and (max-width: 1200px) {
    .footer {
      height: 100%;
      flex-wrap: wrap;
    }
    .footer-leftside {
      width: 61%;
      border-right: 0px;
      border-bottom: 1px solid;
      margin-bottom: 10px;
    }
    .footer-navigator {
      width: 100%;
    }
    .footer-detail {
      width: 100%;
    }
    .footer-rightside {
      width: 40%;
    }
    .footer-rightside > p {
      text-align: center;
    }
  }

  @media screen and (max-width: 600px) {
   ul.menu{
    display: none;
   }
   div.hamburger{
    display: block;
    width: 20px;
   }
   .hamburger > p{
    text-align: center;
   }
   ul.menu-hamburger{
    display: block;
   }
  }
 
</style>

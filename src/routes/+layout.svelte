<script>
    import { onMount } from 'svelte';
    import { fade } from 'svelte/transition';
    import {checkpage} from './store.js';

    let ready = false;
    let check;
    let y = 0;
    onMount(() => ready = true);
    
    checkpage.subscribe(value=>{
        check = value
    })
</script>

<svelte:window bind:scrollY={y}/>

<nav>
{#if ready && y == 0 && check == 1}
    <div class="navbar" transition:fade={{duration:500}}>
    <div class="navbar-logo-container">
        <img class="navbar-logo" width="50px" height="50px" src="/logo.png" alt="logo">
        <p>Import star</p>
    </div>
        <ul class="menu">
            <li class="menu-li"><a href="/">Home</a></li>
            <li class="menu-li"><a href="/about">About</a></li>
            <li class="menu-li"><a href="/Service">Service</a></li>
            <li class="menu-li"><a href="Portfolio">Portfolio</a></li>
            <li class="menu-li"><a href="Contactus">Contact Us</a></li>
        </ul>
    </div>
{:else if ready && y > 10}
<div class="navbar-white" transition:fade={{duration:500}}>
    <div class="navbar-logo-container">
        <img class="navbar-logo" width="50px" height="50px" src="/logo.png" alt="logo">
        <p>Import star</p>
    </div>
        <ul class="menu">
            <li class="menu-li"><a class="scroll" href="/">Home</a></li>
            <li class="menu-li"><a class="scroll" href="/about">About</a></li>
            <li class="menu-li"><a class="scroll" href="/Service">Service</a></li>
            <li class="menu-li"><a class="scroll" href="Portfolio">Portfolio</a></li>
            <li class="menu-li"><a class="scroll" href="Contactus">Contact Us</a></li>
        </ul>
    </div>
{:else}
<div class="navbar-white" transition:fade={{duration:500}}>
    <div class="navbar-logo-container">
        <img class="navbar-logo" width="50px" height="50px" src="/logo.png" alt="logo">
        <p>Import star</p>
    </div>
        <ul class="menu">
            <li class="menu-li"><a class="scroll" href="/">Home</a></li>
            <li class="menu-li"><a class="scroll" href="/about">About</a></li>
            <li class="menu-li"><a class="scroll" href="/Service">Service</a></li>
            <li class="menu-li"><a class="scroll" href="Portfolio">Portfolio</a></li>
            <li class="menu-li"><a class="scroll" href="Contactus">Contact Us</a></li>
        </ul>
    </div>
{/if}
</nav>


<slot></slot>

<footer>
{#if ready}
    <div class="footer" transition:fade={{duration:2000}}>
        <div class="footer-leftside">
            <div class="footer-logo">
                <img class="footer-imglogo" width="40px" src="/logo.png" alt="logo">
                <p>import star co., ltd.</p>
            </div>
            <div class="footer-quotation">
                <p>Let us help you find your IT solution.</p>
            </div>
        </div>
        <div class="footer-rightside">
            <div class="footer-contactus">
                <p>Contact Us</p>
                <ul class="footer-contact-menu">
                    <li><a href="/">logo</a></li>
                    <li><a href="/">Home</a></li>
                    <li><a href="/about">About</a></li>
                </ul>
            </div>
        </div>
    </div>
{/if}
</footer>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Kanit:wght@300;600&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@600&display=swap');

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
        font-family: 'Kanit', sans-serif;
        margin: 0; 
        padding: 0;
    }
    div.navbar{
        color: white;
        position: fixed;
        background-color: transparent;
        display: flex;
        justify-content: space-around;
        align-items: center;
        width: 100%;
        height: 100px;
        z-index: 1;
    }
    div.navbar-white{
        color: rgb(0, 0, 0);
        position: fixed;
        background-color: white;
        display: flex;
        justify-content: space-around;
        align-items: center;
        width: 100%;
        height: 100px;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
        z-index: 1;
    }
    .navbar-logo-container{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .navbar-logo-container > p{
        margin-left: 10px;
    }
    .navbar-logo{
        border-radius: 5px;
    }
    div.footer{
        background-color: rgb(255, 255, 255);
        display: flex;
        justify-content: center;
        align-items: flex-start;
        width: 100%;
        height: 160px;
    }
    .footer-leftside{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 40%;
        flex-wrap: wrap;
    }
    .footer-logo{
        display: flex;
        justify-content: flex-start;
        align-items: center;
        width: 100%;
    }
    .footer-logo > p{
        margin-left: 10px;
    }
    .footer-imglogo{
        border-radius: 5px;
    }
    .footer-quotation{
        width: 100%;
    }
    .footer-quotation > p{
        margin: 0;
    }
    .footer-rightside{
        width: 40%;
    }
    ul.menu{
        display: flex;
        justify-content: center;
        padding: 0;
        margin: 0;
        list-style-type: none;
    }
    li.menu-li{
        margin-left: 30px;
    }
    li.menu-li:hover{
        text-decoration: underline;
    }
    a{
        text-decoration: none;
        color: rgb(255, 255, 255);
    }
    a.scroll{
        color: black;
    }
    ul.footer-contact-menu{
        list-style-type: none;
        padding-left: 0;
    }
    
</style>
<script setup>
    fetch("https://fakestoreapi.com/products")
    .then(res => res.json())
    .then(data => {
        for (let i = 0; i < data.length; i++) {
            // console.log(data[i].image)
        };
        console.log("check",data[0].image );
    });
    function show(){
        document.getElementById("mobile").style.display = "block";
        document.getElementById("mobile").style.right = "0";
    }
    function close(){
        document.getElementById("mobile").style.display = "none";
    }
</script>
<template>
    <div id="container" ref="container">
        <header>
        <div>
            <h3>SOFT</h3>
        </div>
        <div id="go">
            <a href="#">HOME</a>
            <a href="#">ABOUT</a>
            <a href="#">PRODUCTS</a>
            <a href="#">CONTACT</a>
        </div>
        <div>
            <i class="fa-solid fa-cart-shopping"></i>
            <button id="get">Get Started</button>
            <i class="fa-solid fa-bars" id="hamburger" @click="show"></i>
        </div>
    </header>
    </div>
    <section id="mobile">
        <i class="fa-solid fa-xmark" @click="close"></i>
        <div>
            <a href="#">HOME</a>
            <a href="#">ABOUT</a>
            <a href="#">PRODUCTS</a>
            <a href="#">CONTACT</a>
            <button id="mget">Get Started</button>
        </div>
    </section>
    
</template>

<style scoped>
    *{
        padding: 0;
        margin: 0;
        box-sizing: border-box;
    }
    h3{
        font-family: Arial, Helvetica, sans-serif;
        letter-spacing: 12px;
    }
    h3::first-letter{
        color: #134544;
        text-shadow: 0px 0px 5px white;
        font-weight: bold;
        font-size: 30px;
    }
    #container{
        width: 100%;
        min-height: 90vh;
        background-position: center 40px;
        background-repeat: no-repeat;
        background-size: contain;
        background-image: url("product4.jpg");
        background-color: #134544;
        background-blend-mode: multiply;
        /* background- */
        header{
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            width: 100%;
            color: white;
            div{
                color: white;
                font-family: Arial, Helvetica, sans-serif;
                /* display: flex;
                align-items: center; */
                a{
                    text-decoration: none;
                    margin-right: 25px;
                    color: white;
                }
                button{
                    padding: 12px 25px;
                    background-color: white;
                    border: none;
                    color: #134544;
                    border-radius: 10px;
                    cursor: pointer;
                    margin-left: 30px;
                }
            }
        }
    }
    #hamburger, #mobile{
        display: none;
    }
    
    @media screen and (max-width: 750px){
        #go{
            display: none;
        }
        #hamburger{
            margin-left: 20px;
            display: inline-block;
        }
        #mobile{
            position: absolute;
            right: 10px;
            display: none;
            top: 8px;
            min-width: 30%;
            height: 100vh;
            padding-left: 10px;
            background-color: white;
            padding-top: 10px;
            transition: all 2.5s ease;
            > div{
                display: flex;
                flex-direction: column;
                gap: 50px;
                margin-top: 50px;
                > a{
                    text-decoration: none;
                    color: #134544;
                    font-family: Arial, Helvetica, sans-serif;
                }
            }
        }
        #get{
            display: none;
        }
        #mget{
            padding: 12px 25px;
            background-color: white;
            border: none;
            color: #134544;
            border-radius: 10px;
            cursor: pointer;
            margin-left: 30px;
        }
    }
</style>
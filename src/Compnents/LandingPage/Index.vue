<script setup>
    import Header from '../Header/Header.vue';
    import product4 from "./product4.jpg";
    fetch("https://fakestoreapi.com/products")
    .then(res => res.json())
    .then(data => {
        // console.log(data)
        const house = document.getElementById("houses");
        data.forEach(item => {
        const fdiv = document.createElement("div");
        fdiv.style.display = "flex";
        fdiv.style.flexDirection = "column";
        fdiv.style.alignItems = "center";
        fdiv.style.maxWidthwidth = "28%";
        fdiv.style.rowGap = "20px";
        fdiv.style.paddingBottom = "30px";
        // const h3 = document.createElement("h3");
        // h3.innerHTML = `${item.title}`;
        const nav = document.createElement("nav");
        nav.style.backgroundColor = "rgba(0,0,0,0.1)";
        nav.style.padding = "20px";
        nav.style.display = "flex";
        nav.style.justifyContent = "center";
        nav.style.alignItems = "center";
        const img = document.createElement("img");
        img.style.display = "block";
        img.src = `${item.image}`;
        nav.appendChild(img);
        nav.style.minHeight = "30vh";
        img.style.objectFit = "containe";
        img.style.mixBlendMode = "color-burn";
        img.style.width = "35%";
        // const p = document.createElement("p");
        // p.innerHTML = `${item.description}`;
        const li = document.createElement("li");
        li.innerHTML = `$${item.price}`;
        li.style.listStyleType = "none";
        const button = document.createElement("button");
        button.style.padding = "10px 20px";
        button.style.background = "#134544";
        button.style.color = "white";
        button.innerHTML = "Add to Cart";
        button.style.border = "none";
        button.style.borderRadius = "4px";
        button.style.cursor = "pointer";
        fdiv.append(nav, li, button);

        house.appendChild(fdiv);
        });
    });
</script>

<template>
    <Header/>
    <span>New Arrivals</span>
    <div id="houses">
    </div>
</template>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&family=Playwrite+AU+QLD:wght@100..400&display=swap');
    *{
        padding: 0;
        margin: 0;
        box-sizing: border-box;
    }
    span{
        display: block;
        margin: 70px 0px;
        text-align: center;
        font-size: 25px;
        letter-spacing: 5px;
        font-family: sans-serif;
    }
    #houses{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        margin-top: 50px;
    }
   
    @media screen and (max-width: 750px){
        
    }
</style>
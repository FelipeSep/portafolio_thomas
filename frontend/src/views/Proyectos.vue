<template>
    <div id="image-track" data-mouse-down-at="0" data-prev-percentage="0">
    <!--<img class="image" v-for="image in itemsProyectos"  :src="image.url" draggable="false" />-->
    <img class="image" src="https://images.unsplash.com/photo-1610194352361-4c81a6a8967e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1674&q=80" draggable="false" />
    <img class="image" src="https://images.unsplash.com/photo-1618202133208-2907bebba9e1?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1770&q=80" draggable="false" />
    <img class="image" src="https://images.unsplash.com/photo-1495805442109-bf1cf975750b?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1770&q=80" draggable="false" />
    <img class="image" src="https://images.unsplash.com/photo-1548021682-1720ed403a5b?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1770&q=80" draggable="false" />
    <img class="image" src="https://images.unsplash.com/photo-1496753480864-3e588e0269b3?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2134&q=80" draggable="false" />
    <img class="image" src="https://images.unsplash.com/photo-1613346945084-35cccc812dd5?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1759&q=80" draggable="false" />
    <img class="image" src="https://images.unsplash.com/photo-1516681100942-77d8e7f9dd97?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1770&q=80" draggable="false" />
  </div>
  </template>
  
  <script>
  import axios from "axios";
  export default {
  
      data: () => ({

        itemsProyectos:[],
      }),
      mounted(){
          //mouse shit
          const track = document.getElementById("image-track");
  
          //presionar el mouse
          window.onmousedown = e => {
              track.dataset.mouseDownAt = e.clientX;
          }
          window.onmouseup = e => {
              track.dataset.mouseDownAt = "0";
              track.dataset.prevPercentage = track.dataset.percentage;
          }
          //mover el mouse
          window.onmousemove = e => {
              if(track.dataset.mouseDownAt === "0") return;
  
              const mouseDelta = parseFloat(track.dataset.mouseDownAt) - e.clientX,
              maxDelta = window.innerWidth / 2;
  
              const percentage = (mouseDelta / maxDelta) * -100,
                  nextPercentageUnconstrained = parseFloat(track.dataset.prevPercentage) + percentage,
                  //limites del deslizamiento
                  nextPercentage = Math.max(Math.min(nextPercentageUnconstrained, 0), -100);
                  
                  
              track.dataset.percentage = nextPercentage;
  
              track.animate({
                  transform: `translate(${nextPercentage}%, -50%)`
              }, { duration: 1200, fill: "forwards" });
              
              for(const image of track.getElementsByClassName("image")) {
                  image.animate({
                  objectPosition: `${100 + nextPercentage}% center`
                  }, { duration: 1200, fill: "forwards" });
              }
              
              //track.style.transform = `translate(${nextPercentage}% , -50%)`;            
          }
          
          },
          created(){
             
          }
  }
  
  </script>
  
  <style>
      body {
      height: 100vh;
      width: 100vw;
      background-color: black;
      margin: 0rem;
      overflow: hidden;
      }
  
      #image-track > .image {
      width: 50vmin;
      height: 65vmin;
      object-fit: cover;
      object-position: 100% center;
      }
  
      #image-track {
      display: flex;
      gap: 4vmin;
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-15%, -50%); 
      user-select: none; /* -- Prevent image highlighting -- */
      }
  
  </style>
---
layout:post
title: moving box
---

<html lang="en">
<head>
    <meta charset="UTF-8"></meta>
    <meta content="IE=edge" http-equiv="X-UA-Compatible"></meta>
    <meta content="width=device-width, initial-scale=1.0" name="viewport"></meta>
    <style>
        .box{
            width:100px;
            height:100px;
            background-color:rgb(230, 116, 96);
            border:5px solid pink;
            cursor: pointer;
        }
    </style>
    <title>Document</title>
</head>
<body>
    <div class="box"></div>
<script>
   const $box = document.querySelector('.box');

   const initialMousePos = {x:0 , y:0};
   const offset = {x:0 , y:0};

   const move = e => {
       offset.x = e.clientX - initialMousePos.x;
       offset.y = e.clientY - initialMousePos.y;

       $box.style.transform = `translate3d(${offset.x}px,${offset.y}px,0)`;
   }
   $box.addEventListener('mousedown', e=>{
       initialMousePos.x = e.clientX - offset.x;
       initialMousePos.y = e.clientY - offset.y;

     document.addEventListener('mousemove',move);
   });

   $box.addEventListener('mouseup',() => {
       document.removeEventListener('mousemove',move);
   })
</script>
</body>
</html>

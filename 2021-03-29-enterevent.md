---
layout: post
title:  "how to use enterkey"
---
 
* 1. enterkey 작성하기 basic 
  <body>
  <input type = "text">
    <button type= "submit">입력</button>
    <em id= "message"></em>
  <script>
  $content.onkeyup = e => {
            if(e.key !== 'Enter') return;

            $msg.textContent = e.target.value;
            e.target.value='';
                };
  </script>
  </body>
*    
* 2. enterkey 작성하기 + node에 저장 
    <body>
    <input type = "text">
    <button type= "submit">입력</button>
    <em id= "message"></em>
    <script>
    $input.onkeyup = e => {
           if(e.key !== 'Enter') return;
           const p = document.createElement('p');
           const entercontent = document.createTextNode(`${e.target.value}`);
           p.appendChild(entercontent);
           $msg.appendChild(p);
           e.target.value = '';
           };
    </script>
    </body>
           
       

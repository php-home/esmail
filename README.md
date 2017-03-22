# esmail
发送邮件通知的应用，可通过http方式发送邮件，也可以通过web界面发送邮件，同时保留发送记录和支持管理联系人，安装要求php－5.5以上环境和elasticsearch

安装步骤
   下载源码将nginx 目录指向源码下的www目录，配置nginx rewrite条件
   server {
        listen       80;

        root           /usr/local/www;

        location ~* \.(ico|css|js|gif|jpe?g|png|woff2?|ttf|swf){

        }
        location / {
            fastcgi_pass   127.0.0.1:9000;
            fastcgi_index  index.php;
            fastcgi_param  SCRIPT_FILENAME  $document_root/index.php;
            include        fastcgi_params;
        }

    }

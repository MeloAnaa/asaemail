FROM ubuntu:latest

RUN apt-get update  

RUN apt-get upgrade -y

RUN apt-get install postfix -y

RUN apt-get install dovecot-imapd dovecot-pop3d -y

RUN apt install -q -y syslog-ng

#CMD ["sh", "-c", "/sbin/postfix start", "tail -f /var/log/maillog"]

COPY main.cf /etc/postfix

COPY ./dovecot/10-auth.conf /etc/dovecot/conf.d


RUN useradd -m bob
RUN useradd -m patrick

RUN echo "bob:redes" | chpasswd
RUN echo "patrick:redes" | chpasswd


#CMD ["postfix", "start-fg"]
CMD ["sh", "-c", "service postfix start; service syslog-ng start; service dovecot start; tail -F /var/log/mail.log"]



##comandos testar###
#telnet "ip" 25             
#helo mail.asa.br
#mail from: bob@asa.br
#rcpt to: patrick@asa.br
#data
#oi este é um email
#quit

#OU telnet "ip" 110
#comando para pop:
#user bob
#list




##VER LOGS DE EMAILS (cada arquivo é a caixa de email de cada usuario)
#docker exec -it email /bin/bash 
#cd /var/spool/mail
#ls -la
##os emails novos que estao chegando sao colocados no inicio do arquivo






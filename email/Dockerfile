FROM ubuntu:latest

RUN apt-get update -y

RUN apt-get upgrade -y

RUN apt-get install postfix -y

#CMD ["sh", "-c", "/sbin/postfix start", "tail -f /var/log/maillog"]


COPY main.cf /etc/postfix

RUN useradd -m bob
RUN useradd -m sales

RUN echo "bob:redes" | chpasswd
RUN echo "patrick:redes" | chpasswd




#RUN useradd -c 'user bob' -m -s /bin/false bob

#RUN echo -e "pwd123" | passwd bob

#RUN useradd -c 'user patrick' -m -s /bin/false patrick

#RUN echo -e "pwd123" | passwd patrick


CMD ["postfix", "start-fg"]


##comandos testar###
#telnet "ip" 25
#helo eu
#helo mail.asa.br
#mail from: bob@asa.br
#rcpt to: redes@asa.br
#data
#oi este é um email
#quit



# TACACS-RADIUS

[PT/BR]<br><br>
Configure o TACACS e o RADIUS da seguinte maneira:

Servidor:
1) Adicione R1 como um cliente TACACS:
- Nome do cliente = R1
- IP do cliente = 10.1.1.254
- Segredo = cisco
- Tipo = TACACS

2) Adicione R2 como um cliente RADIUS:
- Nome do cliente = R2
- IP do cliente = 10.1.1.253
- Segredo = cisco
- Tipo = RAIO

3) Adicione S1 como um cliente TACACS:
- Nome do cliente = S1
- IP do cliente = 10.1.1.252
- Segredo = cisco
- Tipo = TACACS

4) Adicionar usuário:
- Use seu próprio nome como nome de usuário
- Senha = cisco

R1:
1) Configure a autenticação aaa (para login e habilitação) usando TACACS com o servidor 10.1.1.250.
Use autenticação local como backup com nome de usuário "backup" e senha "cisco"
2) Teste se você pode fazer login usando seu próprio nome

R2:
1) Configure a autenticação aaa (para login e habilitação) usando RADIUS com servidor 10.1.1.250.
Use autenticação local como backup com nome de usuário "backup" e senha "cisco"
2) Teste se você pode fazer login usando seu próprio nome

S1
1) Configure a autenticação aaa (para login e habilitação) usando TACACS com o servidor 10.1.1.250.
 Use autenticação local como backup com nome de usuário "backup" e senha "cisco"
2) Teste se você pode fazer login usando seu próprio nome

Verificação:
1) Você deve ser capaz de fazer login em todos os dispositivos de rede usando seu próprio nome.
2) Crie outro usuário no servidor e verifique se o novo usuário também pode fazer login
3) Verifique se o usuário de backup local não pode fazer login enquanto o servidor estiver acessível
4) Desabilite a porta do switch para o servidor.
Verifique se você pode fazer login usando a conta de backup local.
5) Habilite a porta do switch e verifique se o usuário de backup agora não pode mais fazer login,
 mas você pode entrar com seu nome.

Simulação:
1) Verifique se, ao fazer login como seu próprio usuário, as mensagens TACACS e RADIUS são
 enviado entre o switch e o servidor

[ENG]<br><br>
Configure TACACS and RADIUS as follows:

Server:
1) Add R1 as a TACACS client:
- Client Name = R1
- Client IP = 10.1.1.254
- Secret = cisco
- Type = TACACS

2) Add R2 as a RADIUS client:
- Client Name = R2
- Client IP = 10.1.1.253
- Secret = cisco
- Type = RADIUS

3) Add S1 as a TACACS client:
- Client Name = S1
- Client IP = 10.1.1.252
- Secret = cisco
- Type = TACACS

4) Add user:
- Use your own name as the username
- Password = cisco

R1:
1) Configure aaa authentication (for login and enable) using TACACS with server 10.1.1.250.
Use local authentication as a backup with username "backup" and password "cisco"
2) Test that you can login using your own name

R2:
1) Configure aaa authentication (for login and enable) using RADIUS with server 10.1.1.250.
Use local authentication as a backup with username "backup" and password "cisco"
2) Test that you can login using your own name

S1
1) Configure aaa authentication (for login and enable) using TACACS with server 10.1.1.250.
 Use local authentication as a backup with username "backup" and password "cisco"
2) Test that you can login using your own name

Verification:
1) You should be able to login to all network devices using your own name.
2) Create another user on the server and verify that the new user can also login
3) Verify that the local backup user cannot login while the server is reachable
4) Disable the port on the switch to the server. 
Verify that you can login using the local backup account.
5) Enable the switch port and verify that the backup user can now no longer login,
 but you can login with your name.

Simulation:
1) Verify that when you login as your own user, that TACACS and RADIUS messages are
 sent between the switch and the server

<img src="https://raw.githubusercontent.com/MattheusMartins/TACACS-RADIUS/main/1.PNG">

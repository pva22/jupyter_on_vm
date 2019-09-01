# jupyter_on_vm
У меня была частая проблема запустить jupyter notebook на виртуальной машине. Из-за того, что виртуальные машины приходится удалять и создавать очень часто, проблема быстрой настройки становится ещё острее

Здесь собраны шаги, которые помогли мне запустить подлючиться к jupyter notebook на виртуальной машине. Информация из статей:
https://medium.com/@alexjsanchez/python-3-notebooks-on-aws-ec2-in-15-mostly-easy-steps-2ec5e662c6c6
https://www.digitalocean.com/community/tutorials/how-to-install-run-connect-to-jupyter-notebook-on-remote-server


1. wget https://repo.anaconda.com/archive/Anaconda3-2018.12-Linux-x86_64.sh
2. bash Anaconda3-2018.12-Linux-x86_64.sh
3. vim .bashrc
4. export PATH="/home/ubuntu/anaconda3/bin:$PATH" (перед вставкой нажать "i", затем esc :wq)
5. source .bashrc
6. vim .ssh/config
7. Host ec2
    Hostname **your-ec2’s-public-ip-address here**
    User ubuntu
    IdentityFile ~/tutorialexample.pem
    (перед вставкой нажать "i", затем esc :wq)
8. jupyter notebook --no-browser

PUTTY SSH Tunneling(для Windows)


подключение как обычно, только > SSH > Tunnels

Sourse port: 8000, Destination localhost:8888, нажать Add и Open

SSH Tunneling (Для Mac)

ssh -L 8000:localhost:8888 sammy@your_server_ip



# Linux  
https://github.com/virtua10ne/wannabe_devops/blob/main/linux.md  
Курс "Linux Basic" от Rebrain, сертификат, "сохранёнки" и подготовка к экзамену LPIC.  

# Git  
Курс "Основы Git" от Яндекс Практикум  
https://github.com/virtua10ne/wannabe_devops/blob/main/git.md  

# Docker  
Изучаю Докер по курсу от Яндекс Практикум  
https://github.com/virtua10ne/wannabe_devops/blob/main/docker.md  

# Yandex Cloud  
Изучаю облако Яндекс по курсу "Инженер облачных сервисов" от Яндекс Практикум, получаю сертификат.  
https://github.com/virtua10ne/wannabe_devops/blob/main/yandex_cloud.md


# Roadmap.sh projects  
## roadmap.sh ssh-remote-server-setup project results  
- Project: https://roadmap.sh/projects/ssh-remote-server-setup   
- GitHub: https://github.com/virtua10ne/wannabe_devops  
  
### Full connection syntax works:  
```
ssh -i D:\VMs\YC\VM1\ssh_keys crazydiamond@89.169.151.17  
```
  
### Alias for server is made and connection 'ssh myserv1' works:  
```
Host myserv1  
  Hostname 89.169.151.17  
  User crazydiamond  
  Port 22  
  IdentityFile D:\VMs\YC\VM1\ssh_keys  
  IdentitiesOnly yes  
```
  
### Server up and runnig, Fail2Ban is running:  
```
crazydiamond@compute-vm-2-2-20-hdd-1729889665559:~$ systemctl status fail2ban.service  
● fail2ban.service - Fail2Ban Service  
     Loaded: loaded (/usr/lib/systemd/system/fail2ban.service; enabled; preset: enabled)  
     Active: active (running) since Sat 2024-10-26 07:11:11 UTC; 8min ago  
       Docs: man:fail2ban(1)  
   Main PID: 2800 (fail2ban-server)  
      Tasks: 5 (limit: 2275)  
     Memory: 23.2M (peak: 25.4M)  
        CPU: 672ms  
     CGroup: /system.slice/fail2ban.service  
             └─2800 /usr/bin/python3 /usr/bin/fail2ban-server -xf start  
```

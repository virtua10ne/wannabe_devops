# Resources
- Free MOOC (ru): https://yandex.cloud/ru/training/docker
- Sid Palas Docker big guide: https://courses.devopsdirective.com/docker-beginner-to-pro/lessons/00-introduction/01-main


## cgroups 
Consist of Core for process hierarchy, and cgroups controllers.  
Controllers 1-2 used often.  

1. CPU
2. Memory
3. IO
4. PID (limit fork&clone)
5. сpuset (link cgroup processes to CPU core/NUMA)
6. Device controller
7. RDMA
8. HugeTLB (>2Mi page size)
9. Misc (everything other, CONFIG_CGROUP_MISC)

## Namespaces

1. user namespace (uid, gid)
2. PID namespace
3. network namespace (ips,ports,iptable,conntrack,fw,etc)
4. mount namespace
5. IPC namespace
6. UNIX Time-Sharing (UTS) (hostname,domain)

**nsenter** - run program in different namespaces  

## Install & config
При установке под Windows Docker совсем не интересуется нашими предпочтениями. Что бы явно задать ему директории установки и данных, нужно передать их в следующих параметрах.  
```powershell
Start-Process -Wait -FilePath "Docker Desktop Installer.exe" `
 -ArgumentList "install" `
, "-accept-license" `
, "--installation-dir=D:\VMs\Docker\Docker" `
, "--windows-containers-default-data-root=D:\VMs\Docker"
```
Так же есть параметр `--wsl-default-data-root=D:\\Docker\\wsl` для данных WSL.  


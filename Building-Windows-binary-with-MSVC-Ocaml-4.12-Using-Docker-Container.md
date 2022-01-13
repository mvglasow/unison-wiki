OCaml and opam native Windows Container images for Docker for Windows can be found in the [ocaml/opam](https://hub.docker.com/r/ocaml/opam/tags?page=1&ordering=-name&name=windows) repository in the Docker Hub. This docker container provide the complete setup of OCaml/cygwin64/MSVC environment for building Unison binary in a Windows 64-bit machine. You can make use of this image by getting [Docker Desktop for Windows installed](https://docs.docker.com/docker-for-windows/install/). After installation be sure to [switch Docker to Native Windows Containers](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) before pulling the OCaml+opam Images for Docker for Windows. More details about this docker image announced [here](https://discuss.ocaml.org/t/ann-ocaml-opam-images-for-docker-for-windows/8179). 

## Steps to Setup and Builds
Before the installation, you may want to modify docker images storage location by modify C:\ProgramData\Docker\config\daemon.json
(_if this is a new installation you can create this file in advance like below_):  

    {
        "experimental": false,
        "data-root": "D:\\DockerRoot"
    }
If Docker Desktop for Windows already installed, you can append the "data-root" line, make it point to whatever drive path with enough disk space to hold the current OCaml+opam Images for Docker for Windows which is ~23.5GB. Be sure to append the ',' to the end of "experimental" line above or docker will crash upon re-start.

1. Download and Install [Docker Desktop for Windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows) (Requires Microsoft Windows 10 Professional or Enterprise 64-bit, or Windows 10 Home 64-bit with WSL 2.)
1. Switch to Windows Container (_open the Docker Desktop menu by right-click the Docker icon in the Notifications area or System tray then "Select Switch to Windows containers"_).
1. Open a Windows Command Prompt.
1. Get [OCaml+opam Images for Docker for Windows docker image](https://hub.docker.com/r/ocaml/opam/tags?page=1&ordering=-name&name=windows-msvc-ocaml-4.12) from Docker Hub ocaml/opam repository by enter:  
        `>docker pull ocaml/opam:windows-msvc-ocaml-4.12`

1. It will take quite some time, wait until process finish then enter:  

        >docker images
        REPOSITORY   TAG                       IMAGE ID       CREATED        SIZE
        ocaml/opam   windows-msvc-ocaml-4.12   e69ba8b6bde7   3 months ago   23.5GB

1. Now  create a Container from the above image with Windows Host Folder Access by enter:
(_e.g. C:\Users\Your_Username\Downloads being mount to Docker container C:\cygwin64\home\opam\winfolder_)

        >docker run -it -v C:\Users\Your_Username\Downloads:C:\cygwin64\home\opam\WinFolder ocaml/opam:windows-msvc-ocaml-4.12 ocaml-env exec --64 --ms=vs2019 -- cmd.exe

    (Note: Only execute this command once unless you need to create another container with the same image)  

    You will enter the container environment like below:  

        Microsoft Windows [Version 10.0.19041.1237]
        (c) Microsoft Corporation. All rights reserved.

        C:\cygwin64\home\opam>ls -l
        total 8
        drwxr-xr-x+ 1 Administrators SYSTEM        0 Oct  5 17:39 opam-repository
        drwx------+ 1 Unknown+User   Unknown+Group 0 Jan  8 08:21 winfolder

        C:\cygwin64\home\opam>ls -l winfolder
        total 540137
        -rwx------+ 1 Unknown+User Unknown+Group 519015312 Jan  1 16:12 'Docker Desktop Installer.exe'
    (_As you can see Windows Host C:\Users\Your_Username\Downloads is being mounted to winfolder, files between host and container can be exchanged_)
1. We can exit the Docker Container environment by enter 'exit' or pressing CTRL-C.
1. At this point you are re-enter the Windows Command Prompt.  
If you need to re-enter the container environment you need to know the container ID by enter:  

        >docker ps --all --no-trunc
        CONTAINER ID                                                       IMAGE                                COMMAND                                                                           CREATED         STATUS                      PORTS     NAMES

        eb5a90d15d595b86cfd009a33821a385249448b46ef12d144bde2ef4220eecd0   ocaml/opam:windows-msvc-ocaml-4.12   "ocaml-env exec --64 --ms=vs2019 -- ocaml-env exec --64 --ms=vs2019 -- cmd.exe"   4 minutes ago   Exited (0) 33 seconds ago             silly_mahavira

1. You only need the first 3 digits of the Container ID for re-start the container 'docker start' and re-connect the container 'docker attach' command.  
To restart the Container enter:  

        >docker start eb5
        eb5
        >docker attach eb5

1. You are now re-enter the Container environment, get unison source code by enter:  
        
        >pwd
        /home/opam

        >git clone https://github.com/bcpierce00/unison.git
        Cloning into 'unison'...
        remote: Enumerating objects: 10301, done.
        remote: Counting objects: 100% (799/799), done.
        remote: Compressing objects: 100% (361/361), done.
        remote: Total 10301 (delta 486), reused 643 (delta 413), pack-reused 9502
        Receiving objects: 100% (10301/10301), 16.27 MiB | 1.77 MiB/s, done.
        Resolving deltas: 100% (7718/7718), done.

        >ls -l
        total 4
        drwxr-xr-x+ 1 ContainerAdministrator ContainerAdministrator 0 Jan  8 17:23 unison

    Congratulation, current version of unison "master" branch being downloaded to /home/opam/unison 

1. You can build unison binary from source by enter:

        >cd unison
        >make OSTYPE=cygwin

    If the process exit without error, you will find text user interface version of Windows 64-bit unison.exe and unison-fsmonitor.exe which were compiled with MSVC Ocaml-4.12 in /home/opam/unison/src:  

        >ls -l unison/src/*.exe
        -rwxr-xr-x 1 ContainerAdministrator ContainerAdministrator 1428992 Jan 10 22:10 unison/src/unison-fsmonitor.exe
        -rwxr-xr-x 1 ContainerAdministrator ContainerAdministrator 3142144 Jan 10 22:10 unison/src/unison.exe

   
    To use the binary in Windows, msvcp140.dll is required and need copy to the same folder of unison.exe and unison-fsmonitor.exe, it can be found in this container here:  

        >ls -l \BuildTools/VC/Tools/MSVC/14.29.30133/bin/Hostx86/x86/msvcp140.dll
        -rwxr-xr-x 1 ContainerAdministrator ContainerAdministrator 436600 Oct  5 17:18 '\BuildTools/VC/Tools/MSVC/14.29.30133/bin/Hostx86/x86/msvcp140.dll'

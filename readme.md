

In order to get started with the Jupyter data science container, try the following command.

**Note: You need to (a) download this directory to share the files.**

The -v maps the location of your repository. This should point to the repository


In the below command, you need to customize the location of the directory.  For example, on my machine it is the following.
```
docker build -t analyticsdojo/jupyter:latest .
docker run  -d -p 8888:8888  --name analyticsdojo  -v /Users/jasonkuruzovich/githubdesktop/0_class/techfundamentals-fall2018-materials:/home/jovyan/work analyticsdojo/jupyter:latest

```

On a Windows machine, it might be the following:
```
docker run -d -p 8888:8888  -e GRANT_SUDO=yes  --name analyticsdojo  -v /C//Users/jkuruzovich/materials/analyticsdojo:/home/jovyan/work analyticsdojo/jupyter:latest
```
If you reboot and later find that the container is not running, you can start it from the command line with
```docker start analyticsdojo```

If you enter the wrong file path:

```
docker stop analyticsdojo
docker rm analyticsdojo
```
Then rerun the command.




This will launch a container (called analyticsdojo) and share the appropriate directory with the container.  This will allow the container to easily share files and notebooks with the operating system.

If everything is working correctly then  [http://localhost:8888/](http://localhost:8888/) will show the root directory of this repository in the Jupyter console.

![Console](http://i.imgur.com/0Jqvh56.png)



To launch the Spark notebook, follow a similar command:
```
docker run -p 8888:8888  -e GRANT_SUDO=yes  --name analyticsdojo_pyspark  -v /Users/jasonkuruzovich/githubdesktop/0_class:/home/jovyan/work jupyter/pyspark-notebook
```



License
-------
Please check the individual directories regarding the licensing.  Because this project incorporates materials from different project, the subdirectories had different required attribuiton and licensing.

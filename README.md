Steps to build in Yocto BSP:
1. Create meta-layer
2. Add meta-layer
$ bitbake-layers create-layer meta-work
$ bitbake-layers add-layer meta-work
 
3. Browser to the recipe-example directory
4. Create a recipe folder for your application
5. Create a files folder under your application folder
$ cd meta-work/recipes-example/
$ mkdir hellogtk
$ mkdir hellogtk/files
 
6. Browser to files folder and create hellogtk.c and Makefiles
$ cd hellogtk/files/
$ vim hellogtk.c
 
7. Create bb file by recipetool:
$ cd hellogtk
$ recipetool create -o hellogtk_v1.0.bb files/hellogtk.c
 
8. Modify hellogtk.bb file
	a. Add the SRC_URI file
	b. Modify S = “${WORKDIR}”
	c. Add “DEPENDS = “gtk+3”
	d. Add “inherit pkgconfig”
	e. Add compile command:
 
9. Search the recipe you created:
$ bitbake –s | grep gtk
 
10. Bitbake recipe:
$ bitbake hellogtk
Then it can find the binary file at: ${WORKDIR}

11. Or you can build the application with devshell
$ biitbake hellogtk –c devshell 
# make
 

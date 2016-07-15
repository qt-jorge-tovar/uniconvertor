# uniconvertor

1.- Install MacPorts

2.- I used python 2.7

3.- Clone uniconvertor script

  $ git clone https://github.com/sk1project/uniconvertor/

4.- Try to run the following inside uniconvertor folder

  $ python setup.py build

Which will give some errors:

  ld: library not found for -llcms
  
  collect2: ld returned 1 exit status
  
  ld: library not found for -llcms
  
  collect2: ld returned 1 exit status
  
  lipo: can't open input file: /var/folders/3w/5x6f3w0n4rg0w6sdq2n_48j00000gn/T//cc8y3Erh.out (No such file or directory)
  
  error: command 'llvm-gcc-4.2' failed with exit status 1

5.- Check if lcms is in your MAC

  $ locate lcms

...
/opt/local/include/lcms.h

...

/opt/local/lib/liblcms.a

....

lcms was installed by MacPort on my computer

6.- If lcms is not installed in your MAC

  $ sudo port install lcms
  $ sudo port install freetype

7.- Modify the compiling flags

  $ CFLAGS="-I/opt/local/include -I/opt/local/include/freetype2" LDFLAGS="-L/opt/local/lib"

8.- Now you are be able to build

  $ python setup.py build

9.- And install...

  $ sudo python setup.py install

10.- Type uniconvertor in your command line.

Notes:

  If you ran with problems with PIL module not found, install it through pip
    $ pip install pillow


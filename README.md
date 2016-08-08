# hy-agda

This repo is a collection of notes and other stuff related to Agda.

## Installation of Agda

On macbook pro, there were already some old and/or misconfigured versions of
Haskell and cabal.  Here's how that was fixed:

1.  get rid of old stuff

        rm -rf ~/.cabal/ ~/.ghc/

2. Download and install the latest version (ver 8.0.1) of Haskell from [https://www.haskell.org/platform/](https://www.haskell.org/platform/)

3. Uninstall old versions of Haskell so they don't conflict with the newly installed version. 

        sudo uninstall-hs thru 7.8.3 --remove

4. Download the latest cabal-install source code from [https://www.haskell.org/cabal/download.html](https://www.haskell.org/cabal/download.html)
and put it in ~/opt.

        mv ~/Downloads/cabal-install-1.24.0.0.tar.gz ~/opt/

5. Unpack the cabal-install source code and run the bootstrap.sh installation script.

        cd ~/opt/
        tar xvzf cabal-install-1.24.0.0.tar.gz 
        cd cabal-install-1.24.0.0
        ./bootstrap.sh 

6. Modify the PATH environment variable so we can find stuff in ~/.cabal/bin

        export PATH=$HOME.cabal/bin:$PATH

(Note: $HOME=/Users/shinhyeyoung.  Also added `$HOME/.cabal/bin` to
PATH variable in the config file .bash_profile, so this directory will
be included in PATH in future.) 

7. Run update and install the required dependencies for Agda

        cabal update
        cabal install happy alex

8. Finally, install Agda

        cabal install Agda

9. Run agda-mode setup (which merely modifies your .emacs configuration file, so that emacs knows where to find agda-mode).

        agda-mode setup

10. Launch aquamacs with an agda file called First.agda.

        aquamacs First.agda &



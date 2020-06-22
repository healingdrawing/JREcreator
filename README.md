# JREcreator
Create JRE for modern JDK using python3 scripting of java jlink tool.  
Tested using [python3](https://www.python.org/) on [kubuntu 18.04](https://kubuntu.org/) in 2020.
# steps
- you must have python3 instaled on your pc
- download needed jdk version, f.e. [AdoptOpenJDK]( https://adoptopenjdk.net/)
- extract archive, it create folder, which can be renamed manually, if needed
- place `jrec.py` inside jdk folder. on level of `bin` folder  
  - `jrec.py`  
  - `bin/`
  - `man/`
  - `...`
  - `release`
- run `jrec.py` python3 script.
  - linux (tested using kubuntu 18.04)
    - open terminal, and execute commands
    - `cd /path/of/your/jdk`
    - `python3 jrec.py`
    - enter, wait
  - windows (not tested)
    - place `jrec.py` inside jdk folder
    - select file , and press enter, wait
- jre folder will appear in level of bin folder
  - `jrec.py`  
  - `bin/`
  - `man/`
  - **`jre/`**
  - `release`
  
This allow using resulted jdk with injected jre folder that [packr](https://github.com/libgdx/packr) work correct way , without breaking the flow.

# why this was created
Some tools f.e. libgdx [packr](https://github.com/libgdx/packr) need jre folder inside jdk for correct work, because was updated before java change jdk structure.  
Modern jdk (version 9+) have different structure of JDK , which break the [packr](https://github.com/libgdx/packr) work flow.  
This script `jrec.py` generate the jre folder inside jdk folder , using jlink java tool.
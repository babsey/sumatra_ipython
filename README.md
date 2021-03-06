# sumatra_ipython
Sumatra implementation for IPython magic function. Sumatra works with IPython interactively.

Requirement
-----------
or which I have already tested:
- Sumatra 0.7.0rc ([official](https://github.com/open-research/sumatra) or [my forked](https://github.com/babsey/sumatra) version)
- IPython 3.0.0

How to install it
-----------------
- Download the zip file, then unzip 
- Copy `cp sumatramagic.py  ~/.ipython/profile_default/startup/` (recommended with specific profile)
- Run `ipython` (or `ipython --profile=<profile_name>`)

How to use it
-------------
- Use the magic key `%smt_run` with options:
  - `-m` select the main_file (neccessary)
  - `-r` enable sumatra recording
  - `-s` only save output data to file
- **Important:** The result of the script should be named as `data` and set to global.
  - Implement `global data` in the beginning of the script file 

Examples
--------
- Run without recordings `%smt_run -m myscript.py default.param`
- Run with recordings `%smt_run -m myscript.py default.param -r`
- Run without recordings but save the data to file `%smt_run -m myscript.py default.param -s`
- Run without recordings, change parameter set and then run with recording but use changed parameter set
  1. `%smt_run -m myscript.py default.param`
  2. `parameters.update({'key':value})`
  3. `%smt_run -m myscript.py default.param -r`

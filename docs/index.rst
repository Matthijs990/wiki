# index

welcome at the os_sys docs.

## index:

[first](#first)  
[getting started with os_sys](#getting started)  
[progress bars](#progress bars)  
[discription](#discription)  
[help(os_sys)](#help)

* * *

<div id="first">

## first

first there are somethings you need to know:  
1\. this docs are under devlopment.  
2\. if you want to add somethings to this docs go to os_sys github and post a what you want to add and i will ad it.  
3\. have fun with this package.

</div>

* * *

<div id="getting started">

thanks for downloading os_sys. i hope you will enjoy using it this. this is a doc to help you getting started with os_sys. os_sys is my first big package. again i hope you will enjoy using it so. lets get started.  
typ:  
import os_sys  
print(os_sys.msg) if the installation was a succes you wil se in the shell:  
installation succes  
else you will get a error. so now you have installed os_sys you are ready to use it

</div>

<div id="progress bars">

# loading_bars: Easy progress reporting for Python

|pypi|

## Bars

There are 7 progress bars to choose from:

*   `Bar`
*   `ChargingBar`
*   `FillingSquaresBar`
*   `FillingCirclesBar`
*   `IncrementalBar`
*   `PixelBar`
*   `ShadyBar`

To use them, just call `next` to advance and `finish` to finish:

.. code-block:: python

    from os_sys.progress import bar

    bar = Bar('Processing', max=20)
    for i in range(20):
        # Do some work
        bar.next()
    bar.finish()

or use any bar of this class as a context manager:

.. code-block:: python

    from os_sys.progress import bar

    with Bar('Processing', max=20) as bar:
        for i in range(20):
            # Do some work
            bar.next()

The result will be a bar like the following: ::

    Processing |#############                   | 42/100

To simplify the common case where the work is done in an iterator, you can use the `iter` method:

.. code-block:: python

    for i in Bar('Processing').iter(it):
        # Do some work

Progress bars are very customizable, you can change their width, their fill character, their suffix and more:

.. code-block:: python

    bar = Bar('Loading', fill='@', suffix='%(percent)d%%')

This will produce a bar like the following: ::

    Loading |@@@@@@@@@@@@@                   | 42%

You can use a number of template arguments in `message` and `suffix`:

========== ================================ Name Value ========== ================================ index current value max maximum value remaining max - index progress index / max percent progress * 100 avg simple moving average time per item (in seconds) elapsed elapsed time in seconds elapsed_td elapsed as a timedelta (useful for printing as a string) eta avg * remaining eta_td eta as a timedelta (useful for printing as a string) ========== ================================

Instead of passing all configuration options on instatiation, you can create your custom subclass:

.. code-block:: python

    class FancyBar(Bar):
        message = 'Loading'
        fill = '*'
        suffix = '%(percent).1f%% - %(eta)ds'

You can also override any of the arguments or create your own:

.. code-block:: python

    class SlowBar(Bar):
        suffix = '%(remaining_hours)d hours remaining'
        @property
        def remaining_hours(self):
            return self.eta // 3600

# Spinners

For actions with an unknown number of steps you can use a spinner:

.. code-block:: python

    from os_sys.progress import spinner

    spinner = Spinner('Loading ')
    while state != 'FINISHED':
        # Do some work
        spinner.next()

There are 5 predefined spinners:

*   `Spinner`
*   `PieSpinner`
*   `MoonSpinner`
*   `LineSpinner`
*   `PixelSpinner`

</div>

<div id="discription">

# include:

    introduction

    description                                                                                                                                                                    

    license(at the end)
    home
    loading_bars

# introduction:

    to install os_sys you type: pip install os_sys                                                                                  
    to upgrade os_sys you type: pip install --upgrade os_sys                                                                                  
    so lets get start to install os_sys                                                                                  

# discription:

    os_sys is a extra package for python(3)                                                                                  
    it's a extra to have a more easy use of the normal python libs                                                                                  
    plz look sometimes to my packages becuse i am making more own libs(extra is not that own lib)                                                                                  
    if i have more info i while show it here                                                                                   
    plz read the license                                                                                  

# license:

    Copyright (c) 2018 The Python Packaging Authority

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.

</div>

<div id="help">

' Help on package os_sys:  

NAME  
os_sys  

PACKAGE CONTENTS  
_progress  
commands (package)  
discription  
errors  
fail  
html_text (package)  
modules  
os_sys  
programs (package)  
progress_bars  
py_install (package)  
system  
test (package)  
upload  
wifi  

CLASSES  
builtins.object  
progress_types  
threading.Thread(builtins.object)  
progress_bar_loading  
tqdm  
tqdm._tqdm.tqdm(tqdm._utils.Comparable)  
tqdm._tqdm_gui.tqdm_gui  

gui_bar = class tqdm_gui(tqdm ._tqdm.tqdm)  
| gui_bar(*args, **kwargs)  
|  
| Experimental GUI version of tqdm!  
|  
| Method resolution order: **| tqdm_gui  
| tqdm._tqdm.tqdm  
| tqdm._utils.Comparable  
| builtins.object  
|  
| Methods defined here:  
|  
| __init__(self, *args, **kwargs)  
| Parameters  
| ----------  
| iterable : iter able, optional  
| Iterable to decorate with a progressbar.  
| Leave blank to manually manage the updates.  
| desc : str, optional  
| Prefix for the progressbar.  
| total : int, optional  
| The number of expected i terations. If unspecified,  
| len(iterable) is used if possible. If float("inf") or as a last  
| resort, only basic pr ogress statistics are displayed  
| (no ETA, no progressbar).  
| If `gui` is True and this parameter needs subsequent u pdating,  
| specify an initial arbitrary large positive integer,  
| e.g. int(9e9).  
| leave : bool, optio nal  
| If [default: True], keeps all traces of the progressbar  
| upon termination of iteration.  
| file : `io.TextIOWrapper` or `io.StringIO`, optional  
| Specifies where to output the progress messages  
| (default: sys.std err). Uses `file.write(str)` and `file.flush()`  
| methods.  
| ncols : int, optional  
| The width of the entire output message. If specified,  
| dynamically resizes the progressbar to stay within this bound.  
| If unspecifi ed, attempts to use environment width. The  
| fallback is a meter width of 10 and no limit for the counter and  
| stat istics. If 0, will not print any meter (only stats).  
| mininterval : float, optional  
| Minimum progress display update interval [default: 0.1] seconds.  
| maxinterval : float, optional  
| Maximum progress display update interval [default: 1 0] seconds.  
| Automatically adjusts `miniters` to correspond to `mininterval`  
| after long display update lag. Only works if `dynamic_miniters`  
| or monitor thread is enabled.  
| miniters : int, optional  
| Minimum progr ess display update interval, in iterations.  
| If 0 and `dynamic_miniters`, will automatically adjust to equal  
| `min interval` (more CPU efficient, good for tight loops).  
| If > 0, will skip display of specified number of iterations.  
| Tweak this and `mininterval` to get very efficient loops.  
| If your progress is erratic with both fast and slow iterations  
| (network, skipping items, etc) you should set miniters=1.  
| ascii : bool, optional  
| If unspecified or False, use unicod e (smooth blocks) to fill  
| the meter. The fallback is to use ASCII characters `1-9 #`.  
| disable : bool, optional  
| Whether to disable the entire progressbar wrapper  
| [default: False]. If set to None, disable on non-TTY.  
| un it : str, optional  
| String that will be used to define the unit of each iteration  
| [default: it].  
| u nit_scale : bool or int or float, optional  
| If 1 or True, the number of iterations will be reduced/scaled  
| a utomatically and a metric prefix following the  
| International System of Units standard will be added  
| (kilo, mega, etc.) [default: False]. If any other non-zero  
| number, will scale `total` and `n`.  
| dynamic_ncols : bool, optional  
| If set, constantly alters `ncols` to the environment (allowing  
| for window resizes) [default: False].  
| smoothi ng : float, optional  
| Exponential moving average smoothing factor for speed estimates  
| (ignored in GUI mode). Range s from 0 (average speed) to 1  
| (current/instantaneous speed) [default: 0.3].  
| bar_format : str, optional  
| Specify a custom bar string formatting. May impact performance.  
| [default: \'{l_bar}{bar}{r_bar}\'], where  
| l_bar=\' {desc}: {percentage:3.0f}%|\' and  
| r_bar=\'| {n_fmt}/{total_fmt} [{elapsed}<{remaining}, \'  
| \'{rate_fmt}{postfix }]\'  
| Possible vars: l_bar, bar, r_bar, n, n_fmt, total, total_fmt,  
| percentage, rate, rate_fmt, rate_noinv, rate_ noinv_fmt,  
| rate_inv, rate_inv_fmt, elapsed, remaining, desc, postfix.  
| Note that a trailing ": " is automatically removed after {desc}  
| if the latter is empty.  
| initial : int, optional  
| The initial counter value. Usef ul when restarting a progress  
| bar [default: 0].  
| position : int, optional  
| Specify the line offset to print this bar (starting from 0)  
| Automatic if unspecified.  
| Useful to manage multiple bars at once (eg, from threads) .  
| postfix : dict or *, optional  
| Specify additional stats to display at the end of the bar.  
| Calls `se t_postfix(**postfix)` if possible (dict).  
| unit_divisor : float, optional  
| [default: 1000], ignored unless `unit_scale` i s True.  
| gui : bool, optional  
| WARNING: internal parameter - do not use.  
| Use tqdm_gui(...) instead. I f set, will attempt to use  
| matplotlib animations for a graphical output [default: False].  
|  
| Returns  
| -------  
| out : decorated iterator.  
|  
| __iter__(self)  
| Backward-compatibility to use: for x in tqdm(iterabl e)  
|  
| close(self)  
| Cleanup and (if leave=False) close the progressbar.  
|  
| update(self, n=1)  
| Manually update the progress bar, useful for streams  
| such as reading files.  
| E.g.:  
| >>> t = tqdm(total=filesize) # Initialise  
| >>> for current_buffer in stream:  
| ... ...  
| ... t.update(len(current_buffer))  
| > >> t.close()  
| The last line is highly recommended, but possibly not necessary if  
| `t.update()` will be called in such a way that `filesize` will be  
| exactly reached and printed.  
|  
| Parameters  
| ----------  
| n : int, option al  
| Increment to add to the internal counter of iterations  
| [default: 1].  
|  
| -------------------------- --------------------------------------------  
| Methods inherited from tqdm._tqdm.tqdm:  
|  
| __del__(self)  
|  
| __ent er__(self)  
|  
| __exit__(self, *exc)  
|  
| __hash__(self)  
| Return hash(self).  
|  
| __len__(self)  
|  
| __repr__(self)  
| Return repr(self).  
|  
| clear(self, nolock=False)  
| Clear current bar displa y  
|  
| display(self, msg=None, pos=None)  
| Use `self.sp` and to display `msg` in the specified `pos`.  
|  
| P arameters  
| ----------  
| msg : what to display (default: repr(self))  
| pos : position to display in. (default: abs(s elf.pos))  
|  
| moveto(self, n)  
|  
| refresh(self, nolock=False)  
| Force refresh the display of this bar  
|  
| set_description(self, desc=None, refresh=True)  
| Set/modify description of the progress bar.  
|  
| Parameters  
| desc : str, optional  
| refresh : bool, optional  
| Forces refresh [default: True].  
| **| set_description_str(self, desc=None, refresh=True)  
| Set/modify description without \': \' appended.  
|  
| set_postfix(se lf, ordered_dict=None, refresh=True, **kwargs)  
| Set/modify postfix (additional stats)  
| with automatic formatting based on datatype .  
|  
| Parameters  
| ----------  
| ordered_dict : dict or OrderedDict, optional  
| refresh : bool, o ptional  
| Forces refresh [default: True].  
| kwargs : dict, optional  
|  
| set_postfix_str(self, s=\'\', refresh= True)  
| Postfix without dictionary expansion, similar to prefix handling.  
|  
| unpause(self)  
| Restart tqdm timer fr om last print time.  
|  
| ----------------------------------------------------------------------  
| Class methods inherited from tqdm._ tqdm.tqdm:  
|  
| external_write_mode(file=None, nolock=False) from builtins.type  
| Disable tqdm within context and refresh tqdm whe n exits.  
| Useful when writing to standard output stream  
|  
| get_lock() from builtins.type  
| Get the global lock. Con struct it if it does not exist.  
|  
| pandas(*targs, **tkwargs) from builtins.type  
| Registers the given `tqdm` class with  
| pandas.core.  
| ( frame.DataFrame  
| | series.Series  
| | groupby.DataFrameGroupBy  
| | groupby. SeriesGroupBy  
| ).progress_apply  
|  
| A new instance will be create every time `progress_apply` is called,  
| a nd each instance will automatically close() upon completion.  
|  
| Parameters  
| ----------  
| targs, tkwargs : argum ents for the tqdm instance  
|  
| Examples  
| --------  
| >>> import pandas as pd  
| >>> import numpy as np  
| >>> from tqdm import tqdm, tqdm_gui  
| >>>  
| >>> df = pd.DataFrame(np.random.randint(0, 100, (100000, 6)))  
| >>> tqdm.pandas(ncols=50) # can use tqdm_gui, optional kwargs, etc  
| >>> # Now you can use `progress_apply` instead of `apply`  
| >>> df .groupby(0).progress_apply(lambda x: x**2)  
|  
| References  
| ----------  
| https://stackoverflow.com/questions/186032 70/  
| progress-indicator-during-pandas-operations-python  
|  
| set_lock(lock) from builtins.type  
| Set the global lock.  
|  
| write(s, file=None, end=\'  
\', nolock=False) from builtins.type  
| Print a message via tqdm (without overlap with bars)  
| **| ----------------------------------------------------------------------  
| Static methods inherited from tqdm._tqdm.tqdm:  
|  
| __ne w__(cls, *args, **kwargs)  
| Create and return a new object. See help(type) for accurate signature.  
|  
| ema(x, mu=None, alpha=0.3)  
| Exponential moving average: smoothing to give progressively lower  
| weights to older values.  
|  
| Parameters  
| ----------  
| x : float  
| New value to include in EMA.  
| mu : float, optional  
| Previous EMA value.  
| alpha : float, optional  
| Smoothing factor in range [0, 1], [default: 0.3].  
| Increase to give more weight to recent values.  
| Ranges from 0 (yields mu) to 1 (yields x).  
|  
| format_interval(t)  
| Formats a number of seconds as a clock time, [H:]MM:SS  
|  
| Parameters  
| ----------  
| t : int  
| Number of seconds.  
|  
| Returns  
| -------  
| out : str  
| [H:]MM:SS  
|  
| format_meter(n, total, elapsed, ncols=None, prefix=\'\', ascii=False, unit=\'it\', unit_scale=False, rate=None, bar_format=None, postfix=None, unit_divisor=1000, **extra_kwargs)  
| Return a string-based progr ess bar given some parameters  
|  
| Parameters  
| ----------  
| n : int  
| Number of finished iteration s.  
| total : int  
| The expected total number of iterations. If meaningless (), only  
| basic progress statistics ar e displayed (no ETA).  
| elapsed : float  
| Number of seconds passed since start.  
| ncols : int, optional  
| The width of the entire output message. If specified,  
| dynamically resizes the progress meter to stay within this bound  
| [defau lt: None]. The fallback meter width is 10 for the progress  
| bar + no limit for the iterations counter and statistics. If 0,  
| w ill not print any meter (only stats).  
| prefix : str, optional  
| Prefix message (included in total width) [default: \'\'].  
| Use as {desc} in bar_format string.  
| ascii : bool, optional  
| If not set, use unicode (smooth blocks) to fill the mete r  
| [default: False]. The fallback is to use ASCII characters  
| (1-9 #).  
| unit : str, optional  
| The iteration unit [default: \'it\'].  
| unit_scale : bool or int or float, optional  
| If 1 or True, the number of iterations will be printed with an  
| appropriate SI metric prefix (k = 10^3, M = 10^6, etc.)  
| [default: False]. If any other non-zero number, will scale  
| `total` and `n`.  
| rate : float, optional  
| Manual override for iteration rate.  
| If [default: None], uses n/elapsed.  
| bar_format : str, optional  
| Specify a custom bar string formatting. May impact performanc e.  
| [default: \'{l_bar}{bar}{r_bar}\'], where  
| l_bar=\'{desc}: {percentage:3.0f}%|\' and  
| r_bar=\'| {n_fm t}/{total_fmt} [{elapsed}<{remaining}, \'  
| \'{rate_fmt}{postfix}]\'  
| Possible vars: l_bar, bar, r_bar, n, n_fmt, total, t otal_fmt,  
| percentage, rate, rate_fmt, rate_noinv, rate_noinv_fmt,  
| rate_inv, rate_inv_fmt, elapsed, remaining, desc, p ostfix.  
| Note that a trailing ": " is automatically removed after {desc}  
| if the latter is empty.  
| postfix : *, optional  
| Similar to `prefix`, but placed at the end  
| (e.g. for additional stats).  
| Note: postfix is u sually a string (not a dict) for this method,  
| and will if possible be set to postfix = \', \' + postfix.  
| However other ty pes are supported (#382).  
| unit_divisor : float, optional  
| [default: 1000], ignored unless `unit_scale` is True.  
|  
| Returns  
| -------  
| out : Formatted meter and stats, ready to display.  
|  
| format_num(n)  
| Inte lligent scientific notation (.3g).  
|  
| Parameters  
| ----------  
| n : int or float or Numeric  
| A Number.  
|  
| Returns  
| -------  
| out : str  
| Formatted number.  
|  
| format_si zeof(num, suffix=\'\', divisor=1000)  
| Formats a number (greater than unity) with SI Order of Magnitude  
| prefixes.  
|  
| Parameters  
| ----------  
| num : float  
| Number ( >= 1) to format.  
| suffix : str, optional  
| Post-postfix [default: \'\'].  
| divisor : float, optionl  
| Divisor between prefixes [default: 1000].  
|  
| Returns  
| -------  
| out : str  
| Number with Order of Magnitude SI unit postfix.  
|  
| status_p rinter(file)  
| Manage the printing and in-place updating of a line of characters.  
| Note that if the string is longer than a line, the n in-place  
| updating may not work (it will print a new line at each refresh).  
|  
| ----------------------------------------------- -----------------------  
| Data descriptors inherited from tqdm._tqdm.tqdm:  
|  
| format_dict  
| Public API for read-only mem ber access  
|  
| ----------------------------------------------------------------------  
| Data and other attributes inherited from tqdm. _tqdm.tqdm:  
|  
| monitor = None  
|  
| monitor_interval = 10  
|  
| ------------------------------------------------ ----------------------  
| Methods inherited from tqdm._utils.Comparable:  
|  
| __eq__(self, other)  
| Return self==value.  
|  
| __ge__(self, other)  
| Return self>=value.  
|  
| __gt__(self, other)  
| Return self>value.  
|  
| __le__(self, other)  
| Return self<=value.  
|  
| __lt__(self, other)  
| Return self <value.<br>|  
| __ne__ (self, other)  
| Return self!=value.  
|  
| ----------------------------------------------------------------------  
| Data des criptors inherited from tqdm._utils.Comparable:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  

class progress_bar_loading(threading.Thread)  
| progress_bar_lo ading(group=None, target=None, name=None, args=(), kwargs=None, *, daemon=None)  
|  
| A class that represents a thread of control.  
|  
| This class can be safely subclassed in a limited fashion. There are two ways  
| to specify the activity: by passing a callable object to the construc tor, or  
| by overriding the run() method in a subclass.  
|  
| Method resolution order:  
| progress_bar_loading  
| threading.Thread  
| builtins.object  
|  
| Methods defined here:  
|  
| kill(self)  
|  
| run(self)  
| Method representing the thread\'s activity.  
|  
| You may override this method in a subclass. The standard run() method  
| invokes the callable object passed to the object\'s constructor as the  
| target argument, if any, with sequential and keyword arguments taken  
| from the args and kwargs arguments, respectively.  
|  
| ----------------------------------------------------------------------  
| Data and other attributes defined here:  
|  
| __all__ = [\'run\', \'kill\']  
|  
| ------------------------------------------------ ----------------------  
| Methods inherited from threading.Thread:  
|  
| __init__(self, group=None, target=None, name=None, args=(), kwar gs=None, *, daemon=None)  
| This constructor should always be called with keyword arguments. Arguments are:  
|  
| *group* should be None; reserved for future extension when a ThreadGroup  
| class is implemented.  
|  
| *target* is the callable object to be in voked by the run()  
| method. Defaults to None, meaning nothing is called.  
|  
| *name* is the thread name. By default, a unique name is constructed of  
| the form "Thread-N" where N is a small decimal number.  
|  
| *args* is the argument tuple for the targe t invocation. Defaults to ().  
|  
| *kwargs* is a dictionary of keyword arguments for the target  
| invocation. Defaults to {}. **|  
| If a subclass overrides the constructor, it must make sure to invoke  
| the base class constructor (Thread.__init__()) befor e doing anything  
| else to the thread.  
|  
| __repr__(self)  
| Return repr(self).  
|  
| getName(self)  
|  
| isAlive = is_alive(self)  
| Return whether the thread is alive.  
|  
| This method returns True just before the run() method starts until just  
| after the run() method terminates. The module function enumerate()  
| returns a list of all alive threads. **|  
| isDaemon(self)  
|  
| is_alive(self)  
| Return whether the thread is alive.  
|  
| This method r eturns True just before the run() method starts until just  
| after the run() method terminates. The module function enumerate()  
| retu rns a list of all alive threads.  
|  
| join(self, timeout=None)  
| Wait until the thread terminates.  
|  
| This bl ocks the calling thread until the thread whose join() method is  
| called terminates -- either normally or through an unhandled exception  
| or until the optional timeout occurs.  
|  
| When the timeout argument is present and not None, it should be a  
| floating point n umber specifying a timeout for the operation in seconds  
| (or fractions thereof). As join() always returns None, you must call  
| isAli ve() after join() to decide whether a timeout happened -- if the  
| thread is still alive, the join() call timed out.  
|  
| When the timeout argument is not present or None, the operation will  
| block until the thread terminates.  
|  
| A thread can be join( )ed many times.  
|  
| join() raises a RuntimeError if an attempt is made to join the current  
| thread as that would cause a dead lock. It is also an error to join() a  
| thread before it has been started and attempts to do so raises the same  
| exception.  
|  
| setDaemon(self, daemonic)  
|  
| setName(self, name)  
|  
| start(self)  
| Start the thread\'s activity.  
|  
| It must be called at most once per thread object. It arranges for the  
| object\'s run() method to be invoked in a separate thread of control.  
|  
| This method will raise a RuntimeError if called more than once on the  
| same thread object.  
|  
| ----------------------------------------------------------------------  
| Data descriptors inherited from threading.Thread:  
|  
| __di ct__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if def ined)  
|  
| daemon  
| A boolean value indicating whether this thread is a daemon thread.  
|  
| This must be set be fore start() is called, otherwise RuntimeError is  
| raised. Its initial value is inherited from the creating thread; the  
| main thread is not a daemon thread and therefore all threads created in  
| the main thread default to daemon = False.  
|  
| The entire Python program exits when no alive non-daemon threads are  
| left.  
|  
| ident  
| Thread identifier of this thread or None if it has not been started.  
|  
| This is a nonzero integer. See the get_ident() function. Thread  
| identifiers may be recycled when a thread exits and another thread is  
| created. The identifier is available even after the thread has exited.  
|  
| name  
| A string used for identification purposes only.  
|  
| It has no semantics. Multiple threads may be given the same name. The  
| in itial name is set by the constructor.  

class progress_types(builtins.object)  
| Data descriptors defined here:  
|  
| __dict__ **| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)< br> |  
| ----------------------------------------------------------------------  
| Data and other attributes defined here:  
|  
| __all__ = [\'bar\', \'charging_bar\', \'filling_sqares_bar\', \'filling_circl...  
|  
| bar =<class \'progress.bar.bar\'="">  
|  
|< br> | charging_bar =<class \'progress.bar.chargingbar\'="">  
|  
|  
| countdown =<class \'progress.counter.countdown\'="">  
|  
|  
| counter =<class \'progress.counter.counter\'="">  
|  
|  
| filling_circles_bar =<class \'progress.bar.fillingcirclesbar\'="">  
|  
|  
| filling_sqares_bar =<class \'progress.bar.fillingsquaresbar\'="">  
|  
|  
| incremental_bar =<class \'progress.bar.in="" crementalbar\'="">  
|  
|  
| line_spinner =<class \'progress.spinner.linespinner\'="">  
|  
|  
| moon_spinner =<class \'pr="" ogress.spinner.moonspinner\'="">  
|  
|  
| pie =<class \'progress.counter.pie\'="">  
|  
|  
| pie_spinner =<class \'progre="" ss.spinner.piespinner\'="">  
|  
|  
| pixel_bar =<class \'progress.bar.pixelbar\'="">  
|  
|  
| pixel_spinner =<class \'pr="" ogress.spinner.pixelspinner\'="">  
|  
|  
| shady_bar =<class \'progress.bar.shadybar\'="">  
|  
|  
| spinner =<class \'pr="" ogress.spinner.spinner\'="">  
|  
|  
| stack =<class \'progress.counter.stack\'="">  

class tqdm(threading.Thread)  
| tqdm(args )  
|  
| tqdm help  
|  
| Decorate an iterable object, returning an iterator which acts exactly  
| like the origi nal iterable, but prints a dynamically updating  
| progressbar every time a value is requested.  
|  
|  
| def __init__(self, iterable=None, desc=None, total=None, leave=True,  
| file=None, ncols=None, mininterval=0.1,  
| maxinterval=10.0, miniters=None, ascii=None, disable=False,  
| unit=\'it\', unit_scale=False, dynamic_ncols=False,  
| smoothing=0.3, bar_format=None, initial=0, position=None,  
| postfix=None, unit_divisor=1000 total=100):  
|  
| Method resoluti on order:  
| tqdm  
| threading.Thread  
| builtins.object  
|  
| Methods defined here:  
|  
| __init_ _(self, args)  
| This constructor should always be called with keyword arguments. Arguments are:  
|  
| *group* should be None; reserv ed for future extension when a ThreadGroup  
| class is implemented.  
|  
| *target* is the callable object to be invoked by the run()< br> | method. Defaults to None, meaning nothing is called.  
|  
| *name* is the thread name. By default, a unique name is constructed of< br> | the form "Thread-N" where N is a small decimal number.  
|  
| *args* is the argument tuple for the target invocation. Defaults to ( ).  
|  
| *kwargs* is a dictionary of keyword arguments for the target  
| invocation. Defaults to {}.  
|  
| If a su bclass overrides the constructor, it must make sure to invoke  
| the base class constructor (Thread.__init__()) before doing anything  
| els e to the thread.  
|  
| close()  
|  
| run(self, between)  
| Method representing the thread\'s activity.  
|  
| You may override this method in a subclass. The standard run() method  
| invokes the callable object passed to the object\'s constructor as the  
| target argument, if any, with sequential and keyword arguments taken  
| from the args and kwargs arguments, respectively.  
|  
| up date(self, n=1)  
|  
| ----------------------------------------------------------------------  
| Data and other attributes defined here:  
|  
| __all__ = [\'run\']  
|  
| ----------------------------------------------------------------------  
| Methods inherited from threa ding.Thread:  
|  
| __repr__(self)  
| Return repr(self).  
|  
| getName(self)  
|  
| isAlive = is_alive(self) **| Return whether the thread is alive.  
|  
| This method returns True just before the run() method starts until just  
| aft er the run() method terminates. The module function enumerate()  
| returns a list of all alive threads.  
|  
| isDaemon(self)  
|  
| is_alive(self)  
| Return whether the thread is alive.  
|  
| This method returns True just before the run() method starts until just  
| after the run() method terminates. The module function enumerate()  
| returns a list of all alive threads.  
|  
| join(self , timeout=None)  
| Wait until the thread terminates.  
|  
| This blocks the calling thread until the thread whose join() method is  
| called terminates -- either normally or through an unhandled exception  
| or until the optional timeout occurs.  
|  
| When the timeout argument is present and not None, it should be a  
| floating point number specifying a timeout for the operation in seconds  
| (or fr actions thereof). As join() always returns None, you must call  
| isAlive() after join() to decide whether a timeout happened -- if the  
| th read is still alive, the join() call timed out.  
|  
| When the timeout argument is not present or None, the operation will  
| block un til the thread terminates.  
|  
| A thread can be join()ed many times.  
|  
| join() raises a RuntimeError if an attempt is made to join the current  
| thread as that would cause a deadlock. It is also an error to join() a  
| thread before it has been started and attemp ts to do so raises the same  
| exception.  
|  
| setDaemon(self, daemonic)  
|  
| setName(self, name)  
|  
| st art(self)  
| Start the thread\'s activity.  
|  
| It must be called at most once per thread object. It arranges for the  
| object\'s run() method to be invoked in a separate thread of control.  
|  
| This method will raise a RuntimeError if called more than once on the< br> | same thread object.  
|  
| ----------------------------------------------------------------------  
| Data descriptors inherited from threading.Thread:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| li st of weak references to the object (if defined)  
|  
| daemon  
| A boolean value indicating whether this thread is a daemon thread.  
|  
| This must be set before start() is called, otherwise RuntimeError is  
| raised. Its initial value is inherited from the creating thread; the  
| main thread is not a daemon thread and therefore all threads created in  
| the main thread default to daemon = False.  
|  
| The entire Python program exits when no alive non-daemon threads are  
| left.  
|  
| ident  
| Thread identifier of this thread or None if it has not been started.  
|  
| This is a nonzero integer. See the get_ident() function. Thread  
| identifiers may be recycled when a thread exits and another thread is  
| created. The identifier is available even after the thread has exited.  
|  
| name  
| A string used for identification purposes only.  
|  
| It has no semantics. Multiple threads may be given the same name. The  
| initial name is set by the constructor.  

class tqdm_gui(tqdm._tqdm.tqdm)  
| tqdm_gui(*args, **kwargs)  
|  
| Experimental GUI version of tqdm!  
|  
| Method resolution order:  
| tqdm_gui  
| tqdm._tqdm.tqdm  
| tqdm._utils.Comparable  
| bu iltins.object  
|  
| Methods defined here:  
|  
| __init__(self, *args, **kwargs)  
| Parameters  
| ----------  
| iterable : iterable, optional  
| Iterable to decorate with a progressbar.  
| Leave blank to manually manage the updates.  
| desc : str, optional  
| Prefix for the progressbar.  
| total : int, optional  
| The number is expected iteration s. If unspecified,  
| len(iterable) is used if possible. If float("inf") or as a last  
| resort, only basic progress statistics are d isplayed  
| (no ETA, no progressbar).  
| If `gui` is True and this parameter needs subsequent updating,  
| specify an initial arbitrary large positive integer,  
| e.g. int(9e9).  
| leave : bool, optional  
| If [default: True], keeps all t races of the progressbar  
| upon termination of iteration.  
| file : `io.TextIOWrapper` or `io.StringIO`, optional  
| Sp ecifies where to output the progress messages  
| (default: sys.stderr). Uses `file.write(str)` and `file.flush()`  
| methods.  
| ncols : int, optional  
| The width of the entire output message. If specified,  
| dynamically resizes the progressbar to stay within this bound.  
| If unspecified, attempts to use environment width. The  
| fallback is a meter width of 10 and no limit for the counter and  
| statistics. If 0, will not print any meter (only stats).  
| mininterval : float, optional  
| Minimum prog ress display update interval [default: 0.1] seconds.  
| maxinterval : float, optional  
| Maximum progress display update interval [defau lt: 10] seconds.  
| Automatically adjusts `miniters` to correspond to `mininterval`  
| after long display update lag. Only works if ` dynamic_miniters`  
| or monitor thread is enabled.  
| miniters : int, optional  
| Minimum progress display update interv al, in iterations.  
| If 0 and `dynamic_miniters`, will automatically adjust to equal  
| `mininterval` (more CPU efficient, good for tight loops).  
| If > 0, will skip display of specified number of iterations.  
| Tweak this and `mininterval` to get very efficient l oops.  
| If your progress is erratic with both fast and slow iterations  
| (network, skipping items, etc) you should set miniters=1.< br> | ascii : bool, optional  
| If unspecified or False, use unicode (smooth blocks) to fill  
| the meter. The fallback is to use ASCII characters `1-9 #`.  
| disable : bool, optional  
| Whether to disable the entire progressbar wrapper  
| [de fault: False]. If set to None, disable on non-TTY.  
| unit : str, optional  
| String that will be used to define the unit of each iterat ion  
| [default: it].  
| unit_scale : bool or int or float, optional  
| If 1 or True, the number of iterations will be r educed/scaled  
| automatically and a metric prefix following the  
| International System of Units standard will be added  
| (kilo, mega, etc.) [default: False]. If any other non-zero  
| number, will scale `total` and `n`.  
| dynamic_ncols : bool, optional  
| If set, constantly alters `ncols` to the environment (allowing  
| for window resizes) [default: False].  
| smoothing : float, optional  
| Exponential moving average smoothing factor for speed estimates  
| (ignored in GUI mode). Ranges from 0 (average speed) t o 1  
| (current/instantaneous speed) [default: 0.3].  
| bar_format : str, optional  
| Specify a custom bar string format ting. May impact performance.  
| [default: \'{l_bar}{bar}{r_bar}\'], where  
| l_bar=\'{desc}: {percentage:3.0f}%|\' and  
| r_bar=\'| {n_fmt}/{total_fmt} [{elapsed}<{remaining}, \'  
| \'{rate_fmt}{postfix}]\'  
| Possible vars: l_bar, bar, r_bar, n, n_fmt, total, total_fmt,  
| percentage, rate, rate_fmt, rate_noinv, rate_noinv_fmt,  
| rate_inv, rate_inv_fmt, elapsed, remaining, desc, postfix.  
| Note that a trailing ": " is automatically removed after {desc}  
| if the latter is empty.  
| initial : int, optional  
| The initial counter value. Useful when restarting a progress  
| bar [default: 0].  
| position : int, optiona l  
| Specify the line offset to print this bar (starting from 0)  
| Automatic if unspecified.  
| Useful to manage mul tiple bars at once (eg, from threads).  
| postfix : dict or *, optional  
| Specify additional stats to display at the end of the bar.  
| Calls `set_postfix(**postfix)` if possible (dict).  
| unit_divisor : float, optional  
| [default: 1000], ignored unless `unit_scale` is True.  
| gui : bool, optional  
| WARNING: internal parameter - do not use.  
| Use tqdm_gui(...) instead. If set, will attempt to use  
| matplotlib animations for a graphical output [default: False].  
|  
| Returns  
| -------  
| out : decorated iterator.  
|  
| __iter__(self)  
| Backward-compatibility to use: for x in tqdm(iterable)  
|  
| close(self)  
| Cleanup and (if leave=False) close the progressbar.  
|  
| update(self, n=1)  
| Manually update the progress bar, useful for streams  
| such as reading files.  
| E.g.:  
| >>> t = tqdm(total=filesize) # Initialise  
| >>> for cu rrent_buffer in stream:  
| ... ...  
| ... t.update(len(current_buffer))  
| >>> t.close()  
| The last line is hi ghly recommended, but possibly not necessary if  
| `t.update()` will be called in such a way that `filesize` will be  
| exactly reached and p rinted.  
|  
| Parameters  
| ----------  
| n : int, optional  
| Increment to add to the internal counter o f iterations  
| [default: 1].  
|  
| ----------------------------------------------------------------------  
| Methods inherite d from tqdm._tqdm.tqdm:  
|  
| __del__(self)  
|  
| __enter__(self)  
|  
| __exit__(self, *exc)  
|  
| __hash __(self)  
| Return hash(self).  
|  
| __len__(self)  
|  
| __repr__(self)  
| Return repr(self).  
|  
| clear(self, nolock=False)  
| Clear current bar display  
|  
| display(self, msg=None, pos=None)  
| Use `self.sp` and to disp lay `msg` in the specified `pos`.  
|  
| Parameters  
| ----------  
| msg : what to display (default: repr(self))  
| pos : position to display in. (default: abs(self.pos))  
|  
| moveto(self, n)  
|  
| refresh(self, nolock=False)  
| Force re fresh the display of this bar  
|  
| set_description(self, desc=None, refresh=True)  
| Set/modify description of the progress bar.  
|  
| Parameters  
| ----------  
| desc : str, optional  
| refresh : bool, optional  
| Forces refresh [default: True].  
|  
| set_description_str(self, desc=None, refresh=True)  
| Set/modify description without \': \' appended.  
|  
| set_postfix(self, ordered_dict=None, refresh=True, **kwargs)  
| Set/modify postfix (additional stats)  
| with automatic formatting based o n datatype.  
|  
| Parameters  
| ----------  
| ordered_dict : dict or OrderedDict, optional  
| refresh : bool , optional  
| Forces refresh [default: True].  
| kwargs : dict, optional  
|  
| set_postfix_str(self, s=\'\', refresh=True )  
| Postfix without dictionary expansion, similar to prefix handling.  
|  
| unpause(self)  
| Restart tqdm timer from last pri nt time.  
|  
| ----------------------------------------------------------------------  
| Class methods inherited from tqdm._tqdm.tqdm:  
|  
| external_write_mode(file=None, nolock=False) from builtins.type  
| Disable tqdm within context and refresh tqdm when exits.  
| U seful when writing to standard output stream  
|  
| get_lock() from builtins.type  
| Get the global lock. Construct it if it does not exist .  
|  
| pandas(*targs, **tkwargs) from builtins.type  
| Registers the given `tqdm` class with  
| pandas.core.  
| ( frame.DataFrame  
| | series.Series  
| | groupby.DataFrameGroupBy  
| | groupby.SeriesGroupBy  
| ).pr ogress_apply  
|  
| A new instance will be create every time `progress_apply` is called,  
| and each instance will automatically close( ) upon completion.  
|  
| Parameters  
| ----------  
| targs, tkwargs : arguments for the tqdm instance  
|  
| Examples  
| --------  
| >>> import pandas as pd  
| >>> import numpy as np  
| >>> from tqdm import tqdm, tqdm_gui  
| >>>  
| >>> df = pd.DataFrame(np.random.randint(0, 100, (100000, 6)))  
| >>> tqdm.pandas(ncols=50) # can use tqdm_gui, optional kwargs , etc  
| >>> # Now you can use `progress_apply` instead of `apply`  
| >>> df.groupby(0).progress_apply(lambda x: x**2)  
|  
| References  
| ----------  
| https://stackoverflow.com/questions/18603270/  
| progress-indicator-during-pandas operations-python **|  
| set_lock(lock) from builtins.type  
| Set the global lock.  
|  
| write(s, file=None, end=\'  
\', nolock=False) from b uiltins.type  
| Print a message via tqdm (without overlap with bars)  
|  
| --------------------------------------------------------------- -------  
| Static methods inherited from tqdm._tqdm.tqdm:  
|  
| __new__(cls, *args, **kwargs)  
| Create and return a new object. See help(type) for accurate signature.  
|  
| ema(x, mu=None, alpha=0.3)  
| Exponential moving average: smoothing to give progressively low er  
| weights to older values.  
|  
| Parameters  
| ----------  
| x : float  
| New value to in clude in EMA.  
| mu : float, optional  
| Previous EMA value.  
| alpha : float, optional  
| Smoothing factor in range [0, 1], [default: 0.3].  
| Increase to give more weight to recent values.  
| Ranges from 0 (yields mu) to 1 (yields x).  
|  
| format_interval(t)  
| Formats a number of seconds as a clock time, [H:]MM:SS  
|  
| Parameters  
| ---------- **| t : int  
| Number of seconds.  
|  
| Returns  
| -------  
| out : str  
| [H: ]MM:SS  
|  
| format_meter(n, total, elapsed, ncols=None, prefix=\'\', ascii=False, unit=\'it\', unit_scale=False, rate=None, bar_format=None, postfix= None, unit_divisor=1000, **extra_kwargs)  
| Return a string-based progress bar given some parameters  
|  
| Parameters  
| - ---------  
| n : int  
| Number of finished iterations.  
| total : int  
| The expected total number of itera tions. If meaningless (), only  
| basic progress statistics are displayed (no ETA).  
| elapsed : float  
| Number of seco nds passed since start.  
| ncols : int, optional  
| The width of the entire output message. If specified,  
| dynamically resizes the progress meter to stay within this bound  
| [default: None]. The fallback meter width is 10 for the progress  
| bar + no limit for the iterations counter and statistics. If 0,  
| will not print any meter (only stats).  
| prefix : str, optional  
| Prefix message (included in total width) [default: \'\'].  
| Use as {desc} in bar_format string.  
| ascii : bool, optional  
| If not set, use unicode (smooth blocks) to fill the meter  
| [default: False]. The fallback is to use ASCII characters  
| (1-9 #).  
| unit : str, optional  
| The iteration unit [default: \'it\'].  
| unit_scale : bool or int or float, optional  
| If 1 or True, the number of iterations will be printed with an  
| appropriate SI metric prefix (k = 10^3, M = 10^6, etc.)  
| [default : False]. If any other non-zero number, will scale  
| `total` and `n`.  
| rate : float, optional  
| Manual override for iteration rate.  
| If [default: None], uses n/elapsed.  
| bar_format : str, optional  
| Specify a custom bar string form atting. May impact performance.  
| [default: \'{l_bar}{bar}{r_bar}\'], where  
| l_bar=\'{desc}: {percentage:3.0f}%|\' and  
| r_bar=\'| {n_fmt}/{total_fmt} [{elapsed}<{remaining}, \'  
| \'{rate_fmt}{postfix}]\'  
| Possible vars: l_bar, bar, r_bar, n, n_fmt, total, total_fmt,  
| percentage, rate, rate_fmt, rate_noinv, rate_noinv_fmt,  
| rate_inv, rate_inv_fmt, elapsed, remaining, desc, postfix.  
| Note that a trailing ": " is automatically removed after {desc}  
| if the latter is empty.  
| postfix : *, o ptional  
| Similar to `prefix`, but placed at the end  
| (e.g. for additional stats).  
| Note: postfix is usually a s tring (not a dict) for this method,  
| and will if possible be set to postfix = \', \' + postfix.  
| However other types are supporte d (#382).  
| unit_divisor : float, optional  
| [default: 1000], ignored unless `unit_scale` is True.  
|  
| Returns  
| -------  
| out : Formatted meter and stats, ready to display.  
|  
| format_num(n)  
| Intelligent scientific nota tion (.3g).  
|  
| Parameters  
| ----------  
| n : int or float or Numeric  
| A Number.  
|  
| Returns  
| -------  
| out : str  
| Formatted number.  
|  
| format_sizeof(num, suffix=\'\', divisor=100 0)  
| Formats a number (greater than unity) with SI Order of Magnitude  
| prefixes.  
|  
| Parameters  
| ------ ----  
| num : float  
| Number ( >= 1) to format.  
| suffix : str, optional  
| Post-postfix [default: \'\'].  
| divisor : float, optionl  
| Divisor between prefixes [default: 1000].  
|  
| Returns  
| -------  
| out : str  
| Number with Order of Magnitude SI unit postfix.  
|  
| status_printer(file)  
| Manage the printing and in-place updating of a line of characters.  
| Note that if the string is longer than a line, then in-place  
| updating may not work (it will print a new line at each refresh).  
|  
| ----------------------------------------------------------------------  
| Data descriptors inherited from tqdm._tqdm.tqdm:  
|  
| format_dict  
| Public API for read-only member access  
|  
| ----------------------------------- -----------------------------------  
| Data and other attributes inherited from tqdm._tqdm.tqdm:  
|  
| monitor = None  
|  
| mon itor_interval = 10  
|  
| ----------------------------------------------------------------------  
| Methods inherited from tqdm._utils.Comparab le:  
|  
| __eq__(self, other)  
| Return self==value.  
|  
| __ge__(self, other)  
| Return self>=value.  
|  
| __gt__(self, other)  
| Return self>value.  
|  
| __le__(self, other)  
| Return self<=value.  
|  
| __l t__(self, other)  
| Return self <value.<br>|  
| __ne__(self, other)  
| Return self!=value.  
|  
| ------------------- ---------------------------------------------------  
| Data descriptors inherited from tqdm._utils.Comparable:  
|  
| __dict__  
| di ctionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  

FUNCTIONS  
_code(txt)  

all_dict(dictory, exceptions=None, file_types=None, maps=True, files=False, print_data=False)  

bar(rn, fill=\'.\')  

download (url, file, path=None)  

more_input()  

obj_type = object_type(obj)  

object_type(obj)  

test()  

update_progress(progres s)  
# update_progress() : Displays or updates a console progress bar  
## Accepts a float between 0 and 1\. Any int will be converted to a float.  
## A value under 0 represents a \'halt\'.  
## A value at 1 or bigger represents 100%  

DATA  
__all__ = [\'os_sys\', \'fail\', \'modules\ ', \'system\', \'wifi\', \'programs\', ...  
web =<os_sys.web_open object="">  
' '</os_sys.web_open></value.<br>******</class></class></class></class></class></class></class></class></class></class></class></class></class></class></class></class>******</value.<br>******

******  

No Python documentation found for 'Bar'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'ChargingBar'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'Countdown'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'Counter'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'FillingCirclesBar'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'FillingSquaresBar'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'IncrementalBar'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'Infinite'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'LineSpinner'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'MoonSpinner'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'Pie'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'PieSpinner'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'PixelBar'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'PixelSpinner'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'Progress'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'ShadyBar'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'Spinner'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'Stack'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'Thread'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'WriteMixin'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'WritelnMixin'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for '__all__'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for '__builtins__'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for '__cached__'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

Help on str object:  

__doc__ = class str(object)  
| str(object='') -> str  
| str(bytes_or_buffer[, encoding[, errors]]) -> str  
|  
| Create a new string object from the given object. If encoding or  
| errors is specified, then the object must expose a data buffer  
| that will be decoded using the given encoding and error handler.  
| Otherwise, returns the result of object.__str__() (if defined)  
| or repr(object).  
| encoding defaults to sys.getdefaultencoding().  
| errors defaults to 'strict'.  
|  
| Methods defined here:  
|  
| __add__(self, value, /)  
| Return self+value.  
|  
| __contains__(self, key, /)  
| Return key in self.  
|  
| __eq__(self, value, /)  
| Return self==value.  
|  
| __format__(self, format_spec, /)  
| Return a formatted version of the string as described by format_spec.  
|  
| __ge__(self, value, /)  
| Return self>=value.  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __getitem__(self, key, /)  
| Return self[key].  
|  
| __getnewargs__(...)  
|  
| __gt__(self, value, /)  
| Return self>value.  
|  
| __hash__(self, /)  
| Return hash(self).  
|  
| __iter__(self, /)  
| Implement iter(self).  
|  
| __le__(self, value, /)  
| Return self<=value.  
|  
| __len__(self, /)  
| Return len(self).  
|  
| __lt__(self, value, /)  
| Return self <value. <br="">|  
| __mod__(self, value, /)  
| Return self%value.  
|  
| __mul__(self, value, /)  
| Return self*value.  
|  
| __ne__(self, value, /)  
| Return self!=value.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __rmod__(self, value, /)  
| Return value%self.  
|  
| __rmul__(self, value, /)  
| Return value*self.  
|  
| __sizeof__(self, /)  
| Return the size of the string in memory, in bytes.  
|  
| __str__(self, /)  
| Return str(self).  
|  
| capitalize(self, /)  
| Return a capitalized version of the string.  
|  
| More specifically, make the first character have upper case and the rest lower  
| case.  
|  
| casefold(self, /)  
| Return a version of the string suitable for caseless comparisons.  
|  
| center(self, width, fillchar=' ', /)  
| Return a centered string of length width.  
|  
| Padding is done using the specified fill character (default is a space).  
|  
| count(...)  
| S.count(sub[, start[, end]]) -> int  
|  
| Return the number of non-overlapping occurrences of substring sub in  
| string S[start:end]. Optional arguments start and end are  
| interpreted as in slice notation.  
|  
| encode(self, /, encoding='utf-8', errors='strict')  
| Encode the string using the codec registered for encoding.  
|  
| encoding  
| The encoding in which to encode the string.  
| errors  
| The error handling scheme to use for encoding errors.  
| The default is 'strict' meaning that encoding errors raise a  
| UnicodeEncodeError. Other possible values are 'ignore', 'replace' and  
| 'xmlcharrefreplace' as well as any other name registered with  
| codecs.register_error that can handle UnicodeEncodeErrors.  
|  
| endswith(...)  
| S.endswith(suffix[, start[, end]]) -> bool  
|  
| Return True if S ends with the specified suffix, False otherwise.  
| With optional start, test S beginning at that position.  
| With optional end, stop comparing S at that position.  
| suffix can also be a tuple of strings to try.  
|  
| expandtabs(self, /, tabsize=8)  
| Return a copy where all tab characters are expanded using spaces.  
|  
| If tabsize is not given, a tab size of 8 characters is assumed.  
|  
| find(...)  
| S.find(sub[, start[, end]]) -> int  
|  
| Return the lowest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Return -1 on failure.  
|  
| format(...)  
| S.format(*args, **kwargs) -> str  
|  
| Return a formatted version of S, using substitutions from args and kwargs.  
| The substitutions are identified by braces ('{' and '}').  
|  
| format_map(...)  
| S.format_map(mapping) -> str  
|  
| Return a formatted version of S, using substitutions from mapping.  
| The substitutions are identified by braces ('{' and '}').  
|  
| index(...)  
| S.index(sub[, start[, end]]) -> int  
|  
| Return the lowest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Raises ValueError when the substring is not found.  
|  
| isalnum(self, /)  
| Return True if the string is an alpha-numeric string, False otherwise.  
|  
| A string is alpha-numeric if all characters in the string are alpha-numeric and  
| there is at least one character in the string.  
|  
| isalpha(self, /)  
| Return True if the string is an alphabetic string, False otherwise.  
|  
| A string is alphabetic if all characters in the string are alphabetic and there  
| is at least one character in the string.  
|  
| isascii(self, /)  
| Return True if all characters in the string are ASCII, False otherwise.  
|  
| ASCII characters have code points in the range U+0000-U+007F.  
| Empty string is ASCII too.  
|  
| isdecimal(self, /)  
| Return True if the string is a decimal string, False otherwise.  
|  
| A string is a decimal string if all characters in the string are decimal and  
| there is at least one character in the string.  
|  
| isdigit(self, /)  
| Return True if the string is a digit string, False otherwise.  
|  
| A string is a digit string if all characters in the string are digits and there  
| is at least one character in the string.  
|  
| isidentifier(self, /)  
| Return True if the string is a valid Python identifier, False otherwise.  
|  
| Use keyword.iskeyword() to test for reserved identifiers such as "def" and  
| "class".  
|  
| islower(self, /)  
| Return True if the string is a lowercase string, False otherwise.  
|  
| A string is lowercase if all cased characters in the string are lowercase and  
| there is at least one cased character in the string.  
|  
| isnumeric(self, /)  
| Return True if the string is a numeric string, False otherwise.  
|  
| A string is numeric if all characters in the string are numeric and there is at  
| least one character in the string.  
|  
| isprintable(self, /)  
| Return True if the string is printable, False otherwise.  
|  
| A string is printable if all of its characters are considered printable in  
| repr() or if it is empty.  
|  
| isspace(self, /)  
| Return True if the string is a whitespace string, False otherwise.  
|  
| A string is whitespace if all characters in the string are whitespace and there  
| is at least one character in the string.  
|  
| istitle(self, /)  
| Return True if the string is a title-cased string, False otherwise.  
|  
| In a title-cased string, upper- and title-case characters may only  
| follow uncased characters and lowercase characters only cased ones.  
|  
| isupper(self, /)  
| Return True if the string is an uppercase string, False otherwise.  
|  
| A string is uppercase if all cased characters in the string are uppercase and  
| there is at least one cased character in the string.  
|  
| join(self, iterable, /)  
| Concatenate any number of strings.  
|  
| The string whose method is called is inserted in between each given string.  
| The result is returned as a new string.  
|  
| Example: '.'.join(['ab', 'pq', 'rs']) -> 'ab.pq.rs'  
|  
| ljust(self, width, fillchar=' ', /)  
| Return a left-justified string of length width.  
|  
| Padding is done using the specified fill character (default is a space).  
|  
| lower(self, /)  
| Return a copy of the string converted to lowercase.  
|  
| lstrip(self, chars=None, /)  
| Return a copy of the string with leading whitespace removed.  
|  
| If chars is given and not None, remove characters in chars instead.  
|  
| partition(self, sep, /)  
| Partition the string into three parts using the given separator.  
|  
| This will search for the separator in the string. If the separator is found,  
| returns a 3-tuple containing the part before the separator, the separator  
| itself, and the part after it.  
|  
| If the separator is not found, returns a 3-tuple containing the original string  
| and two empty strings.  
|  
| replace(self, old, new, count=-1, /)  
| Return a copy with all occurrences of substring old replaced by new.  
|  
| count  
| Maximum number of occurrences to replace.  
| -1 (the default value) means replace all occurrences.  
|  
| If the optional argument count is given, only the first count occurrences are  
| replaced.  
|  
| rfind(...)  
| S.rfind(sub[, start[, end]]) -> int  
|  
| Return the highest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Return -1 on failure.  
|  
| rindex(...)  
| S.rindex(sub[, start[, end]]) -> int  
|  
| Return the highest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Raises ValueError when the substring is not found.  
|  
| rjust(self, width, fillchar=' ', /)  
| Return a right-justified string of length width.  
|  
| Padding is done using the specified fill character (default is a space).  
|  
| rpartition(self, sep, /)  
| Partition the string into three parts using the given separator.  
|  
| This will search for the separator in the string, starting at the end. If  
| the separator is found, returns a 3-tuple containing the part before the  
| separator, the separator itself, and the part after it.  
|  
| If the separator is not found, returns a 3-tuple containing two empty strings  
| and the original string.  
|  
| rsplit(self, /, sep=None, maxsplit=-1)  
| Return a list of the words in the string, using sep as the delimiter string.  
|  
| sep  
| The delimiter according which to split the string.  
| None (the default value) means split according to any whitespace,  
| and discard empty strings from the result.  
| maxsplit  
| Maximum number of splits to do.  
| -1 (the default value) means no limit.  
|  
| Splits are done starting at the end of the string and working to the front.  
|  
| rstrip(self, chars=None, /)  
| Return a copy of the string with trailing whitespace removed.  
|  
| If chars is given and not None, remove characters in chars instead.  
|  
| split(self, /, sep=None, maxsplit=-1)  
| Return a list of the words in the string, using sep as the delimiter string.  
|  
| sep  
| The delimiter according which to split the string.  
| None (the default value) means split according to any whitespace,  
| and discard empty strings from the result.  
| maxsplit  
| Maximum number of splits to do.  
| -1 (the default value) means no limit.  
|  
| splitlines(self, /, keepends=False)  
| Return a list of the lines in the string, breaking at line boundaries.  
|  
| Line breaks are not included in the resulting list unless keepends is given and  
| true.  
|  
| startswith(...)  
| S.startswith(prefix[, start[, end]]) -> bool  
|  
| Return True if S starts with the specified prefix, False otherwise.  
| With optional start, test S beginning at that position.  
| With optional end, stop comparing S at that position.  
| prefix can also be a tuple of strings to try.  
|  
| strip(self, chars=None, /)  
| Return a copy of the string with leading and trailing whitespace remove.  
|  
| If chars is given and not None, remove characters in chars instead.  
|  
| swapcase(self, /)  
| Convert uppercase characters to lowercase and lowercase characters to uppercase.  
|  
| title(self, /)  
| Return a version of the string where each word is titlecased.  
|  
| More specifically, words start with uppercased characters and all remaining  
| cased characters have lower case.  
|  
| translate(self, table, /)  
| Replace each character in the string using the given translation table.  
|  
| table  
| Translation table, which must be a mapping of Unicode ordinals to  
| Unicode ordinals, strings, or None.  
|  
| The table must implement lookup/indexing via __getitem__, for instance a  
| dictionary or list. If this operation raises LookupError, the character is  
| left untouched. Characters mapped to None are deleted.  
|  
| upper(self, /)  
| Return a copy of the string converted to uppercase.  
|  
| zfill(self, width, /)  
| Pad a numeric string with zeros on the left, to fill a field of the given width.  
|  
| The string is never truncated.  
|  
|</value.>******

* * *

******  
| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
| maketrans(x, y=None, z=None, /)  
| Return a translation table usable for str.translate().  
|  
| If there is only one argument, it must be a dictionary mapping Unicode  
| ordinals (integers) or characters to Unicode ordinals, strings or None.  
| Character keys will be then converted to ordinals.  
| If there are two arguments, they must be strings of equal length, and  
| in the resulting dictionary, each character in x will be mapped to the  
| character at the same position in y. If there is a third argument, it  
| must be a string, whose characters will be mapped to None in the result.  

No Python documentation found for '__file__'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

Help on class BuiltinImporter in module importlib._bootstrap:  

__loader__ = class BuiltinImporter(builtins.object)  
| Meta path import for built-in modules.  
|  
| All methods are either class or static methods to avoid the need to  
| instantiate the class.  
|  
| Class methods defined here:  
|  
| create_module(spec) from builtins.type  
| Create a built-in module  
|  
| exec_module(module) from builtins.type  
| Exec a built-in module  
|  
| find_module(fullname, path=None) from builtins.type  
| Find the built-in module.  
|  
| If 'path' is ever specified then the search is considered a failure.  
|  
| This method is deprecated. Use find_spec() instead.  
|  
| find_spec(fullname, path=None, target=None) from builtins.type  
|  
| get_code(fullname) from builtins.type  
| Return None as built-in modules do not have code objects.  
|  
| get_source(fullname) from builtins.type  
| Return None as built-in modules do not have source code.  
|  
| is_package(fullname) from builtins.type  
| Return False as built-in modules are never packages.  
|  
| load_module = _load_module_shim(fullname) from builtins.type  
| Load the specified module into sys.modules and return it.  
|  
| This method is deprecated. Use loader.exec_module instead.  
|  
|

* * *

| Static methods defined here:  
|  
| module_repr(module)  
| Return repr for the module.  
|  
| The method is deprecated. The import machinery does the job itself.  
|  
|

* * *

| Data descriptors defined here:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  

Help on str object:  

__name__ = class str(object)  
| str(object='') -> str  
| str(bytes_or_buffer[, encoding[, errors]]) -> str  
|  
| Create a new string object from the given object. If encoding or  
| errors is specified, then the object must expose a data buffer  
| that will be decoded using the given encoding and error handler.  
| Otherwise, returns the result of object.__str__() (if defined)  
| or repr(object).  
| encoding defaults to sys.getdefaultencoding().  
| errors defaults to 'strict'.  
|  
| Methods defined here:  
|  
| __add__(self, value, /)  
| Return self+value.  
|  
| __contains__(self, key, /)  
| Return key in self.  
|  
| __eq__(self, value, /)  
| Return self==value.  
|  
| __format__(self, format_spec, /)  
| Return a formatted version of the string as described by format_spec.  
|  
| __ge__(self, value, /)  
| Return self>=value.  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __getitem__(self, key, /)  
| Return self[key].  
|  
| __getnewargs__(...)  
|  
| __gt__(self, value, /)  
| Return self>value.  
|  
| __hash__(self, /)  
| Return hash(self).  
|  
| __iter__(self, /)  
| Implement iter(self).  
|  
| __le__(self, value, /)  
| Return self<=value.  
|  
| __len__(self, /)  
| Return len(self).  
|  
| __lt__(self, value, /)  
| Return self <value. <br="">|  
| __mod__(self, value, /)  
| Return self%value.  
|  
| __mul__(self, value, /)  
| Return self*value.  
|  
| __ne__(self, value, /)  
| Return self!=value.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __rmod__(self, value, /)  
| Return value%self.  
|  
| __rmul__(self, value, /)  
| Return value*self.  
|  
| __sizeof__(self, /)  
| Return the size of the string in memory, in bytes.  
|  
| __str__(self, /)  
| Return str(self).  
|  
| capitalize(self, /)  
| Return a capitalized version of the string.  
|  
| More specifically, make the first character have upper case and the rest lower  
| case.  
|  
| casefold(self, /)  
| Return a version of the string suitable for caseless comparisons.  
|  
| center(self, width, fillchar=' ', /)  
| Return a centered string of length width.  
|  
| Padding is done using the specified fill character (default is a space).  
|  
| count(...)  
| S.count(sub[, start[, end]]) -> int  
|  
| Return the number of non-overlapping occurrences of substring sub in  
| string S[start:end]. Optional arguments start and end are  
| interpreted as in slice notation.  
|  
| encode(self, /, encoding='utf-8', errors='strict')  
| Encode the string using the codec registered for encoding.  
|  
| encoding  
| The encoding in which to encode the string.  
| errors  
| The error handling scheme to use for encoding errors.  
| The default is 'strict' meaning that encoding errors raise a  
| UnicodeEncodeError. Other possible values are 'ignore', 'replace' and  
| 'xmlcharrefreplace' as well as any other name registered with  
| codecs.register_error that can handle UnicodeEncodeErrors.  
|  
| endswith(...)  
| S.endswith(suffix[, start[, end]]) -> bool  
|  
| Return True if S ends with the specified suffix, False otherwise.  
| With optional start, test S beginning at that position.  
| With optional end, stop comparing S at that position.  
| suffix can also be a tuple of strings to try.  
|  
| expandtabs(self, /, tabsize=8)  
| Return a copy where all tab characters are expanded using spaces.  
|  
| If tabsize is not given, a tab size of 8 characters is assumed.  
|  
| find(...)  
| S.find(sub[, start[, end]]) -> int  
|  
| Return the lowest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Return -1 on failure.  
|  
| format(...)  
| S.format(*args, **kwargs) -> str  
|  
| Return a formatted version of S, using substitutions from args and kwargs.  
| The substitutions are identified by braces ('{' and '}').  
|  
| format_map(...)  
| S.format_map(mapping) -> str  
|  
| Return a formatted version of S, using substitutions from mapping.  
| The substitutions are identified by braces ('{' and '}').  
|  
| index(...)  
| S.index(sub[, start[, end]]) -> int  
|  
| Return the lowest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Raises ValueError when the substring is not found.  
|  
| isalnum(self, /)  
| Return True if the string is an alpha-numeric string, False otherwise.  
|  
| A string is alpha-numeric if all characters in the string are alpha-numeric and  
| there is at least one character in the string.  
|  
| isalpha(self, /)  
| Return True if the string is an alphabetic string, False otherwise.  
|  
| A string is alphabetic if all characters in the string are alphabetic and there  
| is at least one character in the string.  
|  
| isascii(self, /)  
| Return True if all characters in the string are ASCII, False otherwise.  
|  
| ASCII characters have code points in the range U+0000-U+007F.  
| Empty string is ASCII too.  
|  
| isdecimal(self, /)  
| Return True if the string is a decimal string, False otherwise.  
|  
| A string is a decimal string if all characters in the string are decimal and  
| there is at least one character in the string.  
|  
| isdigit(self, /)  
| Return True if the string is a digit string, False otherwise.  
|  
| A string is a digit string if all characters in the string are digits and there  
| is at least one character in the string.  
|  
| isidentifier(self, /)  
| Return True if the string is a valid Python identifier, False otherwise.  
|  
| Use keyword.iskeyword() to test for reserved identifiers such as "def" and  
| "class".  
|  
| islower(self, /)  
| Return True if the string is a lowercase string, False otherwise.  
|  
| A string is lowercase if all cased characters in the string are lowercase and  
| there is at least one cased character in the string.  
|  
| isnumeric(self, /)  
| Return True if the string is a numeric string, False otherwise.  
|  
| A string is numeric if all characters in the string are numeric and there is at  
| least one character in the string.  
|  
| isprintable(self, /)  
| Return True if the string is printable, False otherwise.  
|  
| A string is printable if all of its characters are considered printable in  
| repr() or if it is empty.  
|  
| isspace(self, /)  
| Return True if the string is a whitespace string, False otherwise.  
|  
| A string is whitespace if all characters in the string are whitespace and there  
| is at least one character in the string.  
|  
| istitle(self, /)  
| Return True if the string is a title-cased string, False otherwise.  
|  
| In a title-cased string, upper- and title-case characters may only  
| follow uncased characters and lowercase characters only cased ones.  
|  
| isupper(self, /)  
| Return True if the string is an uppercase string, False otherwise.  
|  
| A string is uppercase if all cased characters in the string are uppercase and  
| there is at least one cased character in the string.  
|  
| join(self, iterable, /)  
| Concatenate any number of strings.  
|  
| The string whose method is called is inserted in between each given string.  
| The result is returned as a new string.  
|  
| Example: '.'.join(['ab', 'pq', 'rs']) -> 'ab.pq.rs'  
|  
| ljust(self, width, fillchar=' ', /)  
| Return a left-justified string of length width.  
|  
| Padding is done using the specified fill character (default is a space).  
|  
| lower(self, /)  
| Return a copy of the string converted to lowercase.  
|  
| lstrip(self, chars=None, /)  
| Return a copy of the string with leading whitespace removed.  
|  
| If chars is given and not None, remove characters in chars instead.  
|  
| partition(self, sep, /)  
| Partition the string into three parts using the given separator.  
|  
| This will search for the separator in the string. If the separator is found,  
| returns a 3-tuple containing the part before the separator, the separator  
| itself, and the part after it.  
|  
| If the separator is not found, returns a 3-tuple containing the original string  
| and two empty strings.  
|  
| replace(self, old, new, count=-1, /)  
| Return a copy with all occurrences of substring old replaced by new.  
|  
| count  
| Maximum number of occurrences to replace.  
| -1 (the default value) means replace all occurrences.  
|  
| If the optional argument count is given, only the first count occurrences are  
| replaced.  
|  
| rfind(...)  
| S.rfind(sub[, start[, end]]) -> int  
|  
| Return the highest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Return -1 on failure.  
|  
| rindex(...)  
| S.rindex(sub[, start[, end]]) -> int  
|  
| Return the highest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Raises ValueError when the substring is not found.  
|  
| rjust(self, width, fillchar=' ', /)  
| Return a right-justified string of length width.  
|  
| Padding is done using the specified fill character (default is a space).  
|  
| rpartition(self, sep, /)  
| Partition the string into three parts using the given separator.  
|  
| This will search for the separator in the string, starting at the end. If  
| the separator is found, returns a 3-tuple containing the part before the  
| separator, the separator itself, and the part after it.  
|  
| If the separator is not found, returns a 3-tuple containing two empty strings  
| and the original string.  
|  
| rsplit(self, /, sep=None, maxsplit=-1)  
| Return a list of the words in the string, using sep as the delimiter string.  
|  
| sep  
| The delimiter according which to split the string.  
| None (the default value) means split according to any whitespace,  
| and discard empty strings from the result.  
| maxsplit  
| Maximum number of splits to do.  
| -1 (the default value) means no limit.  
|  
| Splits are done starting at the end of the string and working to the front.  
|  
| rstrip(self, chars=None, /)  
| Return a copy of the string with trailing whitespace removed.  
|  
| If chars is given and not None, remove characters in chars instead.  
|  
| split(self, /, sep=None, maxsplit=-1)  
| Return a list of the words in the string, using sep as the delimiter string.  
|  
| sep  
| The delimiter according which to split the string.  
| None (the default value) means split according to any whitespace,  
| and discard empty strings from the result.  
| maxsplit  
| Maximum number of splits to do.  
| -1 (the default value) means no limit.  
|  
| splitlines(self, /, keepends=False)  
| Return a list of the lines in the string, breaking at line boundaries.  
|  
| Line breaks are not included in the resulting list unless keepends is given and  
| true.  
|  
| startswith(...)  
| S.startswith(prefix[, start[, end]]) -> bool  
|  
| Return True if S starts with the specified prefix, False otherwise.  
| With optional start, test S beginning at that position.  
| With optional end, stop comparing S at that position.  
| prefix can also be a tuple of strings to try.  
|  
| strip(self, chars=None, /)  
| Return a copy of the string with leading and trailing whitespace remove.  
|  
| If chars is given and not None, remove characters in chars instead.  
|  
| swapcase(self, /)  
| Convert uppercase characters to lowercase and lowercase characters to uppercase.  
|  
| title(self, /)  
| Return a version of the string where each word is titlecased.  
|  
| More specifically, words start with uppercased characters and all remaining  
| cased characters have lower case.  
|  
| translate(self, table, /)  
| Replace each character in the string using the given translation table.  
|  
| table  
| Translation table, which must be a mapping of Unicode ordinals to  
| Unicode ordinals, strings, or None.  
|  
| The table must implement lookup/indexing via __getitem__, for instance a  
| dictionary or list. If this operation raises LookupError, the character is  
| left untouched. Characters mapped to None are deleted.  
|  
| upper(self, /)  
| Return a copy of the string converted to uppercase.  
|  
| zfill(self, width, /)  
| Pad a numeric string with zeros on the left, to fill a field of the given width.  
|  
| The string is never truncated.  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
| maketrans(x, y=None, z=None, /)  
| Return a translation table usable for str.translate().  
|  
| If there is only one argument, it must be a dictionary mapping Unicode  
| ordinals (integers) or characters to Unicode ordinals, strings or None.  
| Character keys will be then converted to ordinals.  
| If there are two arguments, they must be strings of equal length, and  
| in the resulting dictionary, each character in x will be mapped to the  
| character at the same position in y. If there is a third argument, it  
| must be a string, whose characters will be mapped to None in the result.  

Help on str object:  

__package__ = class str(object)  
| str(object='') -> str  
| str(bytes_or_buffer[, encoding[, errors]]) -> str  
|  
| Create a new string object from the given object. If encoding or  
| errors is specified, then the object must expose a data buffer  
| that will be decoded using the given encoding and error handler.  
| Otherwise, returns the result of object.__str__() (if defined)  
| or repr(object).  
| encoding defaults to sys.getdefaultencoding().  
| errors defaults to 'strict'.  
|  
| Methods defined here:  
|  
| __add__(self, value, /)  
| Return self+value.  
|  
| __contains__(self, key, /)  
| Return key in self.  
|  
| __eq__(self, value, /)  
| Return self==value.  
|  
| __format__(self, format_spec, /)  
| Return a formatted version of the string as described by format_spec.  
|  
| __ge__(self, value, /)  
| Return self>=value.  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __getitem__(self, key, /)  
| Return self[key].  
|  
| __getnewargs__(...)  
|  
| __gt__(self, value, /)  
| Return self>value.  
|  
| __hash__(self, /)  
| Return hash(self).  
|  
| __iter__(self, /)  
| Implement iter(self).  
|  
| __le__(self, value, /)  
| Return self<=value.  
|  
| __len__(self, /)  
| Return len(self).  
|  
| __lt__(self, value, /)  
| Return self <value. <br="">|  
| __mod__(self, value, /)  
| Return self%value.  
|  
| __mul__(self, value, /)  
| Return self*value.  
|  
| __ne__(self, value, /)  
| Return self!=value.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __rmod__(self, value, /)  
| Return value%self.  
|  
| __rmul__(self, value, /)  
| Return value*self.  
|  
| __sizeof__(self, /)  
| Return the size of the string in memory, in bytes.  
|  
| __str__(self, /)  
| Return str(self).  
|  
| capitalize(self, /)  
| Return a capitalized version of the string.  
|  
| More specifically, make the first character have upper case and the rest lower  
| case.  
|  
| casefold(self, /)  
| Return a version of the string suitable for caseless comparisons.  
|  
| center(self, width, fillchar=' ', /)  
| Return a centered string of length width.  
|  
| Padding is done using the specified fill character (default is a space).  
|  
| count(...)  
| S.count(sub[, start[, end]]) -> int  
|  
| Return the number of non-overlapping occurrences of substring sub in  
| string S[start:end]. Optional arguments start and end are  
| interpreted as in slice notation.  
|  
| encode(self, /, encoding='utf-8', errors='strict')  
| Encode the string using the codec registered for encoding.  
|  
| encoding  
| The encoding in which to encode the string.  
| errors  
| The error handling scheme to use for encoding errors.  
| The default is 'strict' meaning that encoding errors raise a  
| UnicodeEncodeError. Other possible values are 'ignore', 'replace' and  
| 'xmlcharrefreplace' as well as any other name registered with  
| codecs.register_error that can handle UnicodeEncodeErrors.  
|  
| endswith(...)  
| S.endswith(suffix[, start[, end]]) -> bool  
|  
| Return True if S ends with the specified suffix, False otherwise.  
| With optional start, test S beginning at that position.  
| With optional end, stop comparing S at that position.  
| suffix can also be a tuple of strings to try.  
|  
| expandtabs(self, /, tabsize=8)  
| Return a copy where all tab characters are expanded using spaces.  
|  
| If tabsize is not given, a tab size of 8 characters is assumed.  
|  
| find(...)  
| S.find(sub[, start[, end]]) -> int  
|  
| Return the lowest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Return -1 on failure.  
|  
| format(...)  
| S.format(*args, **kwargs) -> str  
|  
| Return a formatted version of S, using substitutions from args and kwargs.  
| The substitutions are identified by braces ('{' and '}').  
|  
| format_map(...)  
| S.format_map(mapping) -> str  
|  
| Return a formatted version of S, using substitutions from mapping.  
| The substitutions are identified by braces ('{' and '}').  
|  
| index(...)  
| S.index(sub[, start[, end]]) -> int  
|  
| Return the lowest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Raises ValueError when the substring is not found.  
|  
| isalnum(self, /)  
| Return True if the string is an alpha-numeric string, False otherwise.  
|  
| A string is alpha-numeric if all characters in the string are alpha-numeric and  
| there is at least one character in the string.  
|  
| isalpha(self, /)  
| Return True if the string is an alphabetic string, False otherwise.  
|  
| A string is alphabetic if all characters in the string are alphabetic and there  
| is at least one character in the string.  
|  
| isascii(self, /)  
| Return True if all characters in the string are ASCII, False otherwise.  
|  
| ASCII characters have code points in the range U+0000-U+007F.  
| Empty string is ASCII too.  
|  
| isdecimal(self, /)  
| Return True if the string is a decimal string, False otherwise.  
|  
| A string is a decimal string if all characters in the string are decimal and  
| there is at least one character in the string.  
|  
| isdigit(self, /)  
| Return True if the string is a digit string, False otherwise.  
|  
| A string is a digit string if all characters in the string are digits and there  
| is at least one character in the string.  
|  
| isidentifier(self, /)  
| Return True if the string is a valid Python identifier, False otherwise.  
|  
| Use keyword.iskeyword() to test for reserved identifiers such as "def" and  
| "class".  
|  
| islower(self, /)  
| Return True if the string is a lowercase string, False otherwise.  
|  
| A string is lowercase if all cased characters in the string are lowercase and  
| there is at least one cased character in the string.  
|  
| isnumeric(self, /)  
| Return True if the string is a numeric string, False otherwise.  
|  
| A string is numeric if all characters in the string are numeric and there is at  
| least one character in the string.  
|  
| isprintable(self, /)  
| Return True if the string is printable, False otherwise.  
|  
| A string is printable if all of its characters are considered printable in  
| repr() or if it is empty.  
|  
| isspace(self, /)  
| Return True if the string is a whitespace string, False otherwise.  
|  
| A string is whitespace if all characters in the string are whitespace and there  
| is at least one character in the string.  
|  
| istitle(self, /)  
| Return True if the string is a title-cased string, False otherwise.  
|  
| In a title-cased string, upper- and title-case characters may only  
| follow uncased characters and lowercase characters only cased ones.  
|  
| isupper(self, /)  
| Return True if the string is an uppercase string, False otherwise.  
|  
| A string is uppercase if all cased characters in the string are uppercase and  
| there is at least one cased character in the string.  
|  
| join(self, iterable, /)  
| Concatenate any number of strings.  
|  
| The string whose method is called is inserted in between each given string.  
| The result is returned as a new string.  
|  
| Example: '.'.join(['ab', 'pq', 'rs']) -> 'ab.pq.rs'  
|  
| ljust(self, width, fillchar=' ', /)  
| Return a left-justified string of length width.  
|  
| Padding is done using the specified fill character (default is a space).  
|  
| lower(self, /)  
| Return a copy of the string converted to lowercase.  
|  
| lstrip(self, chars=None, /)  
| Return a copy of the string with leading whitespace removed.  
|  
| If chars is given and not None, remove characters in chars instead.  
|  
| partition(self, sep, /)  
| Partition the string into three parts using the given separator.  
|  
| This will search for the separator in the string. If the separator is found,  
| returns a 3-tuple containing the part before the separator, the separator  
| itself, and the part after it.  
|  
| If the separator is not found, returns a 3-tuple containing the original string  
| and two empty strings.  
|  
| replace(self, old, new, count=-1, /)  
| Return a copy with all occurrences of substring old replaced by new.  
|  
| count  
| Maximum number of occurrences to replace.  
| -1 (the default value) means replace all occurrences.  
|  
| If the optional argument count is given, only the first count occurrences are  
| replaced.  
|  
| rfind(...)  
| S.rfind(sub[, start[, end]]) -> int  
|  
| Return the highest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Return -1 on failure.  
|  
| rindex(...)  
| S.rindex(sub[, start[, end]]) -> int  
|  
| Return the highest index in S where substring sub is found,  
| such that sub is contained within S[start:end]. Optional  
| arguments start and end are interpreted as in slice notation.  
|  
| Raises ValueError when the substring is not found.  
|  
| rjust(self, width, fillchar=' ', /)  
| Return a right-justified string of length width.  
|  
| Padding is done using the specified fill character (default is a space).  
|  
| rpartition(self, sep, /)  
| Partition the string into three parts using the given separator.  
|  
| This will search for the separator in the string, starting at the end. If  
| the separator is found, returns a 3-tuple containing the part before the  
| separator, the separator itself, and the part after it.  
|  
| If the separator is not found, returns a 3-tuple containing two empty strings  
| and the original string.  
|  
| rsplit(self, /, sep=None, maxsplit=-1)  
| Return a list of the words in the string, using sep as the delimiter string.  
|  
| sep  
| The delimiter according which to split the string.  
| None (the default value) means split according to any whitespace,  
| and discard empty strings from the result.  
| maxsplit  
| Maximum number of splits to do.  
| -1 (the default value) means no limit.  
|  
| Splits are done starting at the end of the string and working to the front.  
|  
| rstrip(self, chars=None, /)  
| Return a copy of the string with trailing whitespace removed.  
|  
| If chars is given and not None, remove characters in chars instead.  
|  
| split(self, /, sep=None, maxsplit=-1)  
| Return a list of the words in the string, using sep as the delimiter string.  
|  
| sep  
| The delimiter according which to split the string.  
| None (the default value) means split according to any whitespace,  
| and discard empty strings from the result.  
| maxsplit  
| Maximum number of splits to do.  
| -1 (the default value) means no limit.  
|  
| splitlines(self, /, keepends=False)  
| Return a list of the lines in the string, breaking at line boundaries.  
|  
| Line breaks are not included in the resulting list unless keepends is given and  
| true.  
|  
| startswith(...)  
| S.startswith(prefix[, start[, end]]) -> bool  
|  
| Return True if S starts with the specified prefix, False otherwise.  
| With optional start, test S beginning at that position.  
| With optional end, stop comparing S at that position.  
| prefix can also be a tuple of strings to try.  
|  
| strip(self, chars=None, /)  
| Return a copy of the string with leading and trailing whitespace remove.  
|  
| If chars is given and not None, remove characters in chars instead.  
|  
| swapcase(self, /)  
| Convert uppercase characters to lowercase and lowercase characters to uppercase.  
|  
| title(self, /)  
| Return a version of the string where each word is titlecased.  
|  
| More specifically, words start with uppercased characters and all remaining  
| cased characters have lower case.  
|  
| translate(self, table, /)  
| Replace each character in the string using the given translation table.  
|  
| table  
| Translation table, which must be a mapping of Unicode ordinals to  
| Unicode ordinals, strings, or None.  
|  
| The table must implement lookup/indexing via __getitem__, for instance a  
| dictionary or list. If this operation raises LookupError, the character is  
| left untouched. Characters mapped to None are deleted.  
|  
| upper(self, /)  
| Return a copy of the string converted to uppercase.  
|  
| zfill(self, width, /)  
| Pad a numeric string with zeros on the left, to fill a field of the given width.  
|  
| The string is never truncated.  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
| maketrans(x, y=None, z=None, /)  
| Return a translation table usable for str.translate().  
|  
| If there is only one argument, it must be a dictionary mapping Unicode  
| ordinals (integers) or characters to Unicode ordinals, strings or None.  
| Character keys will be then converted to ordinals.  
| If there are two arguments, they must be strings of equal length, and  
| in the resulting dictionary, each character in x will be mapped to the  
| character at the same position in y. If there is a third argument, it  
| must be a string, whose characters will be mapped to None in the result.  

No Python documentation found for '__path__'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

Help on ModuleSpec in module importlib._bootstrap object:  

__spec__ = class ModuleSpec(builtins.object)  
| __spec__(name, loader, *, origin=None, loader_state=None, is_package=None)  
|  
| The specification for a module, used for loading.  
|  
| A module's spec is the source for information about the module. For  
| data associated with the module, including source, use the spec's  
| loader.  
|  
| `name` is the absolute name of the module. `loader` is the loader  
| to use when loading the module. `parent` is the name of the  
| package the module is in. The parent is derived from the name.  
|  
| `is_package` determines if the module is considered a package or  
| not. On modules this is reflected by the `__path__` attribute.  
|  
| `origin` is the specific location used by the loader from which to  
| load the module, if that information is available. When filename is  
| set, origin will match.  
|  
| `has_location` indicates that a spec's "origin" reflects a location.  
| When this is True, `__file__` attribute of the module is set.  
|  
| `cached` is the location of the cached bytecode file, if any. It  
| corresponds to the `__cached__` attribute.  
|  
| `submodule_search_locations` is the sequence of path entries to  
| search when importing submodules. If set, is_package should be  
| True--and False otherwise.  
|  
| Packages are simply modules that (may) have submodules. If a spec  
| has a non-None value in `submodule_search_locations`, the import  
| system will consider modules loaded from the spec as packages.  
|  
| Only finders (see importlib.abc.MetaPathFinder and  
| importlib.abc.PathEntryFinder) should modify ModuleSpec instances.  
|  
| Methods defined here:  
|  
| __eq__(self, other)  
| Return self==value.  
|  
| __init__(self, name, loader, *, origin=None, loader_state=None, is_package=None)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
| __repr__(self)  
| Return repr(self).  
|  
|

* * *

| Data descriptors defined here:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
| cached  
|  
| has_location  
|  
| parent  
| The name of the module's parent.  
|  
|

* * *

| Data and other attributes defined here:  
|  
| __hash__ = None  

No Python documentation found for '_code'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for '_download'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for '_g'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for '_ins'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for '_m'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for '_t_q_d_m_'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'all_dict'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'bar'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'c_list'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'cmd_parser'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

Help on package docs:  

NAME  
docs  

PACKAGE CONTENTS  

FILE  
(built-in)  

Help on package download:  

NAME  
download - A tiny module to make downloading with python super easy.  

PACKAGE CONTENTS  
download  
tests (package)  

VERSION  
0.3.3  

FILE  
c:\users\matthijs\appdata\local\programs\python\python37\lib\site-packages\download\__init__.py  

No Python documentation found for 'get_newest_version'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'gpl'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'gui_bar'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'kill'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'make_text'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'more_input'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'msg'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'my_module'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'obj_type'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'object_type'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

Help on module os:  

NAME  
os - OS routines for NT or Posix depending on what system we're on.  

DESCRIPTION  
This exports:  
- all functions from posix or nt, e.g. unlink, stat, etc.  
- os.path is either posixpath or ntpath  
- os.name is either 'posix' or 'nt'  
- os.curdir is a string representing the current directory (always '.')  
- os.pardir is a string representing the parent directory (always '..')  
- os.sep is the (or a most common) pathname separator ('/' or '\\')  
- os.extsep is the extension separator (always '.')  
- os.altsep is the alternate pathname separator (None or '/')  
- os.pathsep is the component separator used in $PATH etc  
- os.linesep is the line separator in text files ('\r' or '\n' or '\r\n')  
- os.defpath is the default search path for executables  
- os.devnull is the file path of the null device ('/dev/null', etc.)  

Programs that import and use 'os' stand a better chance of being  
portable between different platforms. Of course, they must then  
only use functions that are defined by all platforms (e.g., unlink  
and opendir), and leave all pathname manipulation to os.path  
(e.g., split and join).  

CLASSES  
builtins.Exception(builtins.BaseException)  
builtins.OSError  
builtins.object  
nt.DirEntry  
builtins.tuple(builtins.object)  
nt.times_result  
nt.uname_result  
stat_result  
statvfs_result  
terminal_size  

class DirEntry(builtins.object)  
| Methods defined here:  
|  
| __fspath__(self, /)  
| Returns the path for the entry.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| inode(self, /)  
| Return inode of the entry; cached per entry.  
|  
| is_dir(self, /, *, follow_symlinks=True)  
| Return True if the entry is a directory; cached per entry.  
|  
| is_file(self, /, *, follow_symlinks=True)  
| Return True if the entry is a file; cached per entry.  
|  
| is_symlink(self, /)  
| Return True if the entry is a symbolic link; cached per entry.  
|  
| stat(self, /, *, follow_symlinks=True)  
| Return stat_result object for the entry; cached per entry.  
|  
|

* * *

| Data descriptors defined here:  
|  
| name  
| the entry's base filename, relative to scandir() "path" argument  
|  
| path  
| the entry's full path name; equivalent to os.path.join(scandir_path, entry.name)  

error = class OSError(Exception)  
| Base class for I/O related errors.  
|  
| Method resolution order:  
| OSError  
| Exception  
| BaseException  
| object  
|  
| Methods defined here:  
|  
| __init__(self, /, *args, **kwargs)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __str__(self, /)  
| Return str(self).  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Data descriptors defined here:  
|  
| characters_written  
|  
| errno  
| POSIX exception code  
|  
| filename  
| exception filename  
|  
| filename2  
| second exception filename  
|  
| strerror  
| exception strerror  
|  
| winerror  
| Win32 exception code  
|  
|

* * *

| Methods inherited from BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class stat_result(builtins.tuple)  
| stat_result(iterable=(), /)  
|  
| stat_result: Result from stat, fstat, or lstat.  
|  
| This object may be accessed either as a tuple of  
| (mode, ino, dev, nlink, uid, gid, size, atime, mtime, ctime)  
| or via the attributes st_mode, st_ino, st_dev, st_nlink, st_uid, and so on.  
|  
| Posix/windows: If your platform supports st_blksize, st_blocks, st_rdev,  
| or st_flags, they are available as attributes only.  
|  
| See os.stat for more information.  
|  
| Method resolution order:  
| stat_result  
| builtins.tuple  
| builtins.object  
|  
| Methods defined here:  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Data descriptors defined here:  
|  
| st_atime  
| time of last access  
|  
| st_atime_ns  
| time of last access in nanoseconds  
|  
| st_ctime  
| time of last change  
|  
| st_ctime_ns  
| time of last change in nanoseconds  
|  
| st_dev  
| device  
|  
| st_file_attributes  
| Windows file attribute bits  
|  
| st_gid  
| group ID of owner  
|  
| st_ino  
| inode  
|  
| st_mode  
| protection bits  
|  
| st_mtime  
| time of last modification  
|  
| st_mtime_ns  
| time of last modification in nanoseconds  
|  
| st_nlink  
| number of hard links  
|  
| st_size  
| total size, in bytes  
|  
| st_uid  
| user ID of owner  
|  
|

* * *

| Data and other attributes defined here:  
|  
| n_fields = 17  
|  
| n_sequence_fields = 10  
|  
| n_unnamed_fields = 3  
|  
|

* * *

| Methods inherited from builtins.tuple:  
|  
| __add__(self, value, /)  
| Return self+value.  
|  
| __contains__(self, key, /)  
| Return key in self.  
|  
| __eq__(self, value, /)  
| Return self==value.  
|  
| __ge__(self, value, /)  
| Return self>=value.  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __getitem__(self, key, /)  
| Return self[key].  
|  
| __getnewargs__(self, /)  
|  
| __gt__(self, value, /)  
| Return self>value.  
|  
| __hash__(self, /)  
| Return hash(self).  
|  
| __iter__(self, /)  
| Implement iter(self).  
|  
| __le__(self, value, /)  
| Return self<=value.  
|  
| __len__(self, /)  
| Return len(self).  
|  
| __lt__(self, value, /)  
| Return self <value. <br="">|  
| __mul__(self, value, /)  
| Return self*value.  
|  
| __ne__(self, value, /)  
| Return self!=value.  
|  
| __rmul__(self, value, /)  
| Return value*self.  
|  
| count(self, value, /)  
| Return number of occurrences of value.  
|  
| index(self, value, start=0, stop=9223372036854775807, /)  
| Return first index of value.  
|  
| Raises ValueError if the value is not present.  

class statvfs_result(builtins.tuple)  
| statvfs_result(iterable=(), /)  
|  
| statvfs_result: Result from statvfs or fstatvfs.  
|  
| This object may be accessed either as a tuple of  
| (bsize, frsize, blocks, bfree, bavail, files, ffree, favail, flag, namemax),  
| or via the attributes f_bsize, f_frsize, f_blocks, f_bfree, and so on.  
|  
| See os.statvfs for more information.  
|  
| Method resolution order:  
| statvfs_result  
| builtins.tuple  
| builtins.object  
|  
| Methods defined here:  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Data descriptors defined here:  
|  
| f_bavail  
|  
| f_bfree  
|  
| f_blocks  
|  
| f_bsize  
|  
| f_favail  
|  
| f_ffree  
|  
| f_files  
|  
| f_flag  
|  
| f_frsize  
|  
| f_fsid  
|  
| f_namemax  
|  
|

* * *

| Data and other attributes defined here:  
|  
| n_fields = 11  
|  
| n_sequence_fields = 10  
|  
| n_unnamed_fields = 0  
|  
|

* * *

| Methods inherited from builtins.tuple:  
|  
| __add__(self, value, /)  
| Return self+value.  
|  
| __contains__(self, key, /)  
| Return key in self.  
|  
| __eq__(self, value, /)  
| Return self==value.  
|  
| __ge__(self, value, /)  
| Return self>=value.  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __getitem__(self, key, /)  
| Return self[key].  
|  
| __getnewargs__(self, /)  
|  
| __gt__(self, value, /)  
| Return self>value.  
|  
| __hash__(self, /)  
| Return hash(self).  
|  
| __iter__(self, /)  
| Implement iter(self).  
|  
| __le__(self, value, /)  
| Return self<=value.  
|  
| __len__(self, /)  
| Return len(self).  
|  
| __lt__(self, value, /)  
| Return self <value. <br="">|  
| __mul__(self, value, /)  
| Return self*value.  
|  
| __ne__(self, value, /)  
| Return self!=value.  
|  
| __rmul__(self, value, /)  
| Return value*self.  
|  
| count(self, value, /)  
| Return number of occurrences of value.  
|  
| index(self, value, start=0, stop=9223372036854775807, /)  
| Return first index of value.  
|  
| Raises ValueError if the value is not present.  

class terminal_size(builtins.tuple)  
| terminal_size(iterable=(), /)  
|  
| A tuple of (columns, lines) for holding terminal window size  
|  
| Method resolution order:  
| terminal_size  
| builtins.tuple  
| builtins.object  
|  
| Methods defined here:  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Data descriptors defined here:  
|  
| columns  
| width of the terminal window in characters  
|  
| lines  
| height of the terminal window in characters  
|  
|

* * *

| Data and other attributes defined here:  
|  
| n_fields = 2  
|  
| n_sequence_fields = 2  
|  
| n_unnamed_fields = 0  
|  
|

* * *

| Methods inherited from builtins.tuple:  
|  
| __add__(self, value, /)  
| Return self+value.  
|  
| __contains__(self, key, /)  
| Return key in self.  
|  
| __eq__(self, value, /)  
| Return self==value.  
|  
| __ge__(self, value, /)  
| Return self>=value.  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __getitem__(self, key, /)  
| Return self[key].  
|  
| __getnewargs__(self, /)  
|  
| __gt__(self, value, /)  
| Return self>value.  
|  
| __hash__(self, /)  
| Return hash(self).  
|  
| __iter__(self, /)  
| Implement iter(self).  
|  
| __le__(self, value, /)  
| Return self<=value.  
|  
| __len__(self, /)  
| Return len(self).  
|  
| __lt__(self, value, /)  
| Return self <value. <br="">|  
| __mul__(self, value, /)  
| Return self*value.  
|  
| __ne__(self, value, /)  
| Return self!=value.  
|  
| __rmul__(self, value, /)  
| Return value*self.  
|  
| count(self, value, /)  
| Return number of occurrences of value.  
|  
| index(self, value, start=0, stop=9223372036854775807, /)  
| Return first index of value.  
|  
| Raises ValueError if the value is not present.  

class times_result(builtins.tuple)  
| times_result(iterable=(), /)  
|  
| times_result: Result from os.times().  
|  
| This object may be accessed either as a tuple of  
| (user, system, children_user, children_system, elapsed),  
| or via the attributes user, system, children_user, children_system,  
| and elapsed.  
|  
| See os.times for more information.  
|  
| Method resolution order:  
| times_result  
| builtins.tuple  
| builtins.object  
|  
| Methods defined here:  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Data descriptors defined here:  
|  
| children_system  
| system time of children  
|  
| children_user  
| user time of children  
|  
| elapsed  
| elapsed time since an arbitrary point in the past  
|  
| system  
| system time  
|  
| user  
| user time  
|  
|

* * *

| Data and other attributes defined here:  
|  
| n_fields = 5  
|  
| n_sequence_fields = 5  
|  
| n_unnamed_fields = 0  
|  
|

* * *

| Methods inherited from builtins.tuple:  
|  
| __add__(self, value, /)  
| Return self+value.  
|  
| __contains__(self, key, /)  
| Return key in self.  
|  
| __eq__(self, value, /)  
| Return self==value.  
|  
| __ge__(self, value, /)  
| Return self>=value.  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __getitem__(self, key, /)  
| Return self[key].  
|  
| __getnewargs__(self, /)  
|  
| __gt__(self, value, /)  
| Return self>value.  
|  
| __hash__(self, /)  
| Return hash(self).  
|  
| __iter__(self, /)  
| Implement iter(self).  
|  
| __le__(self, value, /)  
| Return self<=value.  
|  
| __len__(self, /)  
| Return len(self).  
|  
| __lt__(self, value, /)  
| Return self <value. <br="">|  
| __mul__(self, value, /)  
| Return self*value.  
|  
| __ne__(self, value, /)  
| Return self!=value.  
|  
| __rmul__(self, value, /)  
| Return value*self.  
|  
| count(self, value, /)  
| Return number of occurrences of value.  
|  
| index(self, value, start=0, stop=9223372036854775807, /)  
| Return first index of value.  
|  
| Raises ValueError if the value is not present.  

class uname_result(builtins.tuple)  
| uname_result(iterable=(), /)  
|  
| uname_result: Result from os.uname().  
|  
| This object may be accessed either as a tuple of  
| (sysname, nodename, release, version, machine),  
| or via the attributes sysname, nodename, release, version, and machine.  
|  
| See os.uname for more information.  
|  
| Method resolution order:  
| uname_result  
| builtins.tuple  
| builtins.object  
|  
| Methods defined here:  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Data descriptors defined here:  
|  
| machine  
| hardware identifier  
|  
| nodename  
| name of machine on network (implementation-defined)  
|  
| release  
| operating system release  
|  
| sysname  
| operating system name  
|  
| version  
| operating system version  
|  
|

* * *

| Data and other attributes defined here:  
|  
| n_fields = 5  
|  
| n_sequence_fields = 5  
|  
| n_unnamed_fields = 0  
|  
|

* * *

| Methods inherited from builtins.tuple:  
|  
| __add__(self, value, /)  
| Return self+value.  
|  
| __contains__(self, key, /)  
| Return key in self.  
|  
| __eq__(self, value, /)  
| Return self==value.  
|  
| __ge__(self, value, /)  
| Return self>=value.  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __getitem__(self, key, /)  
| Return self[key].  
|  
| __getnewargs__(self, /)  
|  
| __gt__(self, value, /)  
| Return self>value.  
|  
| __hash__(self, /)  
| Return hash(self).  
|  
| __iter__(self, /)  
| Implement iter(self).  
|  
| __le__(self, value, /)  
| Return self<=value.  
|  
| __len__(self, /)  
| Return len(self).  
|  
| __lt__(self, value, /)  
| Return self <value. <br="">|  
| __mul__(self, value, /)  
| Return self*value.  
|  
| __ne__(self, value, /)  
| Return self!=value.  
|  
| __rmul__(self, value, /)  
| Return value*self.  
|  
| count(self, value, /)  
| Return number of occurrences of value.  
|  
| index(self, value, start=0, stop=9223372036854775807, /)  
| Return first index of value.  
|  
| Raises ValueError if the value is not present.  

FUNCTIONS  
_exit(status)  
Exit to the system with specified status, without normal exit processing.  

abort()  
Abort the interpreter immediately.  

This function 'dumps core' or otherwise fails in the hardest way possible  
on the hosting operating system. This function never returns.  

access(path, mode, *, dir_fd=None, effective_ids=False, follow_symlinks=True)  
Use the real uid/gid to test for access to a path.  

path  
Path to be tested; can be string or bytes  
mode  
Operating-system mode bitfield. Can be F_OK to test existence,  
or the inclusive-OR of R_OK, W_OK, and X_OK.  
dir_fd  
If not None, it should be a file descriptor open to a directory,  
and path should be relative; path will then be relative to that  
directory.  
effective_ids  
If True, access will use the effective uid/gid instead of  
the real uid/gid.  
follow_symlinks  
If False, and the last element of the path is a symbolic link,  
access will examine the symbolic link itself instead of the file  
the link points to.  

dir_fd, effective_ids, and follow_symlinks may not be implemented  
on your platform. If they are unavailable, using them will raise a  
NotImplementedError.  

Note that most operations will use the effective uid/gid, therefore this  
routine can be used in a suid/sgid environment to test if the invoking user  
has the specified access to the path.  

chdir(path)  
Change the current working directory to the specified path.  

path may always be specified as a string.  
On some platforms, path may also be specified as an open file descriptor.  
If this functionality is unavailable, using it raises an exception.  

chmod(path, mode, *, dir_fd=None, follow_symlinks=True)  
Change the access permissions of a file.  

path  
Path to be modified. May always be specified as a str or bytes.  
On some platforms, path may also be specified as an open file descriptor.  
If this functionality is unavailable, using it raises an exception.  
mode  
Operating-system mode bitfield.  
dir_fd  
If not None, it should be a file descriptor open to a directory,  
and path should be relative; path will then be relative to that  
directory.  
follow_symlinks  
If False, and the last element of the path is a symbolic link,  
chmod will modify the symbolic link itself instead of the file  
the link points to.  

It is an error to use dir_fd or follow_symlinks when specifying path as  
an open file descriptor.  
dir_fd and follow_symlinks may not be implemented on your platform.  
If they are unavailable, using them will raise a NotImplementedError.  

close(fd)  
Close a file descriptor.  

closerange(fd_low, fd_high, /)  
Closes all file descriptors in [fd_low, fd_high), ignoring errors.  

cpu_count()  
Return the number of CPUs in the system; return None if indeterminable.  

This number is not equivalent to the number of CPUs the current process can  
use. The number of usable CPUs can be obtained with  
``len(os.sched_getaffinity(0))``  

device_encoding(fd)  
Return a string describing the encoding of a terminal's file descriptor.  

The file descriptor must be attached to a terminal.  
If the device is not a terminal, return None.  

dup(fd, /)  
Return a duplicate of a file descriptor.  

dup2(fd, fd2, inheritable=True)  
Duplicate file descriptor.  

execl(file, *args)  
execl(file, *args)  

Execute the executable file with argument list args, replacing the  
current process.  

execle(file, *args)  
execle(file, *args, env)  

Execute the executable file with argument list args and  
environment env, replacing the current process.  

execlp(file, *args)  
execlp(file, *args)  

Execute the executable file (which is searched for along $PATH)  
with argument list args, replacing the current process.  

execlpe(file, *args)  
execlpe(file, *args, env)  

Execute the executable file (which is searched for along $PATH)  
with argument list args and environment env, replacing the current  
process.  

execv(path, argv, /)  
Execute an executable path with arguments, replacing current process.  

path  
Path of executable file.  
argv  
Tuple or list of strings.  

execve(path, argv, env)  
Execute an executable path with arguments, replacing current process.  

path  
Path of executable file.  
argv  
Tuple or list of strings.  
env  
Dictionary of strings mapping to strings.  

execvp(file, args)  
execvp(file, args)  

Execute the executable file (which is searched for along $PATH)  
with argument list args, replacing the current process.  
args may be a list or tuple of strings.  

execvpe(file, args, env)  
execvpe(file, args, env)  

Execute the executable file (which is searched for along $PATH)  
with argument list args and environment env , replacing the  
current process.  
args may be a list or tuple of strings.  

fdopen(fd, *args, **kwargs)  
# Supply os.fdopen()  

fsdecode(filename)  
Decode filename (an os.PathLike, bytes, or str) from the filesystem  
encoding with 'surrogateescape' error handler, return str unchanged. On  
Windows, use 'strict' error handler if the file system encoding is  
'mbcs' (which is the default encoding).  

fsencode(filename)  
Encode filename (an os.PathLike, bytes, or str) to the filesystem  
encoding with 'surrogateescape' error handler, return bytes unchanged.  
On Windows, use 'strict' error handler if the file system encoding is  
'mbcs' (which is the default encoding).  

fspath(path)  
Return the file system path representation of the object.  

If the object is str or bytes, then allow it to pass through as-is. If the  
object defines __fspath__(), then return the result of that method. All other  
types raise a TypeError.  

fstat(fd)  
Perform a stat system call on the given file descriptor.  

Like stat(), but for an open file descriptor.  
Equivalent to os.stat(fd).  

fsync(fd)  
Force write of fd to disk.  

ftruncate(fd, length, /)  
Truncate a file, specified by file descriptor, to a specific length.  

get_exec_path(env=None)  
Returns the sequence of directories that will be searched for the  
named executable (similar to a shell) when launching a process.  

*env* must be an environment variable dict or None. If *env* is None,  
os.environ will be used.  

get_handle_inheritable(handle, /)  
Get the close-on-exe flag of the specified file descriptor.  

get_inheritable(fd, /)  
Get the close-on-exe flag of the specified file descriptor.  

get_terminal_size(...)  
Return the size of the terminal window as (columns, lines).  

The optional argument fd (default standard output) specifies  
which file descriptor should be queried.  

If the file descriptor is not connected to a terminal, an OSError  
is thrown.  

This function will only be defined if an implementation is  
available for this system.  

shutil.get_terminal_size is the high-level function which should  
normally be used, os.get_terminal_size is the low-level implementation.  

getcwd()  
Return a unicode string representing the current working directory.  

getcwdb()  
Return a bytes string representing the current working directory.  

getenv(key, default=None)  
Get an environment variable, return None if it doesn't exist.  
The optional second argument can specify an alternate default.  
key, default and the result are str.  

getlogin()  
Return the actual login name.  

getpid()  
Return the current process id.  

getppid()  
Return the parent's process id.  

If the parent process has already exited, Windows machines will still  
return its id; others systems will return the id of the 'init' process (1).  

isatty(fd, /)  
Return True if the fd is connected to a terminal.  

Return True if the file descriptor is an open file descriptor  
connected to the slave end of a terminal.  

kill(pid, signal, /)  
Kill a process with a signal.  

link(src, dst, *, src_dir_fd=None, dst_dir_fd=None, follow_symlinks=True)  
Create a hard link to a file.  

If either src_dir_fd or dst_dir_fd is not None, it should be a file  
descriptor open to a directory, and the respective path string (src or dst)  
should be relative; the path will then be relative to that directory.  
If follow_symlinks is False, and the last element of src is a symbolic  
link, link will create a link to the symbolic link itself instead of the  
file the link points to.  
src_dir_fd, dst_dir_fd, and follow_symlinks may not be implemented on your  
platform. If they are unavailable, using them will raise a  
NotImplementedError.  

listdir(path=None)  
Return a list containing the names of the files in the directory.  

path can be specified as either str or bytes. If path is bytes,  
the filenames returned will also be bytes; in all other circumstances  
the filenames returned will be str.  
If path is None, uses the path='.'.  
On some platforms, path may also be specified as an open file descriptor;\  
the file descriptor must refer to a directory.  
If this functionality is unavailable, using it raises NotImplementedError.  

The list is in arbitrary order. It does not include the special  
entries '.' and '..' even if they are present in the directory.  

lseek(fd, position, how, /)  
Set the position of a file descriptor. Return the new position.  

Return the new cursor position in number of bytes  
relative to the beginning of the file.  

lstat(path, *, dir_fd=None)  
Perform a stat system call on the given path, without following symbolic links.  

Like stat(), but do not follow symbolic links.  
Equivalent to stat(path, follow_symlinks=False).  

makedirs(name, mode=511, exist_ok=False)  
makedirs(name [, mode=0o777][, exist_ok=False])  

Super-mkdir; create a leaf directory and all intermediate ones. Works like  
mkdir, except that any intermediate path segment (not just the rightmost)  
will be created if it does not exist. If the target directory already  
exists, raise an OSError if exist_ok is False. Otherwise no exception is  
raised. This is recursive.  

mkdir(path, mode=511, *, dir_fd=None)  
Create a directory.  

If dir_fd is not None, it should be a file descriptor open to a directory,  
and path should be relative; path will then be relative to that directory.  
dir_fd may not be implemented on your platform.  
If it is unavailable, using it will raise a NotImplementedError.  

The mode argument is ignored on Windows.  

open(path, flags, mode=511, *, dir_fd=None)  
Open a file for low level IO. Returns a file descriptor (integer).  

If dir_fd is not None, it should be a file descriptor open to a directory,  
and path should be relative; path will then be relative to that directory.  
dir_fd may not be implemented on your platform.  
If it is unavailable, using it will raise a NotImplementedError.  

pipe()  
Create a pipe.  

Returns a tuple of two file descriptors:  
(read_fd, write_fd)  

popen(cmd, mode='r', buffering=-1)  
# Supply os.popen()  

putenv(name, value, /)  
Change or add an environment variable.  

read(fd, length, /)  
Read from a file descriptor. Returns a bytes object.  

readlink(...)  
readlink(path, *, dir_fd=None) -> path  

Return a string representing the path to which the symbolic link points.  

If dir_fd is not None, it should be a file descriptor open to a directory,  
and path should be relative; path will then be relative to that directory.  
dir_fd may not be implemented on your platform.  
If it is unavailable, using it will raise a NotImplementedError.  

remove(path, *, dir_fd=None)  
Remove a file (same as unlink()).  

If dir_fd is not None, it should be a file descriptor open to a directory,  
and path should be relative; path will then be relative to that directory.  
dir_fd may not be implemented on your platform.  
If it is unavailable, using it will raise a NotImplementedError.  

removedirs(name)  
removedirs(name)  

Super-rmdir; remove a leaf directory and all empty intermediate  
ones. Works like rmdir except that, if the leaf directory is  
successfully removed, directories corresponding to rightmost path  
segments will be pruned away until either the whole path is  
consumed or an error occurs. Errors during this latter phase are  
ignored -- they generally mean that a directory was not empty.  

rename(src, dst, *, src_dir_fd=None, dst_dir_fd=None)  
Rename a file or directory.  

If either src_dir_fd or dst_dir_fd is not None, it should be a file  
descriptor open to a directory, and the respective path string (src or dst)  
should be relative; the path will then be relative to that directory.  
src_dir_fd and dst_dir_fd, may not be implemented on your platform.  
If they are unavailable, using them will raise a NotImplementedError.  

renames(old, new)  
renames(old, new)  

Super-rename; create directories as necessary and delete any left  
empty. Works like rename, except creation of any intermediate  
directories needed to make the new pathname good is attempted  
first. After the rename, directories corresponding to rightmost  
path segments of the old name will be pruned until either the  
whole path is consumed or a nonempty directory is found.  

Note: this function can fail with the new directory structure made  
if you lack permissions needed to unlink the leaf directory or  
file.  

replace(src, dst, *, src_dir_fd=None, dst_dir_fd=None)  
Rename a file or directory, overwriting the destination.  

If either src_dir_fd or dst_dir_fd is not None, it should be a file  
descriptor open to a directory, and the respective path string (src or dst)  
should be relative; the path will then be relative to that directory.  
src_dir_fd and dst_dir_fd, may not be implemented on your platform.  
If they are unavailable, using them will raise a NotImplementedError."  

rmdir(path, *, dir_fd=None)  
Remove a directory.  

If dir_fd is not None, it should be a file descriptor open to a directory,  
and path should be relative; path will then be relative to that directory.  
dir_fd may not be implemented on your platform.  
If it is unavailable, using it will raise a NotImplementedError.  

scandir(path=None)  
Return an iterator of DirEntry objects for given path.  

path can be specified as either str, bytes or path-like object. If path  
is bytes, the names of yielded DirEntry objects will also be bytes; in  
all other circumstances they will be str.  

If path is None, uses the path='.'.  

set_handle_inheritable(handle, inheritable, /)  
Set the inheritable flag of the specified handle.  

set_inheritable(fd, inheritable, /)  
Set the inheritable flag of the specified file descriptor.  

spawnl(mode, file, *args)  
spawnl(mode, file, *args) -> integer  

Execute file with arguments from args in a subprocess.  
If mode == P_NOWAIT return the pid of the process.  
If mode == P_WAIT return the process's exit code if it exits normally;  
otherwise return -SIG, where SIG is the signal that killed it.  

spawnle(mode, file, *args)  
spawnle(mode, file, *args, env) -> integer  

Execute file with arguments from args in a subprocess with the  
supplied environment.  
If mode == P_NOWAIT return the pid of the process.  
If mode == P_WAIT return the process's exit code if it exits normally;  
otherwise return -SIG, where SIG is the signal that killed it.  

spawnv(mode, path, argv, /)  
Execute the program specified by path in a new process.  

mode  
Mode of process creation.  
path  
Path of executable file.  
argv  
Tuple or list of strings.  

spawnve(mode, path, argv, env, /)  
Execute the program specified by path in a new process.  

mode  
Mode of process creation.  
path  
Path of executable file.  
argv  
Tuple or list of strings.  
env  
Dictionary of strings mapping to strings.  

startfile(filepath, operation=None)  
startfile(filepath [, operation])  

Start a file with its associated application.  

When "operation" is not specified or "open", this acts like  
double-clicking the file in Explorer, or giving the file name as an  
argument to the DOS "start" command: the file is opened with whatever  
application (if any) its extension is associated.  
When another "operation" is given, it specifies what should be done with  
the file. A typical operation is "print".  

startfile returns as soon as the associated application is launched.  
There is no option to wait for the application to close, and no way  
to retrieve the application's exit status.  

The filepath is relative to the current directory. If you want to use  
an absolute path, make sure the first character is not a slash ("/");  
the underlying Win32 ShellExecute function doesn't work if it is.  

stat(path, *, dir_fd=None, follow_symlinks=True)  
Perform a stat system call on the given path.  

path  
Path to be examined; can be string, bytes, path-like object or  
open-file-descriptor int.  
dir_fd  
If not None, it should be a file descriptor open to a directory,  
and path should be a relative string; path will then be relative to  
that directory.  
follow_symlinks  
If False, and the last element of the path is a symbolic link,  
stat will examine the symbolic link itself instead of the file  
the link points to.  

dir_fd and follow_symlinks may not be implemented  
on your platform. If they are unavailable, using them will raise a  
NotImplementedError.  

It's an error to use dir_fd or follow_symlinks when specifying path as  
an open file descriptor.  

strerror(code, /)  
Translate an error code to a message string.  

symlink(src, dst, target_is_directory=False, *, dir_fd=None)  
Create a symbolic link pointing to src named dst.  

target_is_directory is required on Windows if the target is to be  
interpreted as a directory. (On Windows, symlink requires  
Windows 6.0 or greater, and raises a NotImplementedError otherwise.)  
target_is_directory is ignored on non-Windows platforms.  

If dir_fd is not None, it should be a file descriptor open to a directory,  
and path should be relative; path will then be relative to that directory.  
dir_fd may not be implemented on your platform.  
If it is unavailable, using it will raise a NotImplementedError.  

system(command)  
Execute the command in a subshell.  

times()  
Return a collection containing process timing information.  

The object returned behaves like a named tuple with these fields:  
(utime, stime, cutime, cstime, elapsed_time)  
All fields are floating point numbers.  

truncate(path, length)  
Truncate a file, specified by path, to a specific length.  

On some platforms, path may also be specified as an open file descriptor.  
If this functionality is unavailable, using it raises an exception.  

umask(mask, /)  
Set the current numeric umask and return the previous umask.  

unlink(path, *, dir_fd=None)  
Remove a file (same as remove()).  

If dir_fd is not None, it should be a file descriptor open to a directory,  
and path should be relative; path will then be relative to that directory.  
dir_fd may not be implemented on your platform.  
If it is unavailable, using it will raise a NotImplementedError.  

urandom(size, /)  
Return a bytes object containing random bytes suitable for cryptographic use.  

utime(path, times=None, *, ns=None, dir_fd=None, follow_symlinks=True)  
Set the access and modified time of path.  

path may always be specified as a string.  
On some platforms, path may also be specified as an open file descriptor.  
If this functionality is unavailable, using it raises an exception.  

If times is not None, it must be a tuple (atime, mtime);  
atime and mtime should be expressed as float seconds since the epoch.  
If ns is specified, it must be a tuple (atime_ns, mtime_ns);  
atime_ns and mtime_ns should be expressed as integer nanoseconds  
since the epoch.  
If times is None and ns is unspecified, utime uses the current time.  
Specifying tuples for both times and ns is an error.  

If dir_fd is not None, it should be a file descriptor open to a directory,  
and path should be relative; path will then be relative to that directory.  
If follow_symlinks is False, and the last element of the path is a symbolic  
link, utime will modify the symbolic link itself instead of the file the  
link points to.  
It is an error to use dir_fd or follow_symlinks when specifying path  
as an open file descriptor.  
dir_fd and follow_symlinks may not be available on your platform.  
If they are unavailable, using them will raise a NotImplementedError.  

waitpid(pid, options, /)  
Wait for completion of a given process.  

Returns a tuple of information regarding the process:  
(pid, status << 8)  

The options argument is ignored on Windows.  

walk(top, topdown=True, onerror=None, followlinks=False)  
Directory tree generator.  

For each directory in the directory tree rooted at top (including top  
itself, but excluding '.' and '..'), yields a 3-tuple  

dirpath, dirnames, filenames  

dirpath is a string, the path to the directory. dirnames is a list of  
the names of the subdirectories in dirpath (excluding '.' and '..').  
filenames is a list of the names of the non-directory files in dirpath.  
Note that the names in the lists are just names, with no path components.  
To get a full path (which begins with top) to a file or directory in  
dirpath, do os.path.join(dirpath, name).  

If optional arg 'topdown' is true or not specified, the triple for a  
directory is generated before the triples for any of its subdirectories  
(directories are generated top down). If topdown is false, the triple  
for a directory is generated after the triples for all of its  
subdirectories (directories are generated bottom up).  

When topdown is true, the caller can modify the dirnames list in-place  
(e.g., via del or slice assignment), and walk will only recurse into the  
subdirectories whose names remain in dirnames; this can be used to prune the  
search, or to impose a specific order of visiting. Modifying dirnames when  
topdown is false is ineffective, since the directories in dirnames have  
already been generated by the time dirnames itself is generated. No matter  
the value of topdown, the list of subdirectories is retrieved before the  
tuples for the directory and its subdirectories are generated.  

By default errors from the os.scandir() call are ignored. If  
optional arg 'onerror' is specified, it should be a function; it  
will be called with one argument, an OSError instance. It can  
report the error to continue with the walk, or raise the exception  
to abort the walk. Note that the filename is available as the  
filename attribute of the exception object.  

By default, os.walk does not follow symbolic links to subdirectories on  
systems that support them. In order to get this functionality, set the  
optional argument 'followlinks' to true.  

Caution: if you pass a relative pathname for top, don't change the  
current working directory between resumptions of walk. walk never  
changes the current directory, and assumes that the client doesn't  
either.  

Example:  

import os  
from os.path import join, getsize  
for root, dirs, files in os.walk('python/Lib/email'):  
print(root, "consumes", end="")  
print(sum([getsize(join(root, name)) for name in files]), end="")  
print("bytes in", len(files), "non-directory files")  
if 'CVS' in dirs:  
dirs.remove('CVS') # don't visit CVS directories  

write(fd, data, /)  
Write a bytes object to a file descriptor.  

DATA  
F_OK = 0  
O_APPEND = 8  
O_BINARY = 32768  
O_CREAT = 256  
O_EXCL = 1024  
O_NOINHERIT = 128  
O_RANDOM = 16  
O_RDONLY = 0  
O_RDWR = 2  
O_SEQUENTIAL = 32  
O_SHORT_LIVED = 4096  
O_TEMPORARY = 64  
O_TEXT = 16384  
O_TRUNC = 512  
O_WRONLY = 1  
P_DETACH = 4  
P_NOWAIT = 1  
P_NOWAITO = 3  
P_OVERLAY = 2  
P_WAIT = 0  
R_OK = 4  
SEEK_CUR = 1  
SEEK_END = 2  
SEEK_SET = 0  
TMP_MAX = 2147483647  
W_OK = 2  
X_OK = 1  
__all__ = ['altsep', 'curdir', 'pardir', 'sep', 'pathsep', 'linesep', ...  
altsep = '/'  
curdir = '.'  
defpath = r'.;C:\bin'  
devnull = 'nul'  
environ = environ({'ALLUSERSPROFILE': 'C:\\ProgramData', '... 'C:\\Use...  
extsep = '.'  
linesep = '\r\n'  
name = 'nt'  
pardir = '..'  
pathsep = ';'  
sep = r'\'  
supports_bytes_environ = False  

FILE  
c:\users\matthijs\appdata\local\programs\python\python37\lib\os.py  

No Python documentation found for 'os_sys_lib'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'osm'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'path'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'print_all_dirs'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'progres_types'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'progress_bar_loading'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'progress_types'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

Help on package requests:  

NAME  
requests  

DESCRIPTION  
Requests HTTP Library  
~~~~~~~~~~~~~~~~~~~~~  

Requests is an HTTP library, written in Python, for human beings. Basic GET  
usage:  

>>> import requests  
>>> r = requests.get('https://www.python.org')  
>>> r.status_code  
200  
>>> 'Python is a programming language' in r.content  
True  

... or POST:  

>>> payload = dict(key1='value1', key2='value2')  
>>> r = requests.post('https://httpbin.org/post', data=payload)  
>>> print(r.text)  
{  
...  
"form": {  
"key2": "value2",  
"key1": "value1"  
},  
...  
}  

The other HTTP methods are supported - see `requests.api`. Full documentation  
is at <http: python-requests.org="">.  

:copyright: (c) 2017 by Kenneth Reitz.  
:license: Apache 2.0, see LICENSE for more details.  

PACKAGE CONTENTS  
__version__  
_internal_utils  
adapters  
api  
auth  
certs  
compat  
cookies  
exceptions  
help  
hooks  
models  
packages  
sessions  
status_codes  
structures  
utils  

FUNCTIONS  
check_compatibility(urllib3_version, chardet_version)  

DATA  
__author_email__ = 'me@kennethreitz.org'  
__build__ = 139520  
__cake__ = '\u2728 \U0001f370 \u2728'  
__copyright__ = 'Copyright 2018 Kenneth Reitz'  
__description__ = 'Python HTTP for Humans.'  
__license__ = 'Apache 2.0'  
__title__ = 'requests'  
__url__ = 'http://python-requests.org'  
codes =<lookup 'status_codes'="">  

VERSION  
2.21.0  

AUTHOR  
Kenneth Reitz  

FILE  
c:\users\matthijs\appdata\roaming\python\python37\site-packages\requests\__init__.py  

No Python documentation found for 'run_apart'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'run_background'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'run_cmds'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'run_cmds_'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'show_progres'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'stop'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

Help on module subprocess:  

NAME  
subprocess - Subprocesses with accessible I/O streams  

DESCRIPTION  
This module allows you to spawn processes, connect to their  
input/output/error pipes, and obtain their return codes.  

For a complete description of this module see the Python documentation.  

Main API  
========  
run(...): Runs a command, waits for it to complete, then returns a  
CompletedProcess instance.  
Popen(...): A class for flexibly executing a command in a new process  

Constants  
---------  
DEVNULL: Special value that indicates that os.devnull should be used  
PIPE: Special value that indicates a pipe should be created  
STDOUT: Special value that indicates that stderr should go to stdout  

Older API  
=========  
call(...): Runs a command, waits for it to complete, then returns  
the return code.  
check_call(...): Same as call() but raises CalledProcessError()  
if return code is not 0  
check_output(...): Same as check_call() but returns the contents of  
stdout instead of a return code  
getoutput(...): Runs a command in the shell, waits for it to complete,  
then returns the output  
getstatusoutput(...): Runs a command in the shell, waits for it to complete,  
then returns a (exitcode, output) tuple  

CLASSES  
builtins.Exception(builtins.BaseException)  
SubprocessError  
CalledProcessError  
TimeoutExpired  
builtins.object  
CompletedProcess  
Popen  
STARTUPINFO  

class CalledProcessError(SubprocessError)  
| CalledProcessError(returncode, cmd, output=None, stderr=None)  
|  
| Raised when run() is called with check=True and the process  
| returns a non-zero exit status.  
|  
| Attributes:  
| cmd, returncode, stdout, stderr, output  
|  
| Method resolution order:  
| CalledProcessError  
| SubprocessError  
| builtins.Exception  
| builtins.BaseException  
| builtins.object  
|  
| Methods defined here:  
|  
| __init__(self, returncode, cmd, output=None, stderr=None)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
| __str__(self)  
| Return str(self).  
|  
|

* * *

| Data descriptors defined here:  
|  
| stdout  
| Alias for output attribute, to match stderr  
|  
|

* * *

| Data descriptors inherited from SubprocessError:  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
|

* * *

| Static methods inherited from builtins.Exception:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from builtins.BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from builtins.BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class CompletedProcess(builtins.object)  
| CompletedProcess(args, returncode, stdout=None, stderr=None)  
|  
| A process that has finished running.  
|  
| This is returned by run().  
|  
| Attributes:  
| args: The list or str args passed to run().  
| returncode: The exit code of the process, negative for signals.  
| stdout: The standard output (None if not captured).  
| stderr: The standard error (None if not captured).  
|  
| Methods defined here:  
|  
| __init__(self, args, returncode, stdout=None, stderr=None)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
| __repr__(self)  
| Return repr(self).  
|  
| check_returncode(self)  
| Raise CalledProcessError if the exit code is non-zero.  
|  
|

* * *

| Data descriptors defined here:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  

class Popen(builtins.object)  
| Popen(args, bufsize=-1, executable=None, stdin=None, stdout=None, stderr=None, preexec_fn=None, close_fds=True, shell=False, cwd=None, env=None, universal_newlines=None, startupinfo=None, creationflags=0, restore_signals=True, start_new_session=False, pass_fds=(), *, encoding=None, errors=None, text=None)  
|  
| Execute a child program in a new process.  
|  
| For a complete description of the arguments see the Python documentation.  
|  
| Arguments:  
| args: A string, or a sequence of program arguments.  
|  
| bufsize: supplied as the buffering argument to the open() function when  
| creating the stdin/stdout/stderr pipe file objects  
|  
| executable: A replacement program to execute.  
|  
| stdin, stdout and stderr: These specify the executed programs' standard  
| input, standard output and standard error file handles, respectively.  
|  
| preexec_fn: (POSIX only) An object to be called in the child process  
| just before the child is executed.  
|  
| close_fds: Controls closing or inheriting of file descriptors.  
|  
| shell: If true, the command will be executed through the shell.  
|  
| cwd: Sets the current directory before the child is executed.  
|  
| env: Defines the environment variables for the new process.  
|  
| text: If true, decode stdin, stdout and stderr using the given encoding  
| (if set) or the system default otherwise.  
|  
| universal_newlines: Alias of text, provided for backwards compatibility.  
|  
| startupinfo and creationflags (Windows only)  
|  
| restore_signals (POSIX only)  
|  
| start_new_session (POSIX only)  
|  
| pass_fds (POSIX only)  
|  
| encoding and errors: Text mode encoding and error handling to use for  
| file objects stdin, stdout and stderr.  
|  
| Attributes:  
| stdin, stdout, stderr, pid, returncode  
|  
| Methods defined here:  
|  
| __del__(self, _maxsize=9223372036854775807, _warn=<built-in function="" warn="">)  
|  
| __enter__(self)  
|  
| __exit__(self, exc_type, value, traceback)  
|  
| __init__(self, args, bufsize=-1, executable=None, stdin=None, stdout=None, stderr=None, preexec_fn=None, close_fds=True, shell=False, cwd=None, env=None, universal_newlines=None, startupinfo=None, creationflags=0, restore_signals=True, start_new_session=False, pass_fds=(), *, encoding=None, errors=None, text=None)  
| Create new Popen instance.  
|  
| communicate(self, input=None, timeout=None)  
| Interact with process: Send data to stdin and close it.  
| Read data from stdout and stderr, until end-of-file is  
| reached. Wait for process to terminate.  
|  
| The optional "input" argument should be data to be sent to the  
| child process, or None, if no data should be sent to the child.  
| communicate() returns a tuple (stdout, stderr).  
|  
| By default, all communication is in bytes, and therefore any  
| "input" should be bytes, and the (stdout, stderr) will be bytes.  
| If in text mode (indicated by self.text_mode), any "input" should  
| be a string, and (stdout, stderr) will be strings decoded  
| according to locale encoding, or by "encoding" if set. Text mode  
| is triggered by setting any of text, encoding, errors or  
| universal_newlines.  
|  
| kill = terminate(self)  
|  
| poll(self)  
| Check if child process has terminated. Set and return returncode  
| attribute.  
|  
| send_signal(self, sig)  
| Send a signal to the process.  
|  
| terminate(self)  
| Terminates the process.  
|  
| wait(self, timeout=None)  
| Wait for child process to terminate; returns self.returncode.  
|  
|

* * *

| Data descriptors defined here:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
| universal_newlines  

class STARTUPINFO(builtins.object)  
| STARTUPINFO(*, dwFlags=0, hStdInput=None, hStdOutput=None, hStdError=None, wShowWindow=0, lpAttributeList=None)  
|  
| Methods defined here:  
|  
| __init__(self, *, dwFlags=0, hStdInput=None, hStdOutput=None, hStdError=None, wShowWindow=0, lpAttributeList=None)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
|

* * *

| Data descriptors defined here:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  

class SubprocessError(builtins.Exception)  
| Common base class for all non-exit exceptions.  
|  
| Method resolution order:  
| SubprocessError  
| builtins.Exception  
| builtins.BaseException  
| builtins.object  
|  
| Data descriptors defined here:  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
|

* * *

| Methods inherited from builtins.Exception:  
|  
| __init__(self, /, *args, **kwargs)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
|

* * *

| Static methods inherited from builtins.Exception:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from builtins.BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| __str__(self, /)  
| Return str(self).  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from builtins.BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class TimeoutExpired(SubprocessError)  
| TimeoutExpired(cmd, timeout, output=None, stderr=None)  
|  
| This exception is raised when the timeout expires while waiting for a  
| child process.  
|  
| Attributes:  
| cmd, output, stdout, stderr, timeout  
|  
| Method resolution order:  
| TimeoutExpired  
| SubprocessError  
| builtins.Exception  
| builtins.BaseException  
| builtins.object  
|  
| Methods defined here:  
|  
| __init__(self, cmd, timeout, output=None, stderr=None)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
| __str__(self)  
| Return str(self).  
|  
|

* * *

| Data descriptors defined here:  
|  
| stdout  
|  
|

* * *

| Data descriptors inherited from SubprocessError:  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
|

* * *

| Static methods inherited from builtins.Exception:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from builtins.BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from builtins.BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

FUNCTIONS  
call(*popenargs, timeout=None, **kwargs)  
Run command with arguments. Wait for command to complete or  
timeout, then return the returncode attribute.  

The arguments are the same as for the Popen constructor. Example:  

retcode = call(["ls", "-l"])  

check_call(*popenargs, **kwargs)  
Run command with arguments. Wait for command to complete. If  
the exit code was zero then return, otherwise raise  
CalledProcessError. The CalledProcessError object will have the  
return code in the returncode attribute.  

The arguments are the same as for the call function. Example:  

check_call(["ls", "-l"])  

check_output(*popenargs, timeout=None, **kwargs)  
Run command with arguments and return its output.  

If the exit code was non-zero it raises a CalledProcessError. The  
CalledProcessError object will have the return code in the returncode  
attribute and output in the output attribute.  

The arguments are the same as for the Popen constructor. Example:  

>>> check_output(["ls", "-l", "/dev/null"])  
b'crw-rw-rw- 1 root root 1, 3 Oct 18 2007 /dev/null\n'  

The stdout argument is not allowed as it is used internally.  
To capture standard error in the result, use stderr=STDOUT.  

>>> check_output(["/bin/sh", "-c",  
... "ls -l non_existent_file ; exit 0"],  
... stderr=STDOUT)  
b'ls: non_existent_file: No such file or directory\n'  

There is an additional optional argument, "input", allowing you to  
pass a string to the subprocess's stdin. If you use this argument  
you may not also use the Popen constructor's "stdin" argument, as  
it too will be used internally. Example:  

>>> check_output(["sed", "-e", "s/foo/bar/"],  
... input=b"when in the course of fooman events\n")  
b'when in the course of barman events\n'  

By default, all communication is in bytes, and therefore any "input"  
should be bytes, and the return value wil be bytes. If in text mode,  
any "input" should be a string, and the return value will be a string  
decoded according to locale encoding, or by "encoding" if set. Text mode  
is triggered by setting any of text, encoding, errors or universal_newlines.  

getoutput(cmd)  
Return output (stdout or stderr) of executing cmd in a shell.  

Like getstatusoutput(), except the exit status is ignored and the return  
value is a string containing the command's output. Example:  

>>> import subprocess  
>>> subprocess.getoutput('ls /bin/ls')  
'/bin/ls'  

getstatusoutput(cmd)  
Return (exitcode, output) of executing cmd in a shell.  

Execute the string 'cmd' in a shell with 'check_output' and  
return a 2-tuple (status, output). The locale encoding is used  
to decode the output and process newlines.  

A trailing newline is stripped from the output.  
The exit status for the command can be interpreted  
according to the rules for the function 'wait'. Example:  

>>> import subprocess  
>>> subprocess.getstatusoutput('ls /bin/ls')  
(0, '/bin/ls')  
>>> subprocess.getstatusoutput('cat /bin/junk')  
(1, 'cat: /bin/junk: No such file or directory')  
>>> subprocess.getstatusoutput('/bin/junk')  
(127, 'sh: /bin/junk: not found')  
>>> subprocess.getstatusoutput('/bin/kill /lookup>)  
(-15, '')  

run(*popenargs, input=None, capture_output=False, timeout=None, check=False, **kwargs)  
Run command with arguments and return a CompletedProcess instance.  

The returned instance will have attributes args, returncode, stdout and  
stderr. By default, stdout and stderr are not captured, and those attributes  
will be None. Pass stdout=PIPE and/or stderr=PIPE in order to capture them.  

If check is True and the exit code was non-zero, it raises a  
CalledProcessError. The CalledProcessError object will have the return code  
in the returncode attribute, and output & stderr attributes if those streams  
were captured.  

If timeout is given, and the process takes too long, a TimeoutExpired  
exception will be raised.  

There is an optional argument "input", allowing you to  
pass bytes or a string to the subprocess's stdin. If you use this argument  
you may not also use the Popen constructor's "stdin" argument, as  
it will be used internally.  

By default, all communication is in bytes, and therefore any "input" should  
be bytes, and the stdout and stderr will be bytes. If in text mode, any  
"input" should be a string, and stdout and stderr will be strings decoded  
according to locale encoding, or by "encoding" if set. Text mode is  
triggered by setting any of text, encoding, errors or universal_newlines.  

The other arguments are the same as for the Popen constructor.  

DATA  
ABOVE_NORMAL_PRIORITY_CLASS = 32768  
BELOW_NORMAL_PRIORITY_CLASS = 16384  
CREATE_BREAKAWAY_FROM_JOB = 16777216  
CREATE_DEFAULT_ERROR_MODE = 67108864  
CREATE_NEW_CONSOLE = 16  
CREATE_NEW_PROCESS_GROUP = 512  
CREATE_NO_WINDOW = 134217728  
DETACHED_PROCESS = 8  
DEVNULL = -3  
HIGH_PRIORITY_CLASS = 128  
IDLE_PRIORITY_CLASS = 64  
NORMAL_PRIORITY_CLASS = 32  
PIPE = -1  
REALTIME_PRIORITY_CLASS = 256  
STARTF_USESHOWWINDOW = 1  
STARTF_USESTDHANDLES = 256  
STDOUT = -2  
STD_ERROR_HANDLE = 4294967284  
STD_INPUT_HANDLE = 4294967286  
STD_OUTPUT_HANDLE = 4294967285  
SW_HIDE = 0  
__all__ = ['Popen', 'PIPE', 'STDOUT', 'call', 'check_call', 'getstatus...  

FILE  
c:\users\matthijs\appdata\local\programs\python\python37\lib\subprocess.py  

Help on built-in module sys:  

NAME  
sys  

MODULE REFERENCE  
https://docs.python.org/3.7/library/sys  

The following documentation is automatically generated from the Python  
source files. It may be incomplete, incorrect or include features that  
are considered implementation detail and may vary between Python  
implementations. When in doubt, consult the module reference at the  
location listed above.  

DESCRIPTION  
This module provides access to some objects used or maintained by the  
interpreter and to functions that interact strongly with the interpreter.  

Dynamic objects:  

argv -- command line arguments; argv[0] is the script pathname if known  
path -- module search path; path[0] is the script directory, else ''  
modules -- dictionary of loaded modules  

displayhook -- called to show results in an interactive session  
excepthook -- called to handle any uncaught exception other than SystemExit  
To customize printing in an interactive session or to install a custom  
top-level exception handler, assign other functions to replace these.  

stdin -- standard input file object; used by input()  
stdout -- standard output file object; used by print()  
stderr -- standard error object; used for error messages  
By assigning other file objects (or objects that behave like files)  
to these, it is possible to redirect all of the interpreter's I/O.  

last_type -- type of last uncaught exception  
last_value -- value of last uncaught exception  
last_traceback -- traceback of last uncaught exception  
These three are only available in an interactive session after a  
traceback has been printed.  

Static objects:  

builtin_module_names -- tuple of module names built into this interpreter  
copyright -- copyright notice pertaining to this interpreter  
exec_prefix -- prefix used to find the machine-specific Python library  
executable -- absolute path of the executable binary of the Python interpreter  
float_info -- a struct sequence with information about the float implementation.  
float_repr_style -- string indicating the style of repr() output for floats  
hash_info -- a struct sequence with information about the hash algorithm.  
hexversion -- version information encoded as a single integer  
implementation -- Python implementation information.  
int_info -- a struct sequence with information about the int implementation.  
maxsize -- the largest supported length of containers.  
maxunicode -- the value of the largest Unicode code point  
platform -- platform identifier  
prefix -- prefix used to find the Python library  
thread_info -- a struct sequence with information about the thread implementation.  
version -- the version of this interpreter as a string  
version_info -- version information as a named tuple  
dllhandle -- [Windows only] integer handle of the Python DLL  
winver -- [Windows only] version number of the Python DLL  
_enablelegacywindowsfsencoding -- [Windows only]  
__stdin__ -- the original stdin; don't touch!  
__stdout__ -- the original stdout; don't touch!  
__stderr__ -- the original stderr; don't touch!  
__displayhook__ -- the original displayhook; don't touch!  
__excepthook__ -- the original excepthook; don't touch!  

Functions:  

displayhook() -- print an object to the screen, and save it in builtins._  
excepthook() -- print an exception and its traceback to sys.stderr  
exc_info() -- return thread-safe information about the current exception  
exit() -- exit the interpreter by raising SystemExit  
getdlopenflags() -- returns flags to be used for dlopen() calls  
getprofile() -- get the global profiling function  
getrefcount() -- return the reference count for an object (plus one :-)  
getrecursionlimit() -- return the max recursion depth for the interpreter  
getsizeof() -- return the size of an object in bytes  
gettrace() -- get the global debug tracing function  
setcheckinterval() -- control how often the interpreter checks for events  
setdlopenflags() -- set the flags to be used for dlopen() calls  
setprofile() -- set the global profiling function  
setrecursionlimit() -- set the max recursion depth for the interpreter  
settrace() -- set the global debug tracing function  

FUNCTIONS  
__breakpointhook__ = breakpointhook(...)  
breakpointhook(*args, **kws)  

This hook function is called by built-in breakpoint().  

__displayhook__ = displayhook(...)  
displayhook(object) -> None  

Print an object to sys.stdout and also save it in builtins._  

__excepthook__ = excepthook(...)  
excepthook(exctype, value, traceback) -> None  

Handle an exception by displaying it with a traceback on sys.stderr.  

breakpointhook(...)  
breakpointhook(*args, **kws)  

This hook function is called by built-in breakpoint().  

call_tracing(...)  
call_tracing(func, args) -> object  

Call func(*args), while tracing is enabled. The tracing state is  
saved, and restored afterwards. This is intended to be called from  
a debugger from a checkpoint, to recursively debug some other code.  

callstats(...)  
callstats() -> tuple of integers  

Return a tuple of function call statistics, if CALL_PROFILE was defined  
when Python was built. Otherwise, return None.  

When enabled, this function returns detailed, implementation-specific  
details about the number of function calls executed. The return value is  
a 11-tuple where the entries in the tuple are counts of:  
0\. all function calls  
1\. calls to PyFunction_Type objects  
2\. PyFunction calls that do not create an argument tuple  
3\. PyFunction calls that do not create an argument tuple  
and bypass PyEval_EvalCodeEx()  
4\. PyMethod calls  
5\. PyMethod calls on bound methods  
6\. PyType calls  
7\. PyCFunction calls  
8\. generator calls  
9\. All other calls  
10\. Number of stack pops performed by call_function()  

exc_info(...)  
exc_info() -> (type, value, traceback)  

Return information about the most recent exception caught by an except  
clause in the current stack frame or in an older stack frame.  

excepthook(...)  
excepthook(exctype, value, traceback) -> None  

Handle an exception by displaying it with a traceback on sys.stderr.  

exit(...)  
exit([status])  

Exit the interpreter by raising SystemExit(status).  
If the status is omitted or None, it defaults to zero (i.e., success).  
If the status is an integer, it will be used as the system exit status.  
If it is another kind of object, it will be printed and the system  
exit status will be one (i.e., failure).  

get_asyncgen_hooks(...)  
get_asyncgen_hooks()  

Return a namedtuple of installed asynchronous generators hooks (firstiter, finalizer).  

get_coroutine_origin_tracking_depth()  
Check status of origin tracking for coroutine objects in this thread.  

get_coroutine_wrapper(...)  
get_coroutine_wrapper()  

Return the wrapper for coroutine objects set by sys.set_coroutine_wrapper.  

getallocatedblocks(...)  
getallocatedblocks() -> integer  

Return the number of memory blocks currently allocated, regardless of their  
size.  

getcheckinterval(...)  
getcheckinterval() -> current check interval; see setcheckinterval().  

getdefaultencoding(...)  
getdefaultencoding() -> string  

Return the current default string encoding used by the Unicode  
implementation.  

getfilesystemencodeerrors(...)  
getfilesystemencodeerrors() -> string  

Return the error mode used to convert Unicode filenames in  
operating system filenames.  

getfilesystemencoding(...)  
getfilesystemencoding() -> string  

Return the encoding used to convert Unicode filenames in  
operating system filenames.  

getprofile(...)  
getprofile()  

Return the profiling function set with sys.setprofile.  
See the profiler chapter in the library manual.  

getrecursionlimit(...)  
getrecursionlimit()  

Return the current value of the recursion limit, the maximum depth  
of the Python interpreter stack. This limit prevents infinite  
recursion from causing an overflow of the C stack and crashing Python.  

getrefcount(...)  
getrefcount(object) -> integer  

Return the reference count of object. The count returned is generally  
one higher than you might expect, because it includes the (temporary)  
reference as an argument to getrefcount().  

getsizeof(...)  
getsizeof(object, default) -> int  

Return the size of object in bytes.  

getswitchinterval(...)  
getswitchinterval() -> current thread switch interval; see setswitchinterval().  

gettrace(...)  
gettrace()  

Return the global debug tracing function set with sys.settrace.  
See the debugger chapter in the library manual.  

getwindowsversion(...)  
getwindowsversion()  

Return information about the running version of Windows as a named tuple.  
The members are named: major, minor, build, platform, service_pack,  
service_pack_major, service_pack_minor, suite_mask, and product_type. For  
backward compatibility, only the first 5 items are available by indexing.  
All elements are numbers, except service_pack and platform_type which are  
strings, and platform_version which is a 3-tuple. Platform is always 2.  
Product_type may be 1 for a workstation, 2 for a domain controller, 3 for a  
server. Platform_version is a 3-tuple containing a version number that is  
intended for identifying the OS rather than feature detection.  

intern(...)  
intern(string) -> string  

``Intern'' the given string. This enters the string in the (global)  
table of interned strings whose purpose is to speed up dictionary lookups.  
Return the string itself or the previously interned string object with the  
same value.  

is_finalizing(...)  
is_finalizing()  
Return True if Python is exiting.  

set_asyncgen_hooks(...)  
set_asyncgen_hooks(*, firstiter=None, finalizer=None)  

Set a finalizer for async generators objects.  

set_coroutine_origin_tracking_depth(depth)  
Enable or disable origin tracking for coroutine objects in this thread.  

Coroutine objects will track 'depth' frames of traceback information about  
where they came from, available in their cr_origin attribute. Set depth of 0  
to disable.  

set_coroutine_wrapper(...)  
set_coroutine_wrapper(wrapper)  

Set a wrapper for coroutine objects.  

setcheckinterval(...)  
setcheckinterval(n)  

Tell the Python interpreter to check for asynchronous events every  
n instructions. This also affects how often thread switches occur.  

setprofile(...)  
setprofile(function)  

Set the profiling function. It will be called on each function call  
and return. See the profiler chapter in the library manual.  

setrecursionlimit(...)  
setrecursionlimit(n)  

Set the maximum depth of the Python interpreter stack to n. This  
limit prevents infinite recursion from causing an overflow of the C  
stack and crashing Python. The highest possible limit is platform-  
dependent.  

setswitchinterval(...)  
setswitchinterval(n)  

Set the ideal thread switching delay inside the Python interpreter  
The actual frequency of switching threads can be lower if the  
interpreter executes long sequences of uninterruptible code  
(this is implementation-specific and workload-dependent).  

The parameter must represent the desired switching delay in seconds  
A typical value is 0.005 (5 milliseconds).  

settrace(...)  
settrace(function)  

Set the global debug tracing function. It will be called on each  
function call. See the debugger chapter in the library manual.  

DATA  
__stderr__ = None  
__stdin__ = None  
__stdout__ = None  
api_version = 1013  
argv = ['C:/mattie/own lib/own lib/os_sys/frameworks/python_frameworks...  
base_exec_prefix = r'C:\Users\matthijs\AppData\Local\Programs\Python\P...  
base_prefix = r'C:\Users\matthijs\AppData\Local\Programs\Python\Python...  
builtin_module_names = ('_abc', '_ast', '_bisect', '_blake2', '_codecs...  
byteorder = 'little'  
copyright = 'Copyright (c) 2001-2018 Python Software Foundati...ematis...  
dllhandle = 140731667709952  
dont_write_bytecode = False  
exec_prefix = r'C:\Users\matthijs\AppData\Local\Programs\Python\Python...  
executable = r'C:\Users\matthijs\AppData\Local\Programs\Python\Python3...  
flags = sys.flags(debug=0, inspect=0, interactive=0, opt...ation=1, is...  
float_info = sys.float_info(max=1.7976931348623157e+308, max_...epsilo...  
float_repr_style = 'short'  
hash_info = sys.hash_info(width=64, modulus=2305843009213693...iphash2...  
hexversion = 50790640  
implementation = namespace(cache_tag='cpython-37', hexversion=507...in...  
int_info = sys.int_info(bits_per_digit=30, sizeof_digit=4)  
last_value = AttributeError("module 'os_sys' has no attribute 'i'")  
maxsize = 9223372036854775807  
maxunicode = 1114111  
meta_path = [<class '_frozen_importlib.builtinimporter'="">, <class '_fro...="" <br="">modules = {'__builtins__': {'ArithmeticError': <class 'arithmeticerror...="" <br="">path = ['C:/mattie/own lib/own lib/os_sys/frameworks', r'C:\Users\matt...  
path_hooks = [<class 'zipimport.zipimporter'="">, <function filefinder.pa...="" <br="">path_importer_cache = {'C:/mattie/own lib/own lib/os_sys/frameworks': ...  
platform = 'win32'  
prefix = r'C:\Users\matthijs\AppData\Local\Programs\Python\Python37'  
stderr =<idlelib.run.pseudooutputfile object="">  
stdin =<idlelib.run.pseudoinputfile object="">  
stdout =<idlelib.run.pseudooutputfile object="">  
thread_info = sys.thread_info(name='nt', lock=None, version=None)  
version = '3.7.0 (v3.7.0:1bf9cc5093, Jun 27 2018, 04:59:51) [MSC v.191...  
version_info = sys.version_info(major=3, minor=7, micro=0, releaseleve...  
warnoptions = []  
winver = '3.7'  

FILE  
(built-in)  

Help on package test:  

NAME  
test - # Dummy file to make this directory a package.  

PACKAGE CONTENTS  
__main__  
_test_multiprocessing  
ann_module  
ann_module2  
ann_module3  
audiotests  
autotest  
bad_coding  
bad_coding2  
bad_getattr  
bad_getattr2  
bad_getattr3  
badsyntax_3131  
badsyntax_future10  
badsyntax_future3  
badsyntax_future4  
badsyntax_future5  
badsyntax_future6  
badsyntax_future7  
badsyntax_future8  
badsyntax_future9  
badsyntax_pep3120  
bisect  
bytecode_helper  
coding20731  
curses_tests  
dataclass_module_1  
dataclass_module_1_str  
dataclass_module_2  
dataclass_module_2_str  
datetimetester  
dis_module  
doctest_aliases  
double_const  
encoded_modules (package)  
final_a  
final_b  
fork_wait  
future_test1  
future_test2  
gdb_sample  
good_getattr  
imp_dummy  
inspect_fodder  
inspect_fodder2  
leakers (package)  
libregrtest (package)  
list_tests  
lock_tests  
make_ssl_certs  
mapping_tests  
memory_watchdog  
mock_socket  
mod_generics_cache  
mp_fork_bomb  
mp_preload  
multibytecodec_support  
outstanding_bugs  
pickletester  
profilee  
pyclbr_input  
pydoc_mod  
pydocfodder  
pythoninfo  
re_tests  
regrtest  
relimport  
reperf  
sample_doctest  
sample_doctest_no_docstrings  
sample_doctest_no_doctests  
seq_tests  
signalinterproctester  
sortperf  
ssl_servers  
ssltests  
string_tests  
support (package)  
test___all__  
test___future__  
test__locale  
test__opcode  
test__osx_support  
test_abc  
test_abstract_numbers  
test_aifc  
test_argparse  
test_array  
test_asdl_parser  
test_ast  
test_asyncgen  
test_asynchat  
test_asyncio (package)  
test_asyncore  
test_atexit  
test_audioop  
test_augassign  
test_base64  
test_baseexception  
test_bdb  
test_bigaddrspace  
test_bigmem  
test_binascii  
test_binhex  
test_binop  
test_bisect  
test_bool  
test_buffer  
test_bufio  
test_builtin  
test_bytes  
test_bz2  
test_c_locale_coercion  
test_calendar  
test_call  
test_capi  
test_cgi  
test_cgitb  
test_charmapcodec  
test_class  
test_cmath  
test_cmd  
test_cmd_line  
test_cmd_line_script  
test_code  
test_code_module  
test_codeccallbacks  
test_codecencodings_cn  
test_codecencodings_hk  
test_codecencodings_iso2022  
test_codecencodings_jp  
test_codecencodings_kr  
test_codecencodings_tw  
test_codecmaps_cn  
test_codecmaps_hk  
test_codecmaps_jp  
test_codecmaps_kr  
test_codecmaps_tw  
test_codecs  
test_codeop  
test_collections  
test_colorsys  
test_compare  
test_compile  
test_compileall  
test_complex  
test_concurrent_futures  
test_configparser  
test_contains  
test_context  
test_contextlib  
test_contextlib_async  
test_copy  
test_copyreg  
test_coroutines  
test_cprofile  
test_crashers  
test_crypt  
test_csv  
test_ctypes  
test_curses  
test_dataclasses  
test_datetime  
test_dbm  
test_dbm_dumb  
test_dbm_gnu  
test_dbm_ndbm  
test_decimal  
test_decorators  
test_defaultdict  
test_deque  
test_descr  
test_descrtut  
test_devpoll  
test_dict  
test_dict_version  
test_dictcomps  
test_dictviews  
test_difflib  
test_dis  
test_distutils  
test_doctest  
test_doctest2  
test_docxmlrpc  
test_dtrace  
test_dummy_thread  
test_dummy_threading  
test_dynamic  
test_dynamicclassattribute  
test_eintr  
test_email (package)  
test_embed  
test_ensurepip  
test_enum  
test_enumerate  
test_eof  
test_epoll  
test_errno  
test_exception_hierarchy  
test_exception_variations  
test_exceptions  
test_extcall  
test_faulthandler  
test_fcntl  
test_file  
test_file_eintr  
test_filecmp  
test_fileinput  
test_fileio  
test_finalization  
test_float  
test_flufl  
test_fnmatch  
test_fork1  
test_format  
test_fractions  
test_frame  
test_frozen  
test_fstring  
test_ftplib  
test_funcattrs  
test_functools  
test_future  
test_future3  
test_future4  
test_future5  
test_gc  
test_gdb  
test_generator_stop  
test_generators  
test_genericclass  
test_genericpath  
test_genexps  
test_getargs2  
test_getopt  
test_getpass  
test_gettext  
test_glob  
test_global  
test_grammar  
test_grp  
test_gzip  
test_hash  
test_hashlib  
test_heapq  
test_hmac  
test_html  
test_htmlparser  
test_http_cookiejar  
test_http_cookies  
test_httplib  
test_httpservers  
test_idle  
test_imaplib  
test_imghdr  
test_imp  
test_import (package)  
test_importlib (package)  
test_index  
test_inspect  
test_int  
test_int_literal  
test_io  
test_ioctl  
test_ipaddress  
test_isinstance  
test_iter  
test_iterlen  
test_itertools  
test_json (package)  
test_keyword  
test_keywordonlyarg  
test_kqueue  
test_largefile  
test_lib2to3  
test_linecache  
test_list  
test_listcomps  
test_locale  
test_logging  
test_long  
test_longexp  
test_lzma  
test_macpath  
test_mailbox  
test_mailcap  
test_marshal  
test_math  
test_memoryio  
test_memoryview  
test_metaclass  
test_mimetypes  
test_minidom  
test_mmap  
test_module  
test_modulefinder  
test_msilib  
test_multibytecodec  
test_multiprocessing_fork  
test_multiprocessing_forkserver  
test_multiprocessing_main_handling  
test_multiprocessing_spawn  
test_netrc  
test_nis  
test_nntplib  
test_normalization  
test_ntpath  
test_numeric_tower  
test_opcodes  
test_openpty  
test_operator  
test_optparse  
test_ordered_dict  
test_os  
test_ossaudiodev  
test_osx_env  
test_parser  
test_pathlib  
test_pdb  
test_peepholer  
test_pickle  
test_pickletools  
test_pipes  
test_pkg  
test_pkgimport  
test_pkgutil  
test_platform  
test_plistlib  
test_poll  
test_popen  
test_poplib  
test_posix  
test_posixpath  
test_pow  
test_pprint  
test_print  
test_profile  
test_property  
test_pstats  
test_pty  
test_pulldom  
test_pwd  
test_py_compile  
test_pyclbr  
test_pydoc  
test_pyexpat  
test_queue  
test_quopri  
test_raise  
test_random  
test_range  
test_re  
test_readline  
test_regrtest  
test_repl  
test_reprlib  
test_resource  
test_richcmp  
test_rlcompleter  
test_robotparser  
test_runpy  
test_sax  
test_sched  
test_scope  
test_script_helper  
test_secrets  
test_select  
test_selectors  
test_set  
test_setcomps  
test_shelve  
test_shlex  
test_shutil  
test_signal  
test_site  
test_slice  
test_smtpd  
test_smtplib  
test_smtpnet  
test_sndhdr  
test_socket  
test_socketserver  
test_sort  
test_source_encoding  
test_spwd  
test_sqlite  
test_ssl  
test_startfile  
test_stat  
test_statistics  
test_strftime  
test_string  
test_string_literals  
test_stringprep  
test_strptime  
test_strtod  
test_struct  
test_structmembers  
test_structseq  
test_subclassinit  
test_subprocess  
test_sunau  
test_sundry  
test_super  
test_support  
test_symbol  
test_symtable  
test_syntax  
test_sys  
test_sys_setprofile  
test_sys_settrace  
test_sysconfig  
test_syslog  
test_tarfile  
test_tcl  
test_telnetlib  
test_tempfile  
test_textwrap  
test_thread  
test_threaded_import  
test_threadedtempfile  
test_threading  
test_threading_local  
test_threadsignals  
test_time  
test_timeit  
test_timeout  
test_tix  
test_tk  
test_tokenize  
test_tools (package)  
test_trace  
test_traceback  
test_tracemalloc  
test_ttk_guionly  
test_ttk_textonly  
test_tuple  
test_turtle  
test_typechecks  
test_types  
test_typing  
test_ucn  
test_unary  
test_unicode  
test_unicode_file  
test_unicode_file_functions  
test_unicode_identifiers  
test_unicodedata  
test_unittest  
test_univnewlines  
test_unpack  
test_unpack_ex  
test_urllib  
test_urllib2  
test_urllib2_localnet  
test_urllib2net  
test_urllib_response  
test_urllibnet  
test_urlparse  
test_userdict  
test_userlist  
test_userstring  
test_utf8_mode  
test_utf8source  
test_uu  
test_uuid  
test_venv  
test_wait3  
test_wait4  
test_warnings (package)  
test_wave  
test_weakref  
test_weakset  
test_webbrowser  
test_winconsoleio  
test_winreg  
test_winsound  
test_with  
test_wsgiref  
test_xdrlib  
test_xml_dom_minicompat  
test_xml_etree  
test_xml_etree_c  
test_xmlrpc  
test_xmlrpc_net  
test_xxtestfuzz  
test_yield_from  
test_zipapp  
test_zipfile  
test_zipfile64  
test_zipimport  
test_zipimport_support  
test_zlib  
testcodec  
tf_inherit_check  
threaded_import_hangers  
time_hashlib  
tracedmodules (package)  
win_console_handler  
xmltests  

FILE  
c:\users\matthijs\appdata\local\programs\python\python37\lib\test\__init__.py  

Help on module threading:  

NAME  
threading - Thread module emulating a subset of Java's threading model.  

CLASSES  
builtins.Exception(builtins.BaseException)  
builtins.RuntimeError  
BrokenBarrierError  
builtins.object  
_thread._local  
Barrier  
Condition  
Event  
Semaphore  
BoundedSemaphore  
Thread  
Timer  

class Barrier(builtins.object)  
| Barrier(parties, action=None, timeout=None)  
|  
| Implements a Barrier.  
|  
| Useful for synchronizing a fixed number of threads at known synchronization  
| points. Threads block on 'wait()' and are simultaneously once they have all  
| made that call.  
|  
| Methods defined here:  
|  
| __init__(self, parties, action=None, timeout=None)  
| Create a barrier, initialised to 'parties' threads.  
|  
| 'action' is a callable which, when supplied, will be called by one of  
| the threads after they have all entered the barrier and just prior to  
| releasing them all. If a 'timeout' is provided, it is uses as the  
| default for all subsequent 'wait()' calls.  
|  
| abort(self)  
| Place the barrier into a 'broken' state.  
|  
| Useful in case of error. Any currently waiting threads and threads  
| attempting to 'wait()' will have BrokenBarrierError raised.  
|  
| reset(self)  
| Reset the barrier to the initial state.  
|  
| Any threads currently waiting will get the BrokenBarrier exception  
| raised.  
|  
| wait(self, timeout=None)  
| Wait for the barrier.  
|  
| When the specified number of threads have started waiting, they are all  
| simultaneously awoken. If an 'action' was provided for the barrier, one  
| of the threads will have executed that callback prior to returning.  
| Returns an individual index number from 0 to 'parties-1'.  
|  
|

* * *

| Data descriptors defined here:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
| broken  
| Return True if the barrier is in a broken state.  
|  
| n_waiting  
| Return the number of threads currently waiting at the barrier.  
|  
| parties  
| Return the number of threads required to trip the barrier.  

class BoundedSemaphore(Semaphore)  
| BoundedSemaphore(value=1)  
|  
| Implements a bounded semaphore.  
|  
| A bounded semaphore checks to make sure its current value doesn't exceed its  
| initial value. If it does, ValueError is raised. In most situations  
| semaphores are used to guard resources with limited capacity.  
|  
| If the semaphore is released too many times it's a sign of a bug. If not  
| given, value defaults to 1.  
|  
| Like regular semaphores, bounded semaphores manage a counter representing  
| the number of release() calls minus the number of acquire() calls, plus an  
| initial value. The acquire() method blocks if necessary until it can return  
| without making the counter negative. If not given, value defaults to 1.  
|  
| Method resolution order:  
| BoundedSemaphore  
| Semaphore  
| builtins.object  
|  
| Methods defined here:  
|  
| __init__(self, value=1)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
| release(self)  
| Release a semaphore, incrementing the internal counter by one.  
|  
| When the counter is zero on entry and another thread is waiting for it  
| to become larger than zero again, wake up that thread.  
|  
| If the number of releases exceeds the number of acquires,  
| raise a ValueError.  
|  
|

* * *

| Methods inherited from Semaphore:  
|  
| __enter__ = acquire(self, blocking=True, timeout=None)  
| Acquire a semaphore, decrementing the internal counter by one.  
|  
| When invoked without arguments: if the internal counter is larger than  
| zero on entry, decrement it by one and return immediately. If it is zero  
| on entry, block, waiting until some other thread has called release() to  
| make it larger than zero. This is done with proper interlocking so that  
| if multiple acquire() calls are blocked, release() will wake exactly one  
| of them up. The implementation may pick one at random, so the order in  
| which blocked threads are awakened should not be relied on. There is no  
| return value in this case.  
|  
| When invoked with blocking set to true, do the same thing as when called  
| without arguments, and return true.  
|  
| When invoked with blocking set to false, do not block. If a call without  
| an argument would block, return false immediately; otherwise, do the  
| same thing as when called without arguments, and return true.  
|  
| When invoked with a timeout other than None, it will block for at  
| most timeout seconds. If acquire does not complete successfully in  
| that interval, return false. Return true otherwise.  
|  
| __exit__(self, t, v, tb)  
|  
| acquire(self, blocking=True, timeout=None)  
| Acquire a semaphore, decrementing the internal counter by one.  
|  
| When invoked without arguments: if the internal counter is larger than  
| zero on entry, decrement it by one and return immediately. If it is zero  
| on entry, block, waiting until some other thread has called release() to  
| make it larger than zero. This is done with proper interlocking so that  
| if multiple acquire() calls are blocked, release() will wake exactly one  
| of them up. The implementation may pick one at random, so the order in  
| which blocked threads are awakened should not be relied on. There is no  
| return value in this case.  
|  
| When invoked with blocking set to true, do the same thing as when called  
| without arguments, and return true.  
|  
| When invoked with blocking set to false, do not block. If a call without  
| an argument would block, return false immediately; otherwise, do the  
| same thing as when called without arguments, and return true.  
|  
| When invoked with a timeout other than None, it will block for at  
| most timeout seconds. If acquire does not complete successfully in  
| that interval, return false. Return true otherwise.  
|  
|

* * *

| Data descriptors inherited from Semaphore:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  

class BrokenBarrierError(builtins.RuntimeError)  
| Unspecified run-time error.  
|  
| Method resolution order:  
| BrokenBarrierError  
| builtins.RuntimeError  
| builtins.Exception  
| builtins.BaseException  
| builtins.object  
|  
| Data descriptors defined here:  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
|

* * *

| Methods inherited from builtins.RuntimeError:  
|  
| __init__(self, /, *args, **kwargs)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
|

* * *

| Static methods inherited from builtins.RuntimeError:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from builtins.BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| __str__(self, /)  
| Return str(self).  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from builtins.BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class Condition(builtins.object)  
| Condition(lock=None)  
|  
| Class that implements a condition variable.  
|  
| A condition variable allows one or more threads to wait until they are  
| notified by another thread.  
|  
| If the lock argument is given and not None, it must be a Lock or RLock  
| object, and it is used as the underlying lock. Otherwise, a new RLock object  
| is created and used as the underlying lock.  
|  
| Methods defined here:  
|  
| __enter__(self)  
|  
| __exit__(self, *args)  
|  
| __init__(self, lock=None)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
| __repr__(self)  
| Return repr(self).  
|  
| notify(self, n=1)  
| Wake up one or more threads waiting on this condition, if any.  
|  
| If the calling thread has not acquired the lock when this method is  
| called, a RuntimeError is raised.  
|  
| This method wakes up at most n of the threads waiting for the condition  
| variable; it is a no-op if no threads are waiting.  
|  
| notifyAll = notify_all(self)  
|  
| notify_all(self)  
| Wake up all threads waiting on this condition.  
|  
| If the calling thread has not acquired the lock when this method  
| is called, a RuntimeError is raised.  
|  
| wait(self, timeout=None)  
| Wait until notified or until a timeout occurs.  
|  
| If the calling thread has not acquired the lock when this method is  
| called, a RuntimeError is raised.  
|  
| This method releases the underlying lock, and then blocks until it is  
| awakened by a notify() or notify_all() call for the same condition  
| variable in another thread, or until the optional timeout occurs. Once  
| awakened or timed out, it re-acquires the lock and returns.  
|  
| When the timeout argument is present and not None, it should be a  
| floating point number specifying a timeout for the operation in seconds  
| (or fractions thereof).  
|  
| When the underlying lock is an RLock, it is not released using its  
| release() method, since this may not actually unlock the lock when it  
| was acquired multiple times recursively. Instead, an internal interface  
| of the RLock class is used, which really unlocks it even when it has  
| been recursively acquired several times. Another internal interface is  
| then used to restore the recursion level when the lock is reacquired.  
|  
| wait_for(self, predicate, timeout=None)  
| Wait until a condition evaluates to True.  
|  
| predicate should be a callable which result will be interpreted as a  
| boolean value. A timeout may be provided giving the maximum time to  
| wait.  
|  
|

* * *

| Data descriptors defined here:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  

class Event(builtins.object)  
| Class implementing event objects.  
|  
| Events manage a flag that can be set to true with the set() method and reset  
| to false with the clear() method. The wait() method blocks until the flag is  
| true. The flag is initially false.  
|  
| Methods defined here:  
|  
| __init__(self)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
| clear(self)  
| Reset the internal flag to false.  
|  
| Subsequently, threads calling wait() will block until set() is called to  
| set the internal flag to true again.  
|  
| isSet = is_set(self)  
|  
| is_set(self)  
| Return true if and only if the internal flag is true.  
|  
| set(self)  
| Set the internal flag to true.  
|  
| All threads waiting for it to become true are awakened. Threads  
| that call wait() once the flag is true will not block at all.  
|  
| wait(self, timeout=None)  
| Block until the internal flag is true.  
|  
| If the internal flag is true on entry, return immediately. Otherwise,  
| block until another thread calls set() to set the flag to true, or until  
| the optional timeout occurs.  
|  
| When the timeout argument is present and not None, it should be a  
| floating point number specifying a timeout for the operation in seconds  
| (or fractions thereof).  
|  
| This method returns the internal flag on exit, so it will always return  
| True except if a timeout is given and the operation times out.  
|  
|

* * *

| Data descriptors defined here:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  

class Semaphore(builtins.object)  
| Semaphore(value=1)  
|  
| This class implements semaphore objects.  
|  
| Semaphores manage a counter representing the number of release() calls minus  
| the number of acquire() calls, plus an initial value. The acquire() method  
| blocks if necessary until it can return without making the counter  
| negative. If not given, value defaults to 1.  
|  
| Methods defined here:  
|  
| __enter__ = acquire(self, blocking=True, timeout=None)  
|  
| __exit__(self, t, v, tb)  
|  
| __init__(self, value=1)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
| acquire(self, blocking=True, timeout=None)  
| Acquire a semaphore, decrementing the internal counter by one.  
|  
| When invoked without arguments: if the internal counter is larger than  
| zero on entry, decrement it by one and return immediately. If it is zero  
| on entry, block, waiting until some other thread has called release() to  
| make it larger than zero. This is done with proper interlocking so that  
| if multiple acquire() calls are blocked, release() will wake exactly one  
| of them up. The implementation may pick one at random, so the order in  
| which blocked threads are awakened should not be relied on. There is no  
| return value in this case.  
|  
| When invoked with blocking set to true, do the same thing as when called  
| without arguments, and return true.  
|  
| When invoked with blocking set to false, do not block. If a call without  
| an argument would block, return false immediately; otherwise, do the  
| same thing as when called without arguments, and return true.  
|  
| When invoked with a timeout other than None, it will block for at  
| most timeout seconds. If acquire does not complete successfully in  
| that interval, return false. Return true otherwise.  
|  
| release(self)  
| Release a semaphore, incrementing the internal counter by one.  
|  
| When the counter is zero on entry and another thread is waiting for it  
| to become larger than zero again, wake up that thread.  
|  
|

* * *

| Data descriptors defined here:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  

class Thread(builtins.object)  
| Thread(group=None, target=None, name=None, args=(), kwargs=None, *, daemon=None)  
|  
| A class that represents a thread of control.  
|  
| This class can be safely subclassed in a limited fashion. There are two ways  
| to specify the activity: by passing a callable object to the constructor, or  
| by overriding the run() method in a subclass.  
|  
| Methods defined here:  
|  
| __init__(self, group=None, target=None, name=None, args=(), kwargs=None, *, daemon=None)  
| This constructor should always be called with keyword arguments. Arguments are:  
|  
| *group* should be None; reserved for future extension when a ThreadGroup  
| class is implemented.  
|  
| *target* is the callable object to be invoked by the run()  
| method. Defaults to None, meaning nothing is called.  
|  
| *name* is the thread name. By default, a unique name is constructed of  
| the form "Thread-N" where N is a small decimal number.  
|  
| *args* is the argument tuple for the target invocation. Defaults to ().  
|  
| *kwargs* is a dictionary of keyword arguments for the target  
| invocation. Defaults to {}.  
|  
| If a subclass overrides the constructor, it must make sure to invoke  
| the base class constructor (Thread.__init__()) before doing anything  
| else to the thread.  
|  
| __repr__(self)  
| Return repr(self).  
|  
| getName(self)  
|  
| isAlive = is_alive(self)  
|  
| isDaemon(self)  
|  
| is_alive(self)  
| Return whether the thread is alive.  
|  
| This method returns True just before the run() method starts until just  
| after the run() method terminates. The module function enumerate()  
| returns a list of all alive threads.  
|  
| join(self, timeout=None)  
| Wait until the thread terminates.  
|  
| This blocks the calling thread until the thread whose join() method is  
| called terminates -- either normally or through an unhandled exception  
| or until the optional timeout occurs.  
|  
| When the timeout argument is present and not None, it should be a  
| floating point number specifying a timeout for the operation in seconds  
| (or fractions thereof). As join() always returns None, you must call  
| isAlive() after join() to decide whether a timeout happened -- if the  
| thread is still alive, the join() call timed out.  
|  
| When the timeout argument is not present or None, the operation will  
| block until the thread terminates.  
|  
| A thread can be join()ed many times.  
|  
| join() raises a RuntimeError if an attempt is made to join the current  
| thread as that would cause a deadlock. It is also an error to join() a  
| thread before it has been started and attempts to do so raises the same  
| exception.  
|  
| run(self)  
| Method representing the thread's activity.  
|  
| You may override this method in a subclass. The standard run() method  
| invokes the callable object passed to the object's constructor as the  
| target argument, if any, with sequential and keyword arguments taken  
| from the args and kwargs arguments, respectively.  
|  
| setDaemon(self, daemonic)  
|  
| setName(self, name)  
|  
| start(self)  
| Start the thread's activity.  
|  
| It must be called at most once per thread object. It arranges for the  
| object's run() method to be invoked in a separate thread of control.  
|  
| This method will raise a RuntimeError if called more than once on the  
| same thread object.  
|  
|

* * *

| Data descriptors defined here:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
| daemon  
| A boolean value indicating whether this thread is a daemon thread.  
|  
| This must be set before start() is called, otherwise RuntimeError is  
| raised. Its initial value is inherited from the creating thread; the  
| main thread is not a daemon thread and therefore all threads created in  
| the main thread default to daemon = False.  
|  
| The entire Python program exits when no alive non-daemon threads are  
| left.  
|  
| ident  
| Thread identifier of this thread or None if it has not been started.  
|  
| This is a nonzero integer. See the get_ident() function. Thread  
| identifiers may be recycled when a thread exits and another thread is  
| created. The identifier is available even after the thread has exited.  
|  
| name  
| A string used for identification purposes only.  
|  
| It has no semantics. Multiple threads may be given the same name. The  
| initial name is set by the constructor.  

ThreadError = class RuntimeError(Exception)  
| Unspecified run-time error.  
|  
| Method resolution order:  
| RuntimeError  
| Exception  
| BaseException  
| object  
|  
| Methods defined here:  
|  
| __init__(self, /, *args, **kwargs)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| __str__(self, /)  
| Return str(self).  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class Timer(Thread)  
| Timer(interval, function, args=None, kwargs=None)  
|  
| Call a function after a specified number of seconds:  
|  
| t = Timer(30.0, f, args=None, kwargs=None)  
| t.start()  
| t.cancel() # stop the timer's action if it's still waiting  
|  
| Method resolution order:  
| Timer  
| Thread  
| builtins.object  
|  
| Methods defined here:  
|  
| __init__(self, interval, function, args=None, kwargs=None)  
| This constructor should always be called with keyword arguments. Arguments are:  
|  
| *group* should be None; reserved for future extension when a ThreadGroup  
| class is implemented.  
|  
| *target* is the callable object to be invoked by the run()  
| method. Defaults to None, meaning nothing is called.  
|  
| *name* is the thread name. By default, a unique name is constructed of  
| the form "Thread-N" where N is a small decimal number.  
|  
| *args* is the argument tuple for the target invocation. Defaults to ().  
|  
| *kwargs* is a dictionary of keyword arguments for the target  
| invocation. Defaults to {}.  
|  
| If a subclass overrides the constructor, it must make sure to invoke  
| the base class constructor (Thread.__init__()) before doing anything  
| else to the thread.  
|  
| cancel(self)  
| Stop the timer if it hasn't finished yet.  
|  
| run(self)  
| Method representing the thread's activity.  
|  
| You may override this method in a subclass. The standard run() method  
| invokes the callable object passed to the object's constructor as the  
| target argument, if any, with sequential and keyword arguments taken  
| from the args and kwargs arguments, respectively.  
|  
|

* * *

| Methods inherited from Thread:  
|  
| __repr__(self)  
| Return repr(self).  
|  
| getName(self)  
|  
| isAlive = is_alive(self)  
| Return whether the thread is alive.  
|  
| This method returns True just before the run() method starts until just  
| after the run() method terminates. The module function enumerate()  
| returns a list of all alive threads.  
|  
| isDaemon(self)  
|  
| is_alive(self)  
| Return whether the thread is alive.  
|  
| This method returns True just before the run() method starts until just  
| after the run() method terminates. The module function enumerate()  
| returns a list of all alive threads.  
|  
| join(self, timeout=None)  
| Wait until the thread terminates.  
|  
| This blocks the calling thread until the thread whose join() method is  
| called terminates -- either normally or through an unhandled exception  
| or until the optional timeout occurs.  
|  
| When the timeout argument is present and not None, it should be a  
| floating point number specifying a timeout for the operation in seconds  
| (or fractions thereof). As join() always returns None, you must call  
| isAlive() after join() to decide whether a timeout happened -- if the  
| thread is still alive, the join() call timed out.  
|  
| When the timeout argument is not present or None, the operation will  
| block until the thread terminates.  
|  
| A thread can be join()ed many times.  
|  
| join() raises a RuntimeError if an attempt is made to join the current  
| thread as that would cause a deadlock. It is also an error to join() a  
| thread before it has been started and attempts to do so raises the same  
| exception.  
|  
| setDaemon(self, daemonic)  
|  
| setName(self, name)  
|  
| start(self)  
| Start the thread's activity.  
|  
| It must be called at most once per thread object. It arranges for the  
| object's run() method to be invoked in a separate thread of control.  
|  
| This method will raise a RuntimeError if called more than once on the  
| same thread object.  
|  
|

* * *

| Data descriptors inherited from Thread:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
| daemon  
| A boolean value indicating whether this thread is a daemon thread.  
|  
| This must be set before start() is called, otherwise RuntimeError is  
| raised. Its initial value is inherited from the creating thread; the  
| main thread is not a daemon thread and therefore all threads created in  
| the main thread default to daemon = False.  
|  
| The entire Python program exits when no alive non-daemon threads are  
| left.  
|  
| ident  
| Thread identifier of this thread or None if it has not been started.  
|  
| This is a nonzero integer. See the get_ident() function. Thread  
| identifiers may be recycled when a thread exits and another thread is  
| created. The identifier is available even after the thread has exited.  
|  
| name  
| A string used for identification purposes only.  
|  
| It has no semantics. Multiple threads may be given the same name. The  
| initial name is set by the constructor.  

local = class _local(builtins.object)  
| Thread-local data  
|  
| Methods defined here:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  

FUNCTIONS  
Lock = allocate_lock(...)  
allocate_lock() -> lock object  
(allocate() is an obsolete synonym)  

Create a new lock object. See help(type(threading.Lock())) for  
information about locks.  

RLock(*args, **kwargs)  
Factory function that returns a new reentrant lock.  

A reentrant lock must be released by the thread that acquired it. Once a  
thread has acquired a reentrant lock, the same thread may acquire it again  
without blocking; the thread must release it once for each time it has  
acquired it.  

active_count()  
Return the number of Thread objects currently alive.  

The returned count is equal to the length of the list returned by  
enumerate().  

current_thread()  
Return the current Thread object, corresponding to the caller's thread of control.  

If the caller's thread of control was not created through the threading  
module, a dummy thread object with limited functionality is returned.  

enumerate()  
Return a list of all Thread objects currently alive.  

The list includes daemonic threads, dummy thread objects created by  
current_thread(), and the main thread. It excludes terminated threads and  
threads that have not yet been started.  

get_ident(...)  
get_ident() -> integer  

Return a non-zero integer that uniquely identifies the current thread  
amongst other threads that exist simultaneously.  
This may be used to identify per-thread resources.  
Even though on some platforms threads identities may appear to be  
allocated consecutive numbers starting at 1, this behavior should not  
be relied upon, and the number should be seen purely as a magic cookie.  
A thread's identity may be reused for another thread after it exits.  

main_thread()  
Return the main thread object.  

In normal conditions, the main thread is the thread from which the  
Python interpreter was started.  

setprofile(func)  
Set a profile function for all threads started from the threading module.  

The func will be passed to sys.setprofile() for each thread, before its  
run() method is called.  

settrace(func)  
Set a trace function for all threads started from the threading module.  

The func will be passed to sys.settrace() for each thread, before its run()  
method is called.  

stack_size(...)  
stack_size([size]) -> size  

Return the thread stack size used when creating new threads. The  
optional size argument specifies the stack size (in bytes) to be used  
for subsequently created threads, and must be 0 (use platform or  
configured default) or a positive integer value of at least 32,768 (32k).  
If changing the thread stack size is unsupported, a ThreadError  
exception is raised. If the specified size is invalid, a ValueError  
exception is raised, and the stack size is unmodified. 32k bytes  
currently the minimum supported stack size value to guarantee  
sufficient stack space for the interpreter itself.  

Note that some platforms may have particular restrictions on values for  
the stack size, such as requiring a minimum stack size larger than 32 KiB or  
requiring allocation in multiples of the system memory page size  
- platform documentation should be referred to for more information  
(4 KiB pages are common; using multiples of 4096 for the stack size is  
the suggested approach in the absence of more specific information).  

DATA  
TIMEOUT_MAX = 4294967.0  
__all__ = ['get_ident', 'active_count', 'Condition', 'current_thread',...  

FILE  
c:\users\matthijs\appdata\local\programs\python\python37\lib\threading.py  

Help on built-in module time:  

NAME  
time - This module provides various functions to manipulate time values.  

DESCRIPTION  
There are two standard representations of time. One is the number  
of seconds since the Epoch, in UTC (a.k.a. GMT). It may be an integer  
or a floating point number (to represent fractions of seconds).  
The Epoch is system-defined; on Unix, it is generally January 1st, 1970.  
The actual value can be retrieved by calling gmtime(0).  

The other representation is a tuple of 9 integers giving local time.  
The tuple items are:  
year (including century, e.g. 1998)  
month (1-12)  
day (1-31)  
hours (0-23)  
minutes (0-59)  
seconds (0-59)  
weekday (0-6, Monday is 0)  
Julian day (day in the year, 1-366)  
DST (Daylight Savings Time) flag (-1, 0 or 1)  
If the DST flag is 0, the time is given in the regular time zone;  
if it is 1, the time is given in the DST time zone;  
if it is -1, mktime() should guess based on the date and time.  

CLASSES  
builtins.tuple(builtins.object)  
struct_time  

class struct_time(builtins.tuple)  
| struct_time(iterable=(), /)  
|  
| The time value as returned by gmtime(), localtime(), and strptime(), and  
| accepted by asctime(), mktime() and strftime(). May be considered as a  
| sequence of 9 integers.  
|  
| Note that several fields' values are not the same as those defined by  
| the C language standard for struct tm. For example, the value of the  
| field tm_year is the actual year, not year - 1900\. See individual  
| fields' descriptions for details.  
|  
| Method resolution order:  
| struct_time  
| builtins.tuple  
| builtins.object  
|  
| Methods defined here:  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Data descriptors defined here:  
|  
| tm_gmtoff  
| offset from UTC in seconds  
|  
| tm_hour  
| hours, range [0, 23]  
|  
| tm_isdst  
| 1 if summer time is in effect, 0 if not, and -1 if unknown  
|  
| tm_mday  
| day of month, range [1, 31]  
|  
| tm_min  
| minutes, range [0, 59]  
|  
| tm_mon  
| month of year, range [1, 12]  
|  
| tm_sec  
| seconds, range [0, 61])  
|  
| tm_wday  
| day of week, range [0, 6], Monday is 0  
|  
| tm_yday  
| day of year, range [1, 366]  
|  
| tm_year  
| year, for example, 1993  
|  
| tm_zone  
| abbreviation of timezone name  
|  
|

* * *

| Data and other attributes defined here:  
|  
| n_fields = 11  
|  
| n_sequence_fields = 9  
|  
| n_unnamed_fields = 0  
|  
|

* * *

| Methods inherited from builtins.tuple:  
|  
| __add__(self, value, /)  
| Return self+value.  
|  
| __contains__(self, key, /)  
| Return key in self.  
|  
| __eq__(self, value, /)  
| Return self==value.  
|  
| __ge__(self, value, /)  
| Return self>=value.  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __getitem__(self, key, /)  
| Return self[key].  
|  
| __getnewargs__(self, /)  
|  
| __gt__(self, value, /)  
| Return self>value.  
|  
| __hash__(self, /)  
| Return hash(self).  
|  
| __iter__(self, /)  
| Implement iter(self).  
|  
| __le__(self, value, /)  
| Return self<=value.  
|  
| __len__(self, /)  
| Return len(self).  
|  
| __lt__(self, value, /)  
| Return self <value. <br="">|  
| __mul__(self, value, /)  
| Return self*value.  
|  
| __ne__(self, value, /)  
| Return self!=value.  
|  
| __rmul__(self, value, /)  
| Return value*self.  
|  
| count(self, value, /)  
| Return number of occurrences of value.  
|  
| index(self, value, start=0, stop=9223372036854775807, /)  
| Return first index of value.  
|  
| Raises ValueError if the value is not present.  

FUNCTIONS  
asctime(...)  
asctime([tuple]) -> string  

Convert a time tuple to a string, e.g. 'Sat Jun 06 16:26:11 1998'.  
When the time tuple is not present, current time as returned by localtime()  
is used.  

clock(...)  
clock() -> floating point number  

Return the CPU time or real time since the start of the process or since  
the first call to clock(). This has as much precision as the system  
records.  

ctime(...)  
ctime(seconds) -> string  

Convert a time in seconds since the Epoch to a string in local time.  
This is equivalent to asctime(localtime(seconds)). When the time tuple is  
not present, current time as returned by localtime() is used.  

get_clock_info(...)  
get_clock_info(name: str) -> dict  

Get information of the specified clock.  

gmtime(...)  
gmtime([seconds]) -> (tm_year, tm_mon, tm_mday, tm_hour, tm_min,  
tm_sec, tm_wday, tm_yday, tm_isdst)  

Convert seconds since the Epoch to a time tuple expressing UTC (a.k.a.  
GMT). When 'seconds' is not passed in, convert the current time instead.  

If the platform supports the tm_gmtoff and tm_zone, they are available as  
attributes only.  

localtime(...)  
localtime([seconds]) -> (tm_year,tm_mon,tm_mday,tm_hour,tm_min,  
tm_sec,tm_wday,tm_yday,tm_isdst)  

Convert seconds since the Epoch to a time tuple expressing local time.  
When 'seconds' is not passed in, convert the current time instead.  

mktime(...)  
mktime(tuple) -> floating point number  

Convert a time tuple in local time to seconds since the Epoch.  
Note that mktime(gmtime(0)) will not generally return zero for most  
time zones; instead the returned value will either be equal to that  
of the timezone or altzone attributes on the time module.  

monotonic(...)  
monotonic() -> float  

Monotonic clock, cannot go backward.  

monotonic_ns(...)  
monotonic_ns() -> int  

Monotonic clock, cannot go backward, as nanoseconds.  

perf_counter(...)  
perf_counter() -> float  

Performance counter for benchmarking.  

perf_counter_ns(...)  
perf_counter_ns() -> int  

Performance counter for benchmarking as nanoseconds.  

process_time(...)  
process_time() -> float  

Process time for profiling: sum of the kernel and user-space CPU time.  

process_time_ns(...)  
process_time() -> int  

Process time for profiling as nanoseconds:  
sum of the kernel and user-space CPU time.  

sleep(...)  
sleep(seconds)  

Delay execution for a given number of seconds. The argument may be  
a floating point number for subsecond precision.  

strftime(...)  
strftime(format[, tuple]) -> string  

Convert a time tuple to a string according to a format specification.  
See the library reference manual for formatting codes. When the time tuple  
is not present, current time as returned by localtime() is used.  

Commonly used format codes:  

%Y Year with century as a decimal number.  
%m Month as a decimal number [01,12].  
%d Day of the month as a decimal number [01,31].  
%H Hour (24-hour clock) as a decimal number [00,23].  
%M Minute as a decimal number [00,59].  
%S Second as a decimal number [00,61].  
%z Time zone offset from UTC.  
%a Locale's abbreviated weekday name.  
%A Locale's full weekday name.  
%b Locale's abbreviated month name.  
%B Locale's full month name.  
%c Locale's appropriate date and time representation.  
%I Hour (12-hour clock) as a decimal number [01,12].  
%p Locale's equivalent of either AM or PM.  

Other codes may be available on your platform. See documentation for  
the C library strftime function.  

strptime(...)  
strptime(string, format) -> struct_time  

Parse a string to a time tuple according to a format specification.  
See the library reference manual for formatting codes (same as  
strftime()).  

Commonly used format codes:  

%Y Year with century as a decimal number.  
%m Month as a decimal number [01,12].  
%d Day of the month as a decimal number [01,31].  
%H Hour (24-hour clock) as a decimal number [00,23].  
%M Minute as a decimal number [00,59].  
%S Second as a decimal number [00,61].  
%z Time zone offset from UTC.  
%a Locale's abbreviated weekday name.  
%A Locale's full weekday name.  
%b Locale's abbreviated month name.  
%B Locale's full month name.  
%c Locale's appropriate date and time representation.  
%I Hour (12-hour clock) as a decimal number [01,12].  
%p Locale's equivalent of either AM or PM.  

Other codes may be available on your platform. See documentation for  
the C library strftime function.  

thread_time(...)  
thread_time() -> float  

Thread time for profiling: sum of the kernel and user-space CPU time.  

thread_time_ns(...)  
thread_time() -> int  

Thread time for profiling as nanoseconds:  
sum of the kernel and user-space CPU time.  

time(...)  
time() -> floating point number  

Return the current time in seconds since the Epoch.  
Fractions of a second may be present if the system clock provides them.  

time_ns(...)  
time_ns() -> int  

Return the current time in nanoseconds since the Epoch.  

DATA  
altzone = -7200  
daylight = 1  
timezone = -3600  
tzname = ('West-Europa (standaardtijd)', 'West-Europa (zomertijd)')  

FILE  
(built-in)  

Help on package tqdm:  

NAME  
tqdm  

PACKAGE CONTENTS  
__main__  
_main  
_monitor  
_tqdm  
_tqdm_gui  
_tqdm_notebook  
_tqdm_pandas  
_utils  
_version  
auto (package)  
autonotebook (package)  

CLASSES  
builtins.KeyError(builtins.LookupError)  
tqdm._tqdm.TqdmKeyError  
builtins.RuntimeWarning(builtins.Warning)  
tqdm._monitor.TqdmSynchronisationWarning  
builtins.TypeError(builtins.Exception)  
tqdm._tqdm.TqdmTypeError  
builtins.Warning(builtins.Exception)  
tqdm._tqdm.TqdmWarning  
tqdm._tqdm.TqdmDeprecationWarning(tqdm._tqdm.TqdmWarning, builtins.DeprecationWarning)  
tqdm._tqdm.TqdmExperimentalWarning(tqdm._tqdm.TqdmWarning, builtins.FutureWarning)  
tqdm._tqdm.TqdmMonitorWarning(tqdm._tqdm.TqdmWarning, builtins.RuntimeWarning)  
threading.Thread(builtins.object)  
tqdm._monitor.TMonitor  
tqdm._utils.Comparable(builtins.object)  
tqdm._tqdm.tqdm  
tqdm._tqdm_gui.tqdm_gui  

class TMonitor(threading.Thread)  
| TMonitor(tqdm_cls, sleep_interval)  
|  
| Monitoring thread for tqdm bars.  
| Monitors if tqdm bars are taking too much time to display  
| and readjusts miniters automatically if necessary.  
|  
| Parameters  
| ----------  
| tqdm_cls : class  
| tqdm class to use (can be core tqdm or a submodule).  
| sleep_interval : fload  
| Time to sleep between monitoring checks.  
|  
| Method resolution order:  
| TMonitor  
| threading.Thread  
| builtins.object  
|  
| Methods defined here:  
|  
| __init__(self, tqdm_cls, sleep_interval)  
| This constructor should always be called with keyword arguments. Arguments are:  
|  
| *group* should be None; reserved for future extension when a ThreadGroup  
| class is implemented.  
|  
| *target* is the callable object to be invoked by the run()  
| method. Defaults to None, meaning nothing is called.  
|  
| *name* is the thread name. By default, a unique name is constructed of  
| the form "Thread-N" where N is a small decimal number.  
|  
| *args* is the argument tuple for the target invocation. Defaults to ().  
|  
| *kwargs* is a dictionary of keyword arguments for the target  
| invocation. Defaults to {}.  
|  
| If a subclass overrides the constructor, it must make sure to invoke  
| the base class constructor (Thread.__init__()) before doing anything  
| else to the thread.  
|  
| exit(self)  
|  
| get_instances(self)  
|  
| report(self)  
|  
| run(self)  
| Method representing the thread's activity.  
|  
| You may override this method in a subclass. The standard run() method  
| invokes the callable object passed to the object's constructor as the  
| target argument, if any, with sequential and keyword arguments taken  
| from the args and kwargs arguments, respectively.  
|  
|

* * *

| Methods inherited from threading.Thread:  
|  
| __repr__(self)  
| Return repr(self).  
|  
| getName(self)  
|  
| isAlive = is_alive(self)  
| Return whether the thread is alive.  
|  
| This method returns True just before the run() method starts until just  
| after the run() method terminates. The module function enumerate()  
| returns a list of all alive threads.  
|  
| isDaemon(self)  
|  
| is_alive(self)  
| Return whether the thread is alive.  
|  
| This method returns True just before the run() method starts until just  
| after the run() method terminates. The module function enumerate()  
| returns a list of all alive threads.  
|  
| join(self, timeout=None)  
| Wait until the thread terminates.  
|  
| This blocks the calling thread until the thread whose join() method is  
| called terminates -- either normally or through an unhandled exception  
| or until the optional timeout occurs.  
|  
| When the timeout argument is present and not None, it should be a  
| floating point number specifying a timeout for the operation in seconds  
| (or fractions thereof). As join() always returns None, you must call  
| isAlive() after join() to decide whether a timeout happened -- if the  
| thread is still alive, the join() call timed out.  
|  
| When the timeout argument is not present or None, the operation will  
| block until the thread terminates.  
|  
| A thread can be join()ed many times.  
|  
| join() raises a RuntimeError if an attempt is made to join the current  
| thread as that would cause a deadlock. It is also an error to join() a  
| thread before it has been started and attempts to do so raises the same  
| exception.  
|  
| setDaemon(self, daemonic)  
|  
| setName(self, name)  
|  
| start(self)  
| Start the thread's activity.  
|  
| It must be called at most once per thread object. It arranges for the  
| object's run() method to be invoked in a separate thread of control.  
|  
| This method will raise a RuntimeError if called more than once on the  
| same thread object.  
|  
|

* * *

| Data descriptors inherited from threading.Thread:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
| daemon  
| A boolean value indicating whether this thread is a daemon thread.  
|  
| This must be set before start() is called, otherwise RuntimeError is  
| raised. Its initial value is inherited from the creating thread; the  
| main thread is not a daemon thread and therefore all threads created in  
| the main thread default to daemon = False.  
|  
| The entire Python program exits when no alive non-daemon threads are  
| left.  
|  
| ident  
| Thread identifier of this thread or None if it has not been started.  
|  
| This is a nonzero integer. See the get_ident() function. Thread  
| identifiers may be recycled when a thread exits and another thread is  
| created. The identifier is available even after the thread has exited.  
|  
| name  
| A string used for identification purposes only.  
|  
| It has no semantics. Multiple threads may be given the same name. The  
| initial name is set by the constructor.  

class TqdmDeprecationWarning(TqdmWarning, builtins.DeprecationWarning)  
| TqdmDeprecationWarning(msg, fp_write=None, *a, **k)  
|  
| base class for all tqdm warnings.  
|  
| Used for non-external-code-breaking errors, such as garbled printing.  
|  
| Method resolution order:  
| TqdmDeprecationWarning  
| TqdmWarning  
| builtins.DeprecationWarning  
| builtins.Warning  
| builtins.Exception  
| builtins.BaseException  
| builtins.object  
|  
| Methods inherited from TqdmWarning:  
|  
| __init__(self, msg, fp_write=None, *a, **k)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
|

* * *

| Data descriptors inherited from TqdmWarning:  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
|

* * *

| Static methods inherited from builtins.DeprecationWarning:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from builtins.BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| __str__(self, /)  
| Return str(self).  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from builtins.BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class TqdmExperimentalWarning(TqdmWarning, builtins.FutureWarning)  
| TqdmExperimentalWarning(msg, fp_write=None, *a, **k)  
|  
| beta feature, unstable API and behaviour  
|  
| Method resolution order:  
| TqdmExperimentalWarning  
| TqdmWarning  
| builtins.FutureWarning  
| builtins.Warning  
| builtins.Exception  
| builtins.BaseException  
| builtins.object  
|  
| Methods inherited from TqdmWarning:  
|  
| __init__(self, msg, fp_write=None, *a, **k)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
|

* * *

| Data descriptors inherited from TqdmWarning:  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
|

* * *

| Static methods inherited from builtins.FutureWarning:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from builtins.BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| __str__(self, /)  
| Return str(self).  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from builtins.BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class TqdmKeyError(builtins.KeyError)  
| Mapping key not found.  
|  
| Method resolution order:  
| TqdmKeyError  
| builtins.KeyError  
| builtins.LookupError  
| builtins.Exception  
| builtins.BaseException  
| builtins.object  
|  
| Data descriptors defined here:  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
|

* * *

| Methods inherited from builtins.KeyError:  
|  
| __init__(self, /, *args, **kwargs)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
| __str__(self, /)  
| Return str(self).  
|  
|

* * *

| Static methods inherited from builtins.LookupError:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from builtins.BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from builtins.BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class TqdmMonitorWarning(TqdmWarning, builtins.RuntimeWarning)  
| TqdmMonitorWarning(msg, fp_write=None, *a, **k)  
|  
| tqdm monitor errors which do not affect external functionality  
|  
| Method resolution order:  
| TqdmMonitorWarning  
| TqdmWarning  
| builtins.RuntimeWarning  
| builtins.Warning  
| builtins.Exception  
| builtins.BaseException  
| builtins.object  
|  
| Methods inherited from TqdmWarning:  
|  
| __init__(self, msg, fp_write=None, *a, **k)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
|

* * *

| Data descriptors inherited from TqdmWarning:  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
|

* * *

| Static methods inherited from builtins.RuntimeWarning:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from builtins.BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| __str__(self, /)  
| Return str(self).  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from builtins.BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class TqdmSynchronisationWarning(builtins.RuntimeWarning)  
| tqdm multi-thread/-process errors which may cause incorrect nesting  
| but otherwise no adverse effects  
|  
| Method resolution order:  
| TqdmSynchronisationWarning  
| builtins.RuntimeWarning  
| builtins.Warning  
| builtins.Exception  
| builtins.BaseException  
| builtins.object  
|  
| Data descriptors defined here:  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
|

* * *

| Methods inherited from builtins.RuntimeWarning:  
|  
| __init__(self, /, *args, **kwargs)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
|

* * *

| Static methods inherited from builtins.RuntimeWarning:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from builtins.BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| __str__(self, /)  
| Return str(self).  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from builtins.BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class TqdmTypeError(builtins.TypeError)  
| Inappropriate argument type.  
|  
| Method resolution order:  
| TqdmTypeError  
| builtins.TypeError  
| builtins.Exception  
| builtins.BaseException  
| builtins.object  
|  
| Data descriptors defined here:  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
|

* * *

| Methods inherited from builtins.TypeError:  
|  
| __init__(self, /, *args, **kwargs)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
|

* * *

| Static methods inherited from builtins.TypeError:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from builtins.BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| __str__(self, /)  
| Return str(self).  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from builtins.BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class TqdmWarning(builtins.Warning)  
| TqdmWarning(msg, fp_write=None, *a, **k)  
|  
| base class for all tqdm warnings.  
|  
| Used for non-external-code-breaking errors, such as garbled printing.  
|  
| Method resolution order:  
| TqdmWarning  
| builtins.Warning  
| builtins.Exception  
| builtins.BaseException  
| builtins.object  
|  
| Methods defined here:  
|  
| __init__(self, msg, fp_write=None, *a, **k)  
| Initialize self. See help(type(self)) for accurate signature.  
|  
|

* * *

| Data descriptors defined here:  
|  
| __weakref__  
| list of weak references to the object (if defined)  
|  
|

* * *

| Static methods inherited from builtins.Warning:  
|  
| __new__(*args, **kwargs) from builtins.type  
| Create and return a new object. See help(type) for accurate signature.  
|  
|

* * *

| Methods inherited from builtins.BaseException:  
|  
| __delattr__(self, name, /)  
| Implement delattr(self, name).  
|  
| __getattribute__(self, name, /)  
| Return getattr(self, name).  
|  
| __reduce__(...)  
| Helper for pickle.  
|  
| __repr__(self, /)  
| Return repr(self).  
|  
| __setattr__(self, name, value, /)  
| Implement setattr(self, name, value).  
|  
| __setstate__(...)  
|  
| __str__(self, /)  
| Return str(self).  
|  
| with_traceback(...)  
| Exception.with_traceback(tb) --  
| set self.__traceback__ to tb and return self.  
|  
|

* * *

| Data descriptors inherited from builtins.BaseException:  
|  
| __cause__  
| exception cause  
|  
| __context__  
| exception context  
|  
| __dict__  
|  
| __suppress_context__  
|  
| __traceback__  
|  
| args  

class tqdm(tqdm._utils.Comparable)  
| tqdm(*args, **kwargs)  
|  
| Decorate an iterable object, returning an iterator which acts exactly  
| like the original iterable, but prints a dynamically updating  
| progressbar every time a value is requested.  
|  
| Method resolution order:  
| tqdm  
| tqdm._utils.Comparable  
| builtins.object  
|  
| Methods defined here:  
|  
| __del__(self)  
|  
| __enter__(self)  
|  
| __exit__(self, *exc)  
|  
| __hash__(self)  
| Return hash(self).  
|  
| __init__(self, iterable=None, desc=None, total=None, leave=True, file=None, ncols=None, mininterval=0.1, maxinterval=10.0, miniters=None, ascii=None, disable=False, unit='it', unit_scale=False, dynamic_ncols=False, smoothing=0.3, bar_format=None, initial=0, position=None, postfix=None, unit_divisor=1000, gui=False, **kwargs)  
| Parameters  
| ----------  
| iterable : iterable, optional  
| Iterable to decorate with a progressbar.  
| Leave blank to manually manage the updates.  
| desc : str, optional  
| Prefix for the progressbar.  
| total : int, optional  
| The number of expected iterations. If unspecified,  
| len(iterable) is used if possible. If float("inf") or as a last  
| resort, only basic progress statistics are displayed  
| (no ETA, no progressbar).  
| If `gui` is True and this parameter needs subsequent updating,  
| specify an initial arbitrary large positive integer,  
| e.g. int(9e9).  
| leave : bool, optional  
| If [default: True], keeps all traces of the progressbar  
| upon termination of iteration.  
| file : `io.TextIOWrapper` or `io.StringIO`, optional  
| Specifies where to output the progress messages  
| (default: sys.stderr). Uses `file.write(str)` and `file.flush()`  
| methods.  
| ncols : int, optional  
| The width of the entire output message. If specified,  
| dynamically resizes the progressbar to stay within this bound.  
| If unspecified, attempts to use environment width. The  
| fallback is a meter width of 10 and no limit for the counter and  
| statistics. If 0, will not print any meter (only stats).  
| mininterval : float, optional  
| Minimum progress display update interval [default: 0.1] seconds.  
| maxinterval : float, optional  
| Maximum progress display update interval [default: 10] seconds.  
| Automatically adjusts `miniters` to correspond to `mininterval`  
| after long display update lag. Only works if `dynamic_miniters`  
| or monitor thread is enabled.  
| miniters : int, optional  
| Minimum progress display update interval, in iterations.  
| If 0 and `dynamic_miniters`, will automatically adjust to equal  
| `mininterval` (more CPU efficient, good for tight loops).  
| If > 0, will skip display of specified number of iterations.  
| Tweak this and `mininterval` to get very efficient loops.  
| If your progress is erratic with both fast and slow iterations  
| (network, skipping items, etc) you should set miniters=1.  
| ascii : bool, optional  
| If unspecified or False, use unicode (smooth blocks) to fill  
| the meter. The fallback is to use ASCII characters `1-9 #`.  
| disable : bool, optional  
| Whether to disable the entire progressbar wrapper  
| [default: False]. If set to None, disable on non-TTY.  
| unit : str, optional  
| String that will be used to define the unit of each iteration  
| [default: it].  
| unit_scale : bool or int or float, optional  
| If 1 or True, the number of iterations will be reduced/scaled  
| automatically and a metric prefix following the  
| International System of Units standard will be added  
| (kilo, mega, etc.) [default: False]. If any other non-zero  
| number, will scale `total` and `n`.  
| dynamic_ncols : bool, optional  
| If set, constantly alters `ncols` to the environment (allowing  
| for window resizes) [default: False].  
| smoothing : float, optional  
| Exponential moving average smoothing factor for speed estimates  
| (ignored in GUI mode). Ranges from 0 (average speed) to 1  
| (current/instantaneous speed) [default: 0.3].  
| bar_format : str, optional  
| Specify a custom bar string formatting. May impact performance.  
| [default: '{l_bar}{bar}{r_bar}'], where  
| l_bar='{desc}: {percentage:3.0f}%|' and  
| r_bar='| {n_fmt}/{total_fmt} [{elapsed}<{remaining}, '  
| '{rate_fmt}{postfix}]'  
| Possible vars: l_bar, bar, r_bar, n, n_fmt, total, total_fmt,  
| percentage, rate, rate_fmt, rate_noinv, rate_noinv_fmt,  
| rate_inv, rate_inv_fmt, elapsed, remaining, desc, postfix.  
| Note that a trailing ": " is automatically removed after {desc}  
| if the latter is empty.  
| initial : int, optional  
| The initial counter value. Useful when restarting a progress  
| bar [default: 0].  
| position : int, optional  
| Specify the line offset to print this bar (starting from 0)  
| Automatic if unspecified.  
| Useful to manage multiple bars at once (eg, from threads).  
| postfix : dict or *, optional  
| Specify additional stats to display at the end of the bar.  
| Calls `set_postfix(**postfix)` if possible (dict).  
| unit_divisor : float, optional  
| [default: 1000], ignored unless `unit_scale` is True.  
| gui : bool, optional  
| WARNING: internal parameter - do not use.  
| Use tqdm_gui(...) instead. If set, will attempt to use  
| matplotlib animations for a graphical output [default: False].  
|  
| Returns  
| -------  
| out : decorated iterator.  
|  
| __iter__(self)  
| Backward-compatibility to use: for x in tqdm(iterable)  
|  
| __len__(self)  
|  
| __repr__(self)  
| Return repr(self).  
|  
| clear(self, nolock=False)  
| Clear current bar display  
|  
| close(self)  
| Cleanup and (if leave=False) close the progressbar.  
|  
| display(self, msg=None, pos=None)  
| Use `self.sp` and to display `msg` in the specified `pos`.  
|  
| Parameters  
| ----------  
| msg : what to display (default: repr(self))  
| pos : position to display in. (default: abs(self.pos))  
|  
| moveto(self, n)  
|  
| refresh(self, nolock=False)  
| Force refresh the display of this bar  
|  
| set_description(self, desc=None, refresh=True)  
| Set/modify description of the progress bar.  
|  
| Parameters  
| ----------  
| desc : str, optional  
| refresh : bool, optional  
| Forces refresh [default: True].  
|  
| set_description_str(self, desc=None, refresh=True)  
| Set/modify description without ': ' appended.  
|  
| set_postfix(self, ordered_dict=None, refresh=True, **kwargs)  
| Set/modify postfix (additional stats)  
| with automatic formatting based on datatype.  
|  
| Parameters  
| ----------  
| ordered_dict : dict or OrderedDict, optional  
| refresh : bool, optional  
| Forces refresh [default: True].  
| kwargs : dict, optional  
|  
| set_postfix_str(self, s='', refresh=True)  
| Postfix without dictionary expansion, similar to prefix handling.  
|  
| unpause(self)  
| Restart tqdm timer from last print time.  
|  
| update(self, n=1)  
| Manually update the progress bar, useful for streams  
| such as reading files.  
| E.g.:  
| >>> t = tqdm(total=filesize) # Initialise  
| >>> for current_buffer in stream:  
| ... ...  
| ... t.update(len(current_buffer))  
| >>> t.close()  
| The last line is highly recommended, but possibly not necessary if  
| `t.update()` will be called in such a way that `filesize` will be  
| exactly reached and printed.  
|  
| Parameters  
| ----------  
| n : int, optional  
| Increment to add to the internal counter of iterations  
| [default: 1].  
|  
|

* * *

| Class methods defined here:  
|  
| external_write_mode(file=None, nolock=False) from builtins.type  
| Disable tqdm within context and refresh tqdm when exits.  
| Useful when writing to standard output stream  
|  
| get_lock() from builtins.type  
| Get the global lock. Construct it if it does not exist.  
|  
| pandas(*targs, **tkwargs) from builtins.type  
| Registers the given `tqdm` class with  
| pandas.core.  
| ( frame.DataFrame  
| | series.Series  
| | groupby.DataFrameGroupBy  
| | groupby.SeriesGroupBy  
| ).progress_apply  
|  
| A new instance will be create every time `progress_apply` is called,  
| and each instance will automatically close() upon completion.  
|  
| Parameters  
| ----------  
| targs, tkwargs : arguments for the tqdm instance  
|  
| Examples  
| --------  
| >>> import pandas as pd  
| >>> import numpy as np  
| >>> from tqdm import tqdm, tqdm_gui  
| >>>  
| >>> df = pd.DataFrame(np.random.randint(0, 100, (100000, 6)))  
| >>> tqdm.pandas(ncols=50) # can use tqdm_gui, optional kwargs, etc  
| >>> # Now you can use `progress_apply` instead of `apply`  
| >>> df.groupby(0).progress_apply(lambda x: x**2)  
|  
| References  
| ----------  
| https://stackoverflow.com/questions/18603270/  
| progress-indicator-during-pandas-operations-python  
|  
| set_lock(lock) from builtins.type  
| Set the global lock.  
|  
| write(s, file=None, end='\n', nolock=False) from builtins.type  
| Print a message via tqdm (without overlap with bars)  
|  
|

* * *

| Static methods defined here:  
|  
| __new__(cls, *args, **kwargs)  
| Create and return a new object. See help(type) for accurate signature.  
|  
| ema(x, mu=None, alpha=0.3)  
| Exponential moving average: smoothing to give progressively lower  
| weights to older values.  
|  
| Parameters  
| ----------  
| x : float  
| New value to include in EMA.  
| mu : float, optional  
| Previous EMA value.  
| alpha : float, optional  
| Smoothing factor in range [0, 1], [default: 0.3].  
| Increase to give more weight to recent values.  
| Ranges from 0 (yields mu) to 1 (yields x).  
|  
| format_interval(t)  
| Formats a number of seconds as a clock time, [H:]MM:SS  
|  
| Parameters  
| ----------  
| t : int  
| Number of seconds.  
|  
| Returns  
| -------  
| out : str  
| [H:]MM:SS  
|  
| format_meter(n, total, elapsed, ncols=None, prefix='', ascii=False, unit='it', unit_scale=False, rate=None, bar_format=None, postfix=None, unit_divisor=1000, **extra_kwargs)  
| Return a string-based progress bar given some parameters  
|  
| Parameters  
| ----------  
| n : int  
| Number of finished iterations.  
| total : int  
| The expected total number of iterations. If meaningless (), only  
| basic progress statistics are displayed (no ETA).  
| elapsed : float  
| Number of seconds passed since start.  
| ncols : int, optional  
| The width of the entire output message. If specified,  
| dynamically resizes the progress meter to stay within this bound  
| [default: None]. The fallback meter width is 10 for the progress  
| bar + no limit for the iterations counter and statistics. If 0,  
| will not print any meter (only stats).  
| prefix : str, optional  
| Prefix message (included in total width) [default: ''].  
| Use as {desc} in bar_format string.  
| ascii : bool, optional  
| If not set, use unicode (smooth blocks) to fill the meter  
| [default: False]. The fallback is to use ASCII characters  
| (1-9 #).  
| unit : str, optional  
| The iteration unit [default: 'it'].  
| unit_scale : bool or int or float, optional  
| If 1 or True, the number of iterations will be printed with an  
| appropriate SI metric prefix (k = 10^3, M = 10^6, etc.)  
| [default: False]. If any other non-zero number, will scale  
| `total` and `n`.  
| rate : float, optional  
| Manual override for iteration rate.  
| If [default: None], uses n/elapsed.  
| bar_format : str, optional  
| Specify a custom bar string formatting. May impact performance.  
| [default: '{l_bar}{bar}{r_bar}'], where  
| l_bar='{desc}: {percentage:3.0f}%|' and  
| r_bar='| {n_fmt}/{total_fmt} [{elapsed}<{remaining}, '  
| '{rate_fmt}{postfix}]'  
| Possible vars: l_bar, bar, r_bar, n, n_fmt, total, total_fmt,  
| percentage, rate, rate_fmt, rate_noinv, rate_noinv_fmt,  
| rate_inv, rate_inv_fmt, elapsed, remaining, desc, postfix.  
| Note that a trailing ": " is automatically removed after {desc}  
| if the latter is empty.  
| postfix : *, optional  
| Similar to `prefix`, but placed at the end  
| (e.g. for additional stats).  
| Note: postfix is usually a string (not a dict) for this method,  
| and will if possible be set to postfix = ', ' + postfix.  
| However other types are supported (#382).  
| unit_divisor : float, optional  
| [default: 1000], ignored unless `unit_scale` is True.  
|  
| Returns  
| -------  
| out : Formatted meter and stats, ready to display.  
|  
| format_num(n)  
| Intelligent scientific notation (.3g).  
|  
| Parameters  
| ----------  
| n : int or float or Numeric  
| A Number.  
|  
| Returns  
| -------  
| out : str  
| Formatted number.  
|  
| format_sizeof(num, suffix='', divisor=1000)  
| Formats a number (greater than unity) with SI Order of Magnitude  
| prefixes.  
|  
| Parameters  
| ----------  
| num : float  
| Number ( >= 1) to format.  
| suffix : str, optional  
| Post-postfix [default: ''].  
| divisor : float, optionl  
| Divisor between prefixes [default: 1000].  
|  
| Returns  
| -------  
| out : str  
| Number with Order of Magnitude SI unit postfix.  
|  
| status_printer(file)  
| Manage the printing and in-place updating of a line of characters.  
| Note that if the string is longer than a line, then in-place  
| updating may not work (it will print a new line at each refresh).  
|  
|

* * *

| Data descriptors defined here:  
|  
| format_dict  
| Public API for read-only member access  
|  
|

* * *

| Data and other attributes defined here:  
|  
| monitor = None  
|  
| monitor_interval = 10  
|  
|

* * *

| Methods inherited from tqdm._utils.Comparable:  
|  
| __eq__(self, other)  
| Return self==value.  
|  
| __ge__(self, other)  
| Return self>=value.  
|  
| __gt__(self, other)  
| Return self>value.  
|  
| __le__(self, other)  
| Return self<=value.  
|  
| __lt__(self, other)  
| Return self <value. <br="">|  
| __ne__(self, other)  
| Return self!=value.  
|  
|

* * *

| Data descriptors inherited from tqdm._utils.Comparable:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  

class tqdm_gui(tqdm._tqdm.tqdm)  
| tqdm_gui(*args, **kwargs)  
|  
| Experimental GUI version of tqdm!  
|  
| Method resolution order:  
| tqdm_gui  
| tqdm._tqdm.tqdm  
| tqdm._utils.Comparable  
| builtins.object  
|  
| Methods defined here:  
|  
| __init__(self, *args, **kwargs)  
| Parameters  
| ----------  
| iterable : iterable, optional  
| Iterable to decorate with a progressbar.  
| Leave blank to manually manage the updates.  
| desc : str, optional  
| Prefix for the progressbar.  
| total : int, optional  
| The number of expected iterations. If unspecified,  
| len(iterable) is used if possible. If float("inf") or as a last  
| resort, only basic progress statistics are displayed  
| (no ETA, no progressbar).  
| If `gui` is True and this parameter needs subsequent updating,  
| specify an initial arbitrary large positive integer,  
| e.g. int(9e9).  
| leave : bool, optional  
| If [default: True], keeps all traces of the progressbar  
| upon termination of iteration.  
| file : `io.TextIOWrapper` or `io.StringIO`, optional  
| Specifies where to output the progress messages  
| (default: sys.stderr). Uses `file.write(str)` and `file.flush()`  
| methods.  
| ncols : int, optional  
| The width of the entire output message. If specified,  
| dynamically resizes the progressbar to stay within this bound.  
| If unspecified, attempts to use environment width. The  
| fallback is a meter width of 10 and no limit for the counter and  
| statistics. If 0, will not print any meter (only stats).  
| mininterval : float, optional  
| Minimum progress display update interval [default: 0.1] seconds.  
| maxinterval : float, optional  
| Maximum progress display update interval [default: 10] seconds.  
| Automatically adjusts `miniters` to correspond to `mininterval`  
| after long display update lag. Only works if `dynamic_miniters`  
| or monitor thread is enabled.  
| miniters : int, optional  
| Minimum progress display update interval, in iterations.  
| If 0 and `dynamic_miniters`, will automatically adjust to equal  
| `mininterval` (more CPU efficient, good for tight loops).  
| If > 0, will skip display of specified number of iterations.  
| Tweak this and `mininterval` to get very efficient loops.  
| If your progress is erratic with both fast and slow iterations  
| (network, skipping items, etc) you should set miniters=1.  
| ascii : bool, optional  
| If unspecified or False, use unicode (smooth blocks) to fill  
| the meter. The fallback is to use ASCII characters `1-9 #`.  
| disable : bool, optional  
| Whether to disable the entire progressbar wrapper  
| [default: False]. If set to None, disable on non-TTY.  
| unit : str, optional  
| String that will be used to define the unit of each iteration  
| [default: it].  
| unit_scale : bool or int or float, optional  
| If 1 or True, the number of iterations will be reduced/scaled  
| automatically and a metric prefix following the  
| International System of Units standard will be added  
| (kilo, mega, etc.) [default: False]. If any other non-zero  
| number, will scale `total` and `n`.  
| dynamic_ncols : bool, optional  
| If set, constantly alters `ncols` to the environment (allowing  
| for window resizes) [default: False].  
| smoothing : float, optional  
| Exponential moving average smoothing factor for speed estimates  
| (ignored in GUI mode). Ranges from 0 (average speed) to 1  
| (current/instantaneous speed) [default: 0.3].  
| bar_format : str, optional  
| Specify a custom bar string formatting. May impact performance.  
| [default: '{l_bar}{bar}{r_bar}'], where  
| l_bar='{desc}: {percentage:3.0f}%|' and  
| r_bar='| {n_fmt}/{total_fmt} [{elapsed}<{remaining}, '  
| '{rate_fmt}{postfix}]'  
| Possible vars: l_bar, bar, r_bar, n, n_fmt, total, total_fmt,  
| percentage, rate, rate_fmt, rate_noinv, rate_noinv_fmt,  
| rate_inv, rate_inv_fmt, elapsed, remaining, desc, postfix.  
| Note that a trailing ": " is automatically removed after {desc}  
| if the latter is empty.  
| initial : int, optional  
| The initial counter value. Useful when restarting a progress  
| bar [default: 0].  
| position : int, optional  
| Specify the line offset to print this bar (starting from 0)  
| Automatic if unspecified.  
| Useful to manage multiple bars at once (eg, from threads).  
| postfix : dict or *, optional  
| Specify additional stats to display at the end of the bar.  
| Calls `set_postfix(**postfix)` if possible (dict).  
| unit_divisor : float, optional  
| [default: 1000], ignored unless `unit_scale` is True.  
| gui : bool, optional  
| WARNING: internal parameter - do not use.  
| Use tqdm_gui(...) instead. If set, will attempt to use  
| matplotlib animations for a graphical output [default: False].  
|  
| Returns  
| -------  
| out : decorated iterator.  
|  
| __iter__(self)  
| Backward-compatibility to use: for x in tqdm(iterable)  
|  
| close(self)  
| Cleanup and (if leave=False) close the progressbar.  
|  
| update(self, n=1)  
| Manually update the progress bar, useful for streams  
| such as reading files.  
| E.g.:  
| >>> t = tqdm(total=filesize) # Initialise  
| >>> for current_buffer in stream:  
| ... ...  
| ... t.update(len(current_buffer))  
| >>> t.close()  
| The last line is highly recommended, but possibly not necessary if  
| `t.update()` will be called in such a way that `filesize` will be  
| exactly reached and printed.  
|  
| Parameters  
| ----------  
| n : int, optional  
| Increment to add to the internal counter of iterations  
| [default: 1].  
|  
|

* * *

| Methods inherited from tqdm._tqdm.tqdm:  
|  
| __del__(self)  
|  
| __enter__(self)  
|  
| __exit__(self, *exc)  
|  
| __hash__(self)  
| Return hash(self).  
|  
| __len__(self)  
|  
| __repr__(self)  
| Return repr(self).  
|  
| clear(self, nolock=False)  
| Clear current bar display  
|  
| display(self, msg=None, pos=None)  
| Use `self.sp` and to display `msg` in the specified `pos`.  
|  
| Parameters  
| ----------  
| msg : what to display (default: repr(self))  
| pos : position to display in. (default: abs(self.pos))  
|  
| moveto(self, n)  
|  
| refresh(self, nolock=False)  
| Force refresh the display of this bar  
|  
| set_description(self, desc=None, refresh=True)  
| Set/modify description of the progress bar.  
|  
| Parameters  
| ----------  
| desc : str, optional  
| refresh : bool, optional  
| Forces refresh [default: True].  
|  
| set_description_str(self, desc=None, refresh=True)  
| Set/modify description without ': ' appended.  
|  
| set_postfix(self, ordered_dict=None, refresh=True, **kwargs)  
| Set/modify postfix (additional stats)  
| with automatic formatting based on datatype.  
|  
| Parameters  
| ----------  
| ordered_dict : dict or OrderedDict, optional  
| refresh : bool, optional  
| Forces refresh [default: True].  
| kwargs : dict, optional  
|  
| set_postfix_str(self, s='', refresh=True)  
| Postfix without dictionary expansion, similar to prefix handling.  
|  
| unpause(self)  
| Restart tqdm timer from last print time.  
|  
|

* * *

| Class methods inherited from tqdm._tqdm.tqdm:  
|  
| external_write_mode(file=None, nolock=False) from builtins.type  
| Disable tqdm within context and refresh tqdm when exits.  
| Useful when writing to standard output stream  
|  
| get_lock() from builtins.type  
| Get the global lock. Construct it if it does not exist.  
|  
| pandas(*targs, **tkwargs) from builtins.type  
| Registers the given `tqdm` class with  
| pandas.core.  
| ( frame.DataFrame  
| | series.Series  
| | groupby.DataFrameGroupBy  
| | groupby.SeriesGroupBy  
| ).progress_apply  
|  
| A new instance will be create every time `progress_apply` is called,  
| and each instance will automatically close() upon completion.  
|  
| Parameters  
| ----------  
| targs, tkwargs : arguments for the tqdm instance  
|  
| Examples  
| --------  
| >>> import pandas as pd  
| >>> import numpy as np  
| >>> from tqdm import tqdm, tqdm_gui  
| >>>  
| >>> df = pd.DataFrame(np.random.randint(0, 100, (100000, 6)))  
| >>> tqdm.pandas(ncols=50) # can use tqdm_gui, optional kwargs, etc  
| >>> # Now you can use `progress_apply` instead of `apply`  
| >>> df.groupby(0).progress_apply(lambda x: x**2)  
|  
| References  
| ----------  
| https://stackoverflow.com/questions/18603270/  
| progress-indicator-during-pandas-operations-python  
|  
| set_lock(lock) from builtins.type  
| Set the global lock.  
|  
| write(s, file=None, end='\n', nolock=False) from builtins.type  
| Print a message via tqdm (without overlap with bars)  
|  
|

* * *

| Static methods inherited from tqdm._tqdm.tqdm:  
|  
| __new__(cls, *args, **kwargs)  
| Create and return a new object. See help(type) for accurate signature.  
|  
| ema(x, mu=None, alpha=0.3)  
| Exponential moving average: smoothing to give progressively lower  
| weights to older values.  
|  
| Parameters  
| ----------  
| x : float  
| New value to include in EMA.  
| mu : float, optional  
| Previous EMA value.  
| alpha : float, optional  
| Smoothing factor in range [0, 1], [default: 0.3].  
| Increase to give more weight to recent values.  
| Ranges from 0 (yields mu) to 1 (yields x).  
|  
| format_interval(t)  
| Formats a number of seconds as a clock time, [H:]MM:SS  
|  
| Parameters  
| ----------  
| t : int  
| Number of seconds.  
|  
| Returns  
| -------  
| out : str  
| [H:]MM:SS  
|  
| format_meter(n, total, elapsed, ncols=None, prefix='', ascii=False, unit='it', unit_scale=False, rate=None, bar_format=None, postfix=None, unit_divisor=1000, **extra_kwargs)  
| Return a string-based progress bar given some parameters  
|  
| Parameters  
| ----------  
| n : int  
| Number of finished iterations.  
| total : int  
| The expected total number of iterations. If meaningless (), only  
| basic progress statistics are displayed (no ETA).  
| elapsed : float  
| Number of seconds passed since start.  
| ncols : int, optional  
| The width of the entire output message. If specified,  
| dynamically resizes the progress meter to stay within this bound  
| [default: None]. The fallback meter width is 10 for the progress  
| bar + no limit for the iterations counter and statistics. If 0,  
| will not print any meter (only stats).  
| prefix : str, optional  
| Prefix message (included in total width) [default: ''].  
| Use as {desc} in bar_format string.  
| ascii : bool, optional  
| If not set, use unicode (smooth blocks) to fill the meter  
| [default: False]. The fallback is to use ASCII characters  
| (1-9 #).  
| unit : str, optional  
| The iteration unit [default: 'it'].  
| unit_scale : bool or int or float, optional  
| If 1 or True, the number of iterations will be printed with an  
| appropriate SI metric prefix (k = 10^3, M = 10^6, etc.)  
| [default: False]. If any other non-zero number, will scale  
| `total` and `n`.  
| rate : float, optional  
| Manual override for iteration rate.  
| If [default: None], uses n/elapsed.  
| bar_format : str, optional  
| Specify a custom bar string formatting. May impact performance.  
| [default: '{l_bar}{bar}{r_bar}'], where  
| l_bar='{desc}: {percentage:3.0f}%|' and  
| r_bar='| {n_fmt}/{total_fmt} [{elapsed}<{remaining}, '  
| '{rate_fmt}{postfix}]'  
| Possible vars: l_bar, bar, r_bar, n, n_fmt, total, total_fmt,  
| percentage, rate, rate_fmt, rate_noinv, rate_noinv_fmt,  
| rate_inv, rate_inv_fmt, elapsed, remaining, desc, postfix.  
| Note that a trailing ": " is automatically removed after {desc}  
| if the latter is empty.  
| postfix : *, optional  
| Similar to `prefix`, but placed at the end  
| (e.g. for additional stats).  
| Note: postfix is usually a string (not a dict) for this method,  
| and will if possible be set to postfix = ', ' + postfix.  
| However other types are supported (#382).  
| unit_divisor : float, optional  
| [default: 1000], ignored unless `unit_scale` is True.  
|  
| Returns  
| -------  
| out : Formatted meter and stats, ready to display.  
|  
| format_num(n)  
| Intelligent scientific notation (.3g).  
|  
| Parameters  
| ----------  
| n : int or float or Numeric  
| A Number.  
|  
| Returns  
| -------  
| out : str  
| Formatted number.  
|  
| format_sizeof(num, suffix='', divisor=1000)  
| Formats a number (greater than unity) with SI Order of Magnitude  
| prefixes.  
|  
| Parameters  
| ----------  
| num : float  
| Number ( >= 1) to format.  
| suffix : str, optional  
| Post-postfix [default: ''].  
| divisor : float, optionl  
| Divisor between prefixes [default: 1000].  
|  
| Returns  
| -------  
| out : str  
| Number with Order of Magnitude SI unit postfix.  
|  
| status_printer(file)  
| Manage the printing and in-place updating of a line of characters.  
| Note that if the string is longer than a line, then in-place  
| updating may not work (it will print a new line at each refresh).  
|  
|

* * *

| Data descriptors inherited from tqdm._tqdm.tqdm:  
|  
| format_dict  
| Public API for read-only member access  
|  
|

* * *

| Data and other attributes inherited from tqdm._tqdm.tqdm:  
|  
| monitor = None  
|  
| monitor_interval = 10  
|  
|

* * *

| Methods inherited from tqdm._utils.Comparable:  
|  
| __eq__(self, other)  
| Return self==value.  
|  
| __ge__(self, other)  
| Return self>=value.  
|  
| __gt__(self, other)  
| Return self>value.  
|  
| __le__(self, other)  
| Return self<=value.  
|  
| __lt__(self, other)  
| Return self <value. <br="">|  
| __ne__(self, other)  
| Return self!=value.  
|  
|

* * *

| Data descriptors inherited from tqdm._utils.Comparable:  
|  
| __dict__  
| dictionary for instance variables (if defined)  
|  
| __weakref__  
| list of weak references to the object (if defined)  

FUNCTIONS  
main(fp=<idlelib.run.pseudooutputfile object="" at="" 0x0000027a2adc4eb8="">, argv=None)  
Parameters (internal use only)  
---------  
fp : file-like object for tqdm  
argv : list (default: sys.argv[1:])  

tgrange(*args, **kwargs)  
A shortcut for tqdm_gui(xrange(*args), **kwargs).  
On Python3+ range is used instead of xrange.  

tnrange(*args, **kwargs)  
A shortcut for tqdm_notebook(xrange(*args), **kwargs).  
On Python3+ range is used instead of xrange.  

tqdm_notebook(*args, **kwargs)  
See tqdm._tqdm_notebook.tqdm_notebook for full documentation  

tqdm_pandas(tclass, *targs, **tkwargs)  
Registers the given `tqdm` instance with  
`pandas.core.groupby.DataFrameGroupBy.progress_apply`.  
It will even close() the `tqdm` instance upon completion.  

Parameters  
----------  
tclass : tqdm class you want to use (eg, tqdm, tqdm_notebook, etc)  
targs and tkwargs : arguments for the tqdm instance  

Examples  
--------  
>>> import pandas as pd  
>>> import numpy as np  
>>> from tqdm import tqdm, tqdm_pandas  
>>>  
>>> df = pd.DataFrame(np.random.randint(0, 100, (100000, 6)))  
>>> tqdm_pandas(tqdm, leave=True) # can use tqdm_gui, optional kwargs, etc  
>>> # Now you can use `progress_apply` instead of `apply`  
>>> df.groupby(0).progress_apply(lambda x: x**2)  

References  
----------  
https://stackoverflow.com/questions/18603270/  
progress-indicator-during-pandas-operations-python  

trange(*args, **kwargs)  
A shortcut for tqdm(xrange(*args), **kwargs).  
On Python3+ range is used instead of xrange.  

DATA  
__all__ = ['tqdm', 'tqdm_gui', 'trange', 'tgrange', 'tqdm_pandas', 'tq...  

VERSION  
4.30.0  

FILE  
c:\users\matthijs\appdata\local\programs\python\python37\lib\site-packages\tqdm\__init__.py  

No Python documentation found for 'tqdm_gui'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'tqdm_loop'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'unicode_literals'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'update_progress'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'web'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.  

No Python documentation found for 'web_open'.  
Use help() to get the interactive help utility.  
Use help(str) for help on the str class.</idlelib.run.pseudooutputfile></value.></value.></value.></idlelib.run.pseudooutputfile></idlelib.run.pseudoinputfile></idlelib.run.pseudooutputfile></function></class></class></class></class></built-in></lookup></http:></value.></value.></value.></value.></value.></value.></value.>******</div>
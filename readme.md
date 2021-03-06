# _GOLF_

_GOLF_ is a tiny CPU architecture designed to facilitate programming contests.
It provides a simple to understand controlled environment where performance can
be measured and tracked down to the individual cycle. It can provide an
unambiguous winning criterium for either the speed in cycles or size in
instructions of a solution.

The architecture was designed with simplicity as its main goal. It should be
very easy to start coding in _GOLF_ assembly by just reading the specification
and the examples.

For now there is only an assembler and a virtual machine in Python 3. In the
future a virtual machine in a faster language might be made. In a very distant
future we might see a LLVM backend for _GOLF_, allowing many languages to be ran
on _GOLF_.

`assemble.py` is the assembler, `golf.py` is the virtual machine. Both have a
built-in command line interface. Example usage:

    $ python3 assemble.py examples/helloworld.golf
    $ python3 golf.py examples/helloworld.bin
    Hello, world!
    $ echo foobar | python3 assemble.py -r examples/cat.golf
    foobar
    $ python3 assemble.py examples/fibonacci.golf
    $ python3 golf.py -p f examples/fibonacci.bin f=25
    75025
    Execution terminated after 154 cycles with exit code 0.

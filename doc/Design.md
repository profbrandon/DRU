
One possible way of building this project would be to design
a pipeline implemented as some sort of monadic structure.
The pipeline could then be built dynamically depending on
the arguments. Some parts of the command are ordered so that
must be respected.
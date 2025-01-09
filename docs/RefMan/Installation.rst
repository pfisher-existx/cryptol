
Installation
============
Cryptol is intended to be written and run from files. By convention, those files
end with a :code:`.cry` file extension, but that is not a requirement. For 
convenience, Galois also provides a JSON-RPC server implementation for executing
Cryptol specifications and a REPL that can be used for exploring Cryptol. The
JSON-RPC server is intended for use in prototypes or systems where performance
is not a requirement.

There are some slight differences in the syntax for running commands in the
REPL. The examples will be provided for use in a file and, where possible, the
REPL command will be provided after.

Local Installation
------------------
1. Download the binaries from the 
   `Github release page <https://github.com/GaloisInc/cryptol/releases>`_. 

  In order to solve constraints during typechecking, you must also have a solver
  installed. By default, Cryptol uses the Z3 SMT solver, but this can be
  configured otherwise. If you download a version of Cryptol without solvers,
  you will have to install one yourself.

2. Extract the files to a location of your choice.

3. Add the binaries to your PATH environment variable.


Docker Installation
-------------------
Cryptol is also packaged as a set of Docker images: one for using the REPL and
one for running the remote API server.

.. code-block:: bash

  docker pull ghcr.io/galoisinc/cryptol:3.2.0 # Pull REPL image
  docker run -it ghcr.io/galoisinc/cryptol /bin/bash 
  # Run the image and open the REPL in a shell
  # When the REPL is exited, the container will shut down

Running the JSON-RPC server will allow you to run remote commands. Files can be
provided to the remote server by binding it to a volume.

.. code-block:: bash

  docker pull ghcr.io/galoisinc/cryptol-remote-api:3.2.0 # Pull remote server


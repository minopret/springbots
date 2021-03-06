# Springbots

http://www.youtube.com/watch?v=U4vJP5q3jlo

## What is it?

Springbot is a genetic algorithm experiment in which physical simulated 2d
creatures built with nodes and springs evolve to walk, swim, jump or whatever
fitness function the user decides.  After several simulations it's possible
for one to see animal-like behaviors optimized for the desired fitness.

## Requirements

 * Python >= 2.5
 * python-qt4 (optional: springbots editor)
 * xmlrpclib-python (optional: network distribution)
 * pygame (optional: real time graphics)

## Scripts

 * `evolve.py` - Take an population described in a xml file in the stardard
                 input and evolve them for a specific fitness function chosen in
                 command line (see --help), writing statistics in standard
                 output and saving the population snapshots every several
                 iterations. Optionaly it can be run with real time graphics
                 using pygame.

 * `net-evolve.py` - Same like evolve.py but connect to a set of servers listed
                     in `fitness-servers.txt` to do the processing.

 * `fitness-server.py` - Start a fitness server, optionaly with real time
                         graphics. Listens to a TCP port accepting fitness
                         tests requests and returning the fitness itself.

 * `imagebot.py` - Transform a xml springbot description into a svg image.

 * `randombot.py` - Generate a random springbot population xml file writting in
                    standard outpuy, useful for a starting seed for
                    simulations.

 * `viewer.py` - Real time graphics of the springbot being simulated. does not
                 evolve, just for viewing purpouse.

 * `demo.py` - Takes a population xml as standard input and shows each springbot
               for a specific amount of time on it adapted environment, optionally
               includes some randoms too. This program was designed for
               demonstration purpouses.

 * `log-plot.py` - Plots a statistic graph from evolution experiments output
                   based on very flexible parameters.

## Examples

```console
# Evolve a starting random population of 100 genomes with graphics and
# statistic output:
$ ./randombot.py -p 100 | ./evolve.py -f swim -vg

# To start editor move to editor directory and run editor.py:
$ ./editor.py

# Depending on your system configuration you can run the editor direct from
# file manager.
```

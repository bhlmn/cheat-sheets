# Python Logging

Some info on how I set up logging in my python projects.

## main.py

In `__main__.py`, import `logging` and use the `argparse` package to add verbosity as a command line argument. Set the default logging level to `info`.

``` python
# __main__.py

import logging
import argparse
# other imports ...

def main():
    # process command line arguments
    parser = argparse.ArgumentParser()
    parser.add_argument('--verbosity',
                        default='info',
                        choices=['debug', 'info', 'warn'],
                        help='How verbose should the logging be? Most ' +\
                             '(debug) to least (warn). Default is info.')
    args = parser.parse_args()

    # determine logging level
    if args.verbosity == 'debug':
        logging.getLogger().setLevel(logging.DEBUG)
    elif args.verbosity == 'warn':
        logging.getLogger().setLevel(logging.WARN)
    else:
        logging.getLogger().setLevel(logging.INFO)
    logging.info('Logging verbosity set to ' + args.verbosity + '.')


if __name__ == '__main__':
    main()
```

## Other python files

Then, in all other python files within the package, import `logging` and specify the level each time you want to log information:

``` python
import logging
# other imports ...

logging.debug('This will be seen if verbosity is set to debug.') 
logging.info('This will be seen if verbosity is set to debug or info.') 
logging.warning('This will be seen if verbosity is set to debug, info, or warn.') 
```

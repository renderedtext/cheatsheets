# Bash

Count the number of files per directory:

    for i in ./*; do echo $i; find $i |wc -l; done

Split lines of output:

    command | sed -e "s/delimiter/\n/g" | tail -x

Read first n lines from file:

    line=$(head -n 1 filename)

Assign output of a shell command to a variable:

    pwd=`pwd`

or:

    pwd=$(pwd)

Test if file or directory exists:

    if [ -f /tmp/foo.txt ]
    then
        echo the file exists
    fi

One lineer:

    if [ -f config/some.yml.example ]; then mv config/some.yml.example config/some.yml; fi

    if [ -d /tmp ]
    then
        echo the directory exists
    fi

A good primer on conditionals: http://mywiki.wooledge.org/BashGuide/TestsAndConditionals.

How to repeat command n times:

    vim ~/.bash-aliases

    repeat() {
        n=$1
        shift
        while [ $(( n -= 1 )) -ge 0 ]
        do
            "$@"
        done
    }

After you `source ~/.bash-aliases` you will be able to run `repeat 5 echo hello`.

# Bash

Use output of one program, one by one, as an argument to another:

    ls | xargs -n 1 rm $1

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

How to write one-liners:

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

Echo something to a file as root:

    sudo sh -c "echo 'something' >> /etc/privilegedfile"

Find and replace across files:

    find . -name "*.rb" -print | xargs sed -i 's/foo/bar/g'

Find and replace in a single file:

    sudo sed -i 's/#START=yes/START=yes/g' /etc/default/beanstalkd

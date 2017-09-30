# minicom-2.7

Added functionality with -X option that creates second channel for send/receive.
Example:

    minicom $@ -X extrapty

will start minicom and save the name of the created pty in file extrapty.
You can then write to the serial connection while minicom is running via:

    f=`cat extrapty`
    echo "ls -la " > $f

or connect a second minicom to it:

    f=`cat extrapty`
    minicom -D $f
    



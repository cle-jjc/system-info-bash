System Info Bash Script

#! /bin/bash

# Welcome message

    echo "Hello and welcome to Christian's System Info Bash script!"
    
        sleep 1

    echo "Please wait while I get everything ready for you"
    
        echo '.'
        sleep 1
        echo '.'
        sleep 1
        echo '.'
        sleep 1

        while true; do
    
    echo 'Please select from the following options to display information'

# Selection menu

        echo 'Hostname         Displays system hostname and other information'
        echo 'OS               Displays the operating system information'
        echo 'Uptime           Displays how long the current system has been running'
        echo 'Kernal           Displays the Linux Kernal version information'
        echo 'CPU              Displays the systems CPU information'
        echo 'Memory           Displays how much memory is available on the current system'
        echo 'IP               Displays the IP address information for the current system'
        echo 'Utilization      Displays the amount of filesystem utilization and the filesystem types'
        echo 'Log              Displays the last five general log files that contain the word "error"'
        echo 'Quit             Quits the scripts'

# User Selection

    echo 'Please enter your selection: '
    
        read selection

# User Selection Outputs

    case $(echo "$selection" | tr '[:upper:]' '[:lower:]') in

    hostname)

        echo 'Please wait while I get that information for you!'
    
            echo '.'
            sleep 1
            echo '.'
            sleep 1
            echo '.'
            sleep 1

        echo 'The system hostname is: '
        hostnamectl
        ;;
    os)

        echo 'Please wait while I get that information for you!'

            echo '.'
            sleep 1
            echo '.'
            sleep 1
            echo '.'
            sleep 1

        echo 'This is the systems Operating System information: '
        cat /etc/os-release && lsb_release -a
        ;;
    uptime)
    
         echo 'Please wait while I get that information for you!'

            echo '.'
            sleep 1
            echo '.'
            sleep 1
            echo '.'
            sleep 1

        echo 'The current system uptime is: '
        uptime -p
        ;;
    kernal)
    
        echo 'Please wait while I get that information for you!'

            echo '.'
            sleep 1
            echo '.'
            sleep 1
            echo '.'
            sleep 1

        echo 'This is the Linux Kernal information: '
        uname -r
        ;;
    cpu)
    
        echo 'Please wait while I get that information for you!'
    
            echo '.'
            sleep 1
            echo '.'
            sleep 1
            echo '.'
            sleep 1

        echo 'This is the systems CPU information: '
        lscpu
        ;;
    memory)

        echo 'Please wait while I get that information for you!'
    
            echo '.'
            sleep 1
            echo '.'
            sleep 1
            echo '.'
            sleep 1

        echo 'The current available space on this system is: '
        free
        ;;
    ip)

        echo 'Please wait while I get that information for you!'
    
            echo '.'
            sleep 1
            echo '.'
            sleep 1
            echo '.'
            sleep 1

        echo 'The systems IP information is: '
        ifconfig
        ;;
    utilization)

        echo 'Please wait while I get that information for you!'
    
            echo '.'
            sleep 1
            echo '.'
            sleep 1
            echo '.'
            sleep 1

        echo 'This is the current filesystem utilization: '
        df -Th
        ;;
    log)

        echo 'Please wait while I get that information for you!'
    
            echo '.'
            sleep 1
            echo '.'
            sleep 1
            echo '.'
            sleep 1

        echo 'These are the last five general logs that contain the word "error"'
        grep -i error /var/log/syslog | tail -n 5
        ;;
    quit)
        echo 'Exiting'
    
            echo '.'
            sleep 1
            echo '.'
            sleep 1
            echo '.'
            sleep 1

        echo "Thank you for using Christian's System Info Bash script!"
        exit
        ;;
    *)
        echo 'Invalid Option! Please make sure you are selecting an option from the selection menu!'
        ;;
        esac

# Continuation Choice
while true; do

    read -p 'Would you like to make another selection? (Y/N): ' continue_choice
    case $continue_choice in
        [Nn]* )
            echo 'Exiting'

                echo '.'
                sleep 1
                echo '.'
                sleep 1
                echo '.'
                sleep 1
            echo "Thank you for using Christian's System Info Bash script!"
            exit;;
        [Yy]* )
            break;;
        * )
            echo 'Invalid Option! Please make sure you are using Y/y or N/n!'
    esac

    done

done

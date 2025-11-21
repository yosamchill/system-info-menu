#!/bin/bash

while true
do
    echo "-------------------------------------"
    echo "        SYSTEM INFORMATION MENU"
    echo "-------------------------------------"
    echo "1. Show Current Date and Time"
    echo "2. Show Users Currently Logged In"
    echo "3. Show Disk Usage"
    echo "4. Show Memory Usage"
    echo "5. Show System Uptime"
    echo "6. Exit"
    echo "-------------------------------------"
    read -p "Enter your choice [1-6]: " choice

    case $choice in
        1) 
            echo -e "\nCurrent Date and Time:"
            date
            ;;
        2)
            echo -e "\nUsers Logged In:"
            who | wc -l
            ;;
        3)
            echo -e "\nDisk Usage:"
            df -h --total | grep total
            ;;
        4)
            echo -e "\nMemory Usage:"
            free -h
            ;;
        5)
            echo -e "\nSystem Uptime:"
            uptime -p
            ;;
        6)
            echo "Exiting... Goodbye!"
            break
            ;;
        *)
            echo "Invalid choice, please try again."
            ;;
    esac

    echo -e "\nPress Enter to continue..."
    read
done

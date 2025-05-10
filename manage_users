#!/bin/sh -u
PATH=/bin:/usr/bin ; export PATH
umask 022

#Description: To add, change user's groups, login shell, and expiration, and also delete user.

menu(){
	clear
	echo "Input your choice. You can: "
	echo "1. Add User Account (Press A or a)"
	echo "2. Change a user’s initial/primary group (Press I or i)"
	echo "3. Change a user’s supplementary group (Press S or s)"
	echo "4. Change a user’s login shell for a user account (Press L or l)"
	echo "5. Change the expiration date for a user account (Press E or e)"
	echo "6. Delete a user account (Press D or d)"
	echo "7. Quit the script (Press Q or q)"
	echo -n "Input: "
}

add_user(){
	clear
	echo -n "New username: "
	read username
	echo -n "Enter home directory (absolute path): "
	read homeDirectory
	echo -n "Enter Default Login Shell (absolute path): "
	read defaultLoginShell
	sudo useradd -m -d "$homeDirectory" -s "$defaultLoginShell" "$username"

	if [ $? -eq 0 ]; then
		echo "$username has been created successfully (yipee!) :D"
	else
		echo 1>&2 "$0: Error: Failed to create $username :("
	fi

	sleep 3
}

change_user_initial_group(){
	clear
	echo -n "Username: "
	read username
	echo -n "New initial group: "
	read initialGroup
	sudo usermod -g "$initialGroup" "$username"
	
	if [ $? -eq 0 ]; then
		echo "$username's initial group has changed to $initialGroup :)"
	else
		echo 1>&2 "$0: Error: Failed to change $username's initial group to $initialGroup :("
	fi

	sleep 3
}

change_user_supplementary_group(){
	clear
	echo -n "Username: "
	read username
	echo -n "New supplementary group: "
	read supplementaryGroup
	sudo usermod -aG "$supplementaryGroup" "$username"

	if [ $? -eq 0 ]; then
		echo "$username's supplementary group has changed to $supplementaryGroup :)"
	else
		echo 1>&2 "$0: Error: Failed to change $username's supplementary group to $supplementaryGroup :("
	fi

	sleep 3
}

change_user_login_shell(){
	clear
	echo -n "Username: "
	read username
	echo -n "New login Shell: "
	read loginShell
	sudo usermod -s "$loginShell" "$username"

	if [ $? -eq 0 ]; then
		echo "$username's login shell has changed to $loginShell :)"
	else
		echo 1>&2 "$0: Error: Failed to change $username's login shell to $loginShell :("
	fi

	sleep 2
}

change_expiration_date(){
	clear
	echo -n "Username: "
	read username
	echo -n "New expiration date (format: YYYY-MM-DD): "
	read expirationDate
	sudo usermod -e "$expirationDate" "$username"

	if [ $? -eq 0 ]; then
		echo "$username's expiration date has changed to $expirationDate :)"
	else
		echo 1>&2 "$0: Error: Failed to change $username's expiration date to $expirationDate :("
	fi

	sleep 3
}

delete_user_account(){
	clear
	echo -n "Username: "
	read username
	sudo userdel -r "$username" 2>/dev/null

	if [ $? -eq 0 ]; then
		echo "$username has been deleted successfully :D"
	else
		echo 1>&2 "$0: Error: Failed to delete $username :("
	fi

	sleep 3
}

none_option(){
	clear
	echo "echo Please input the correct option >:("
	sleep 3
}

while true; do
	menu
	read choice
	case $choice in
		A|a) add_user ;;
		I|i) change_user_initial_group ;;
		S|s) change_user_supplementary_group ;;
		L|l) change_user_login_shell ;;
		E|e) change_expiration_date ;;
		D|d) delete_user_account ;;
		Q|q) break ;;
		*) none_option ;;
	esac
done

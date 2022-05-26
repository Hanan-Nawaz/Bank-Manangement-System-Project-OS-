#!/bin/sh
echo "";
echo "";
echo "-------------------------";
echo "|      Bank of NUML     |";
echo "-------------------------";
echo "";
echo "";
echo "-------------------------";
echo "|   Welcome  Customer   |";
echo "-------------------------";
echo "";
echo "";
while true
do
echo "";
echo "";
echo "-------------------------";
echo "|     Please Select     |";
echo "-------------------------";
echo "";
echo "";
echo "-------------------------";
echo "| 1 | Open Bank Account |";
echo "-------------------------";
echo "| 2 | View Account List |";
echo "-------------------------";
echo "| 3 | Search Account    |";
echo "-------------------------";
echo "| 4 | Withdraw Amount   |";
echo "-------------------------";
echo "| 5 | Deposit Amount    |";
echo "-------------------------";
echo "| 6 | Modify Account    |";
echo "-------------------------";
echo "| 7 | Close Account     |";
echo "-------------------------";
echo "| 8 | Logout            |";
echo "-------------------------";
echo "Please Select(1-8)";
read select;
case "$select" in
"1")
echo "";
echo "";
echo "-------------------------";
echo "|   Open Bank Account   |";
echo "-------------------------";
echo "";
echo "";
echo "Enter Account Number";
read -r account_number
if [ "$(fgrep -c $account_number BAccount.txt)" -eq 1 ]
then
echo "-------------------------------------------------------";
echo "| THE Account WITH Account Number $account_number ALREADY EXISTS |";
echo "-------------------------------------------------------";
else
echo "Enter Account Name";
read -r account_name
echo "Enter CNIC";
read -r account_cnic
echo "Enter Mobile Number";
read -r account_phone
echo "Enter Type (Saving/Current)";
read -r account_type
echo "Enter Initial Amount";
read -r account_amount
echo 'Account Number: '$account_number , 'Account Name: '$account_name , 'CNIC: '$account_cnic ,'Mobile Number: '$account_phone ,'Type :'$account_type , 'Initial Amount: '$account_amount >>BAccount.txt
echo "";
echo "";
echo "-----------------------------------------------";
echo "| Congratulations Account Opened Successfully |";
echo "-----------------------------------------------";
echo "";
echo "";
fi
;;
"2")
echo "";
echo "";
echo "-------------------------";
echo "|   View Account's List  |";
echo "-------------------------";
echo "";
echo "";
cat BAccount.txt;
;;
"3")
echo "";
echo "";
echo "-------------------------";
echo "|   Search Bank Account  |";
echo "-------------------------";
echo "";
echo "";
echo "Enter Account Number";
read -r account_number
echo "";
echo "";
echo "$(fgrep -w $account_number BAccount.txt)";
;;
"4")
echo "";
echo "";
echo "-------------------------";
echo "|     Withdraw Amount   |";
echo "-------------------------";
echo "";
echo "";
echo "Enter Account Number";
read -r account_number
if [ "$(fgrep -c $account_number BAccount.txt)" -eq 1 ]
then
value="$(grep $account_number BAccount.txt)";
sed -i "/$account_number/d" BAccount.txt;
echo $value >>Modify.txt
Current="$(awk '{ print $19 }' Modify.txt)";
echo "Current Balance is $Current PKR";
sed -i "/$account_number/d" BAccount.txt;
read -p "Enter the Amount: " withdraw
if [ "$withdraw" -gt "$Current" ]
then
echo "";
echo "---------------";
echo "| Low Balance |";
echo "---------------";
echo "";
else
left=$((Current-withdraw));
data="$(awk '{ print $1,$2,$3,$4,$5,$6,$7,$8,$9,$10,$11,$12,$13,$14,$15 }' Modify.txt)";
sed -i "/$account_number/d" Modify.txt;
echo $data , 'Initial Amount: '$left >>Modify.txt;
fi
value1="$(grep $account_number Modify.txt)";
echo $value1 >>BAccount.txt;
sed -i "/$account_number/d" Modify.txt;
else
echo "-------------------------------------------------------";
echo "| THE Account WITH Account Number $account_number Doesn't EXISTS |";
echo "-------------------------------------------------------";
fi
;;
"5")
echo "";
echo "";
echo "-------------------------";
echo "|     Deposit  Amount   |";
echo "-------------------------";
echo "";
echo "";
echo "Enter Account Number";
read -r account_number
if [ "$(fgrep -c $account_number BAccount.txt)" -eq 1 ]
then
value="$(grep $account_number BAccount.txt)";
sed -i "/$account_number/d" BAccount.txt;
echo $value >>Modify.txt
Current="$(awk '{ print $19 }' Modify.txt)";
echo "Current Balance is $Current PKR";
sed -i "/$account_number/d" BAccount.txt;
read -p "Enter the Amount: " withdraw
left=$((Current+withdraw));
data="$(awk '{ print $1,$2,$3,$4,$5,$6,$7,$8,$9,$10,$11,$12,$13,$14,$15 }' Modify.txt)";
sed -i "/$account_number/d" Modify.txt;
echo $data , 'Initial Amount: '$left >>Modify.txt;
value1="$(grep $account_number Modify.txt)";
echo $value1 >>BAccount.txt;
sed -i "/$account_number/d" Modify.txt;
else
echo "-------------------------------------------------------";
echo "| THE Account WITH Account Number $account_number Doesn't EXISTS |";
echo "-------------------------------------------------------";
fi
;;
"6")
echo "";
echo "";
echo "-------------------------";
echo "|     Please Select     |";
echo "-------------------------";
echo "";
echo "";
echo "-------------------";
echo "| 1 | Change Name |";
echo "-------------------";
echo "| 2 | Change CNIC |";
echo "-------------------";
echo "| 3 | Change No.  |";
echo "-------------------";
echo "| 4 | Exit        |";
echo "-------------------";
echo "Please Select(1-4)";
read -r choice
if [ "$choice" -eq 1 ]
then
echo "";
echo "";
echo "-------------------";
echo "|   Change Name   |";
echo "-------------------";
echo "";
echo "";
echo "Enter Account Number";
read -r account_number
if [ "$(fgrep -c $account_number BAccount.txt)" -eq 1 ]
then
value="$(grep $account_number BAccount.txt)";
echo $value >>Modify.txt
filename="Modify.txt"
sed -i "/$account_number/d" BAccount.txt;
value="$(grep $account_number BAccount.txt)";
echo $value >>Modify.txt
filename="Modify.txt"
sed -i "/$account_number/d" BAccount.txt;
read -p "Enter the Current Name: " search
read -p "Enter the New Name: " replace
sed -i "s/$search/$replace/" $filename
value1="$(grep $account_number Modify.txt)";
echo $value1 >>BAccount.txt;
sed -i "/$account_number/d" Modify.txt;
else
echo "-------------------------------------------------------";
echo "| THE Account WITH Account Number $account_number Doesn't EXISTS |";
echo "-------------------------------------------------------";
fi
elif [ "$choice" -eq 2 ]
then
value="$(grep $account_number BAccount.txt)";
echo $value >>Modify.txt
filename="Modify.txt"
sed -i "/$account_number/d" BAccount.txt;
echo "";
echo "";
echo "-------------------";
echo "|   Change CNIC   |";
echo "-------------------";
echo "";
echo "";
echo "Enter Account Mobile Number";
read -r account_number
if [ "$(fgrep -c $account_number BAccount.txt)" -eq 1 ]
then
value="$(grep $account_number BAccount.txt)";
echo $value >>Modify.txt
filename="Modify.txt"
sed -i "/$account_number/d" BAccount.txt;
read -p "Enter the Current CNIC: " search
read -p "Enter the New CNIC: " replace
sed -i "s/$search/$replace/" $filename
value1="$(grep $account_number Modify.txt)";
echo $value1 >>BAccount.txt;
sed -i "/$account_number/d" Modify.txt;
else
echo "-------------------------------------------------------";
echo "| THE Account WITH Account Number $account_number Doesn't EXISTS |";
echo "-------------------------------------------------------";
fi
elif [ "$choice" -eq 3 ]
then
echo "";
echo "";
echo "-------------------";
echo "|  Change Number  |";
echo "-------------------";
echo "";
echo "";
echo "Enter Account Number";
read -r account_number
if [ "$(fgrep -c $account_number BAccount.txt)" -eq 1 ]
then
value="$(grep $account_number BAccount.txt)";
echo $value >>Modify.txt
filename="Modify.txt"
sed -i "/$account_number/d" BAccount.txt;
read -p "Enter the Current Mobile Number: " search
read -p "Enter the New Mobile Number: " replace
sed -i "s/$search/$replace/" $filename
value1="$(grep $account_number Modify.txt)";
echo $value1 >>BAccount.txt;
sed -i "/$account_number/d" Modify.txt;
else
echo "-------------------------------------------------------";
echo "| THE Account WITH Account Number $account_number Doesn't EXISTS |";
echo "-------------------------------------------------------";
fi
fi
;;
"7")
echo "";
echo "";
echo "-------------------------";
echo "|   Close Bank Account  |";
echo "-------------------------";
echo "";
echo "";
echo "Enter Account Number";
read -r account_number
echo "";
echo "";
sed -i "/$account_number/d" BAccount.txt;
echo "";
echo "";
echo "-------------------------";
echo "|    Closed Sucessfully  |";
echo "-------------------------";
echo "";
echo "";
;;
"8")
echo "-----------------------------------------------";
echo "|    Thanks For Working with Bank of NUML     |";
echo "-----------------------------------------------";
echo "";
echo "";
exit 0
;;
esac
done

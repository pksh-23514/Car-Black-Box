# Car-Black-Box
Initially run the Makefile from CBB_EEPROM_Loader folder. It stores the initial values in the External EEPROM. After this, run the Makefile from CBB_Main folder. This starts executing the Project on the PIC18F4580 Micro-controller board. An on-board CLCD screen is used to create an interactive interface.

Initially a Dashboard screen is displayed. It shows Current time, Last occurred event and Vehicle speed. Vehicle speed can be varied using the on-board POT (potentiometer). Matrix SW1 is used to register the Gear UP event. Matrix SW2 is used to register the Gear DOWN event. Matrix SW3 is used to register the Collision event. These event types are stored onto External EEPROM at any time in any display mode. Note that the other events are not displayed on dashboard. They are visible only in View log & Download log operation.

Matrix SW8 when pressed once takes the user to Password screen. Now the User has to provide the Correct Password. Initial Password is "0000" (changeable). Same Matrix SW8 is used to write '0' while Matrix SW9 is used to write '1'. With every entry, User can just see a '*' on the CLCD screen. User has to provide the password within 5 sec (changeable). If Password is correct then, a Log Menu screen opens up. Here, user can Scroll UP and DOWN using the matrix SW11 & matrix SW10 key respectively. If Password does not match, 4 (changeable) more tries are given to User. If User fails to provide the Correct Password after 5th try then, the screen will be locked for 60 sec (changeable). After 60 sec, User can retry again further 5 times.

Long pressing of matrix SW10 performs the rsepective functionalities:
1. View log: User can see last 10 possible Events stored in the Data log from the External EEPROM.
2. Clear log: A message appears on the screen saying that the Log is cleared from the External EEPROM. Now, in the View log mode; rest of the Events will not be visible to User. Scrolling operation will be ineffective.
3. Change Password : User can set a new Password. In this, after entering the Password once, the user will be asked to re-enter the Password. Now the user has to give the same pattern. Otherwise, it repeats enter & re-enter cycles.
4. Download log: User has to open the Serial terminal like Minicom or PuTTY etc. on the PC and connect the board with it using UART communication. After Long pressing the Download log option, the Data log will be printed on the Serial monitor.

Long pressing of matrix SW11 will take the User back to the Log Menu if a particular Option is opened. Again Long pressing of matrix SW11 will take the User back to the Dashboard.

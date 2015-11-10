# Setup for Health website

1. Open up the command prompt. This can be done in a variety of ways.
   * **Method 1**: press WindowsKey + R, then type cmd
   * **Method 2**: press WindowsKey, then type cmd

2. Change into the directory where your project is located. You will need to make use of commands: 
   * ```dir``` to view all files/subdirectories in your current directory 
   * ```cd [name of subdirectory]``` to change directories. 
   * You have successfully done this step once you get to the point where you can type "dir" and see the file ```manage.py```

3. We will begin by making migrations. This is a two step process. In the command prompt type
    ```
    python manage.py makemigrations
    ```
    then
    ```
    python manage.py migrate
    ```
4. We will now create an admin account. Do this by typing in the command prompt
    ```    
    python manage.py createsuperuser
    ```
    * If done successfully you will be prompte to enter a username, email, and password
    * **DON'T FORGET THE USERNAME AND PASSWORD! YOU WILL NEED THIS LATER**

5. We will now start up the website. In the command prompt type
   ```
   python manage.py runserver
   ```

6. Nagivate to the website in any browser.
    * Depending on the browser the url is slightly different, for example:
      * In chrome, it is sufficient to just type localhost:8000
      * In Internet Explorer, you need to type http://localhost:8000/

7. From here, you should be ready to start experimenting with the website. See the subsections below for optional guides on establishing certain tasks on the website

### Creating a patient
1. Go to the homepage, http://localhost:8000/ and ensure you are not already logged in to an existing account
2. click on **link to register as a patient**
3. Fill out the form
    * **Phone** must be in the form of ten consecutive digits (no spaces). For example, **5851234567** would be the correct entry for the phone number 585-123-4567
    * **date** must be in the form **xx/xx/xxxx**
    * **social security** must in the form of nine consecutive digits (no spaces). For example, **123121234** would be the correct entry for the SSN 123-12-1234
4. Upon successful completion of the form, the patient has been created. He/she can now log in with the patient's username and password

### Logging in
1. Go to the homepage, http://localhost:8000/ and ensure you are not already logged in to an existing account
2. Click on "link to login"
    * **alternative method 1** go to page http://localhost:8000/login
    * **alternative method 2** click on the login button on the black side bar
3. Enter the correct username and password. If the credientials don't match you will be forwarded to the same page to try again

### Creating a Doctor/Nurse
1. Log in to an administrator account
2. If registering as a doctor click on **link to register as doctor**
3. If registering as a nurse click on **link to register as a nurse**
4. Fill out the form
    * See [step 3 from Creating a Patient](#Creating-a-Patient)
5. Upon successful completion of the form, the nurse/doctor has been created. He/she can now log in with the associated username and password

### Sending a private message
1. Log in to any user account
2. Click on **send private message**
3. Select the desired user from the **Receiver** drop down menu
4. In the **Message** text box, type the message you want to send to the user
5. Click the **send** button to send the message

### Viewing private messages
1. Log in to any user account
2. Go to the homepage, http://localhost:8000/
3. If you have any messages sent to you, they will be displayed on the homepage
4. **note**: to verify the functionality of sending and viewing private messages, send a message to yourself then try to view it from the homepage

### Update profile (as a patient)
1. Log in to an existing patient account
2. On the black sidebar, click on **Update profile**
3. Fill out the forms
4. click **submit**
5. **This is a broken so it won't work**

### Update patient medical information
1. Log in to an existing doctor account
2. Click on **Update patient medical information**
3. Select the patient you want to update using the drop down menu
4. Change the medication or upload another file 

### Viewing Logging Activity
1. Log in to an existing admin account
2. On the black sidebar, click on **View logging activity**

### Accessing the admin console
1. Navigate to http://localhost:8000/admin
2. Log in with the credentials of an existing admin account

### Known Bugs
* A non-admin user must be created before logging into the admin account or else an error will occur
* Logging in with incorrect credentials causes an error
* Multiple appointments can be made but only one appointment will show 
* Currently making appointments only work for patients. This functionality should be extended to doctors and nurses
* Can not cancel an appointment. A patient should be able to do this
* When logged into a doctor, when selecting update patient medical information, "fail" displayed and when selecting a patient, "success" is displayed. **These are debug messages and will be removed in the released**
* Nurses can't do much in our current build. But they can do various things

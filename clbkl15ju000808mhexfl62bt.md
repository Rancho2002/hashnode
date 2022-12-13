# How to send automatic messages to your friend on WhatsApp?

In the 21st century, people love to automate everything. Now sending messages is also possible with some simple lines of code. If you are not a programmer, it's not a big issue. Understanding logic is the main thing in every work you do.

### Let's understand, what are the prerequisites for this hack:

*   Python(latest version)
    
*   Whatsapp installed(web or app) on your PC
    

## #Step 1:

First of all, if you do not have Python installed on your PC,

*   open **Chrome Browser**
    
*   Type **Python Install** in the search bar
    
*   Head to the first website [python.org/downloads](https://www.python.org/downloads/)
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670828020353/plst2D-cO.png align="center")
    
*   Download & Install the latest version
    

## #Step 2:

Install **Whatsapp** from the Microsoft store or from the browser.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670828538261/mtXekJp3y.png align="center")

## #Step 3:

Open **Windows PowerShell** or **Command Prompt** or **Bash** and type the below command:

```bash
python --version
```

If you get this kind of output as shown below, then you have successfully installed python on your system and you can move to the next steps else follow **#Step 1** again.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670828667990/HI3Rn2Jmy.png align="center")

## #Step 4:

Now let's come to the most important steps.

1.  Open **Windows PowerShell** or **Command Prompt** or **Bash** and type the below command:
    
    ```bash
    pip install pyautogui
    ```
    
2.  In my case, I have already pyautogui installed on my system, so it shows like this.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670842169123/YSPy8IrxY.png align="center")
    
3.  After **pyautogui** installation, copy the below code
    
    ```python
    import pyautogui as ai
    import time
    time.sleep(4)
    i=1
    while (i!=25):
        ai.write("My message") # Write your message in My message section
        ai.keyDown('enter')
        i+=1
    ```
    
4.  Open **Notepad** and change the "My message" section with your desired message.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670833922752/JDRpsHlOr.png align="center")
    
5.  Now create a folder in the desktop and save this file inside the folder. Name this file as **AImessage.py**, click on **Yes** if you get any kind of warning.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670834449078/oQ1H7bxxk.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670834458728/JmMBB0UjC.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670834550497/C5E5IZVpX.png align="center")
    
6.  Open **Whatsapp** and select the chat to whom you want to send the message.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670835161911/mrPu_BgEv.png align="center")
    
7.  Minimize the screen
    
8.  Now the final step to automate your message.
    

*   Right click on the folder and click on **open in terminal**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670834787054/YRFXk7htp.png align="center")
    
*   Type the below command as mentioned below
    
    ```bash
     python .\AImessage.py
    ```
    
*   Hit **Enter <mark>[⚠️⚠️⚠️ Read Below Message first before pressing Enter ⚠️⚠️⚠️]</mark>**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670835586895/5Z14oWQNj.png align="center")
    
*   After you have pressed **Enter** quickly navigate to **Whatsapp** which you have already minimized before. You have 4 secs to open the tab(**Shortcut: Alt+tab**) and **SEE THE MAGIC.** In case you need more time to open **Whatsapp**, change the *time.sleep(4)* to *time.sleep(10)* to get 10 seconds delay.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670835403345/qDSxkQFLm.png align="center")
    
    In the above program, you have send 25 messages to your friend automatically. In case you want to send more message change the section `while(i<=25)` to `while(i<=100)` to send 100 automatic messages in your code.
    

# Finally you have sent your automate messages successfully. If you want to know how this things work, don't forget to comment below.
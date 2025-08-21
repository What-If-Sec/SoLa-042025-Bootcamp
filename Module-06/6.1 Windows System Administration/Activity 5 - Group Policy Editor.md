## Activity Objective

Students will learn how to use the Group Policy Editor (`gpedit.msc`) in Windows to manage and configure system settings and policies. By the end of the activity, students will be able to navigate the Group Policy Editor, understand its structure, and apply policies to manage user and computer configurations effectively.

## Activity Instructions

Follow the instructions below:

1. Open the Local Group Policy Editor and explore the user and computer settings that you can configure.

2. Set a Default Homepage in Internet Explorer  
   - Navigate to:  
     `User Configuration -> Administrative Templates -> Windows Components -> Internet Explorer`
   - Find and double-click **"Disable changing home page settings"**
   - Enable the policy
   - Enter: `https://www.thesolafoundation.org/` as the default homepage
   - Click OK
   - Verify that the browser opens to the specified homepage and that you cannot change it.

3. Require a Password on Wake Up:  
   - Navigate to:  
     `Computer Configuration -> Administrative Templates -> System -> Power Management -> Sleep Settings`
   - Find and double-click **"Require a password when a computer wakes (plugged in)"**
   - Enable the policy
   - Verify that the computer now requires a password on wakeup.

4. Configure Automatic Updates:  
   - Navigate to:  
     `Computer Configuration -> Administrative Templates -> Windows Components -> Windows Update`
   - Find and double-click **"Configure Automatic Updates"**
   - Set the policy to `4 - Auto Download and Schedule the Install`
   - Set the desired install time to **3:00 AM**

5. Record and submit your analysis on the importance and practical uses of the Group Policy Editor in managing systems.

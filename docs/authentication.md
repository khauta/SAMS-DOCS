# Authentication: Login & Password Update

This guide explains the process for logging into the My Wallet application and handling the mandatory password update required for some accounts.

## Login Process

1.  Navigate to the login page (typically the application's starting point or `/auth/login`).
2.  Enter your assigned **Username** (e.g., your email address)[cite: 14, 332].
3.  Enter your current **Password**.
4.  You may have an option to check **Remember Me** to potentially extend your session duration.
5.  Click the **Login** button.

### Login Outcome:

* The application securely sends your credentials to the backend for verification.
* **If credentials are invalid:** An error message will be displayed on the login form (e.g., "Invalid username or password").
* **If credentials are valid:** The backend checks if your account requires a password reset (indicated by a `reset: 1` flag in the user data).
    * **Reset NOT Required (`reset: 0`):** You will be logged in and automatically redirected to the main application **Dashboard**[cite: 18, 336].
    * **Reset REQUIRED (`reset: 1`):** You will remain on the login screen context, but a **Password Update** modal dialog will appear overlaying the application. You *must* complete this step to access the dashboard.

## Mandatory Password Update (Modal Dialog)

If the Password Update modal appears after logging in:

1.  **Current Password:** Re-enter the password you just used to successfully log in. This field is required [cite: (Implied from standard update forms)].
2.  **New Password:** Enter a new, secure password. It must meet complexity requirements (e.g., minimum 8 characters) [cite: (Implied from component code)]. This field is required.
3.  **Confirm New Password:** Re-enter the exact same new password to confirm it. This field is required and must match the New Password field [cite: (Implied from component code)].
4.  **Error Display:** If there are validation errors (e.g., required field empty, passwords don't match, minimum length not met), error messages will appear below the respective input fields [cite: (Implied from standard Angular Material forms)]. An overall error message from the backend (e.g., "Invalid current password") may also appear if the submission fails [cite: (Implied from component code)].
5.  **Update Button:** Click this button to submit the password change request to the backend. The button is disabled until all fields are validly filled and the new passwords match [cite: (Implied from component code)].
    * **On Success:** The backend confirms the update. The modal dialog closes automatically, and you are redirected to the main application **Dashboard**. A brief success notification might appear [cite: (Implied from component code)].
    * **On Failure:** The backend rejects the update (e.g., incorrect current password). An error message appears in the modal. Correct the information and click "Update" again [cite: (Implied from component code)].
6.  **Cancel Button:** Clicking "Cancel" closes the modal dialog and navigates you back to the **Login** page. You will need to log in again and successfully complete the password update if it is still required for your account [cite: (Implied from component code)].

*(Consider adding screenshots of the login page and the password update modal dialog here)*
# Creating a System Restore Point in Windows

## 📌 Project Overview
This document explains what a System Restore Point is, why it is important, and provides step-by-step instructions on how to create one manually using both the Windows GUI and PowerShell. A restore point allows you to revert your computer's system files, drivers, and registry settings to a previous working state if something goes wrong.

---

## 🛡️ What is a System Restore Point?
A System Restore Point is a snapshot of your computer's system files, installed programs, Windows Registry, and drivers at a specific point in time. It does **not** back up your personal files (like documents, photos, or videos). It is primarily used to undo system changes (e.g., a bad driver update or software installation) without affecting your personal files.

---

## 💻 Method 1: Using the Windows GUI (Graphical User Interface)

### Step 1: Open System Protection
1. Press the **Windows Key** on your keyboard.
2. Type **"Create a restore point"** and press **Enter**.
3. The **System Properties** window will open. Make sure you are on the **System Protection** tab.

### Step 2: Select the Drive
1. Under the "Protection Settings" section, look for your main drive (usually **C: On** or **C: Off**).
2. If it says **Off**, select the drive and click **Configure** to turn it on.
3. Ensure **"Turn on system protection"** is selected. Allocate some disk space (5-10% is usually enough).
4. Click **Apply** and **OK**.

### Step 3: Create the Restore Point
1. Back in the System Protection tab, click the **Create...** button at the bottom.
2. A small window will pop up asking you to type a description.
3. Type a clear name (e.g., `Before Installing New Software` or `Manual Restore Point`).
4. Click **Create**.
5. Windows will take a few moments to create the snapshot. A message will appear saying "The restore point was created successfully."

---

## ⚡ Method 2: Using PowerShell (Command Line)

If you prefer using the command line or need to automate this process, you can use PowerShell.

### Step 1: Open PowerShell as Administrator
1. Press the **Windows Key**, type **"PowerShell"**.
2. Right-click on **Windows PowerShell** and select **"Run as administrator"**.

### Step 2: Run the Command
Type the following command and press **Enter**. Replace the description with your own text.

```powershell
Checkpoint-Computer -Description "Manual Restore Point via PowerShell" -RestorePointType "MODIFY_SETTINGS"

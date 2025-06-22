# Group Policy Wallpaper Enforcement  
*Enforcing corporate wallpaper via Active Directory Group Policy*

---

## Step 1: Prepare Network Share  
![NETLOGON Share Configuration](gpo%201.png)  
- Created `NETLOGON` share on server `ELI01`  
- Confirmed share permissions for domain user access  
 

---

## Step 2: Upload Wallpaper File  
![Wallpaper File in Share](gpo%202.png)  
- Added `it_wallpaper.jpg` to `\\ELI01\NETLOGON\`  
- File properties: JPG
- Access path: `\\ELI01\NETLOGON\it_wallpaper.jpg`  

---

## Step 3: Create GPO  
![New GPO Creation](gpo%203.png)  
1. Opened **Group Policy Management Console**  
2. Created new GPO: `Set background for users`  
3. Linked to domain: `Eli.local`  

---

## Step 4: Configure Wallpaper Policy  
![Policy Navigation](gpo%204.png)  
- Path: `User Configuration > Policies > Administrative Templates > Desktop > Desktop`  
- Enabled: **Desktop Wallpaper** setting  
- Blocked user changes with:  
  `Prohibit changes`  
  `Allow only bitmapped wallpaper`  

---

## Step 5: Set Wallpaper Path  
![Wallpaper Configuration](gpo%205.png)  
- **Wallpaper Name**: `\\ELI01\NETLOGON\it_wallpaper.jpg`  
- **Wallpaper Style**: Centered  
- *Critical: Used UNC path for network accessibility*  

---

## Step 6: Scope GPO Application  
![GPO Security Filtering](gpo%206.png)  
- Applied to: **Authenticated Users**  
- Linked to: Domain root (inherits to all users)  
 

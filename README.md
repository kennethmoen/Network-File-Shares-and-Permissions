<p align="center">
<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/d6192fbb-d4fb-4f62-b6ed-806da21dc4ff"/>
</p>
<p>
<h2>Network File Shares and Permissions</h2>

In this lab will be sharing files and folders throughout the network and giving and taking permissions away from accounts.
  
<h2>Create some sample file shares with various permissions</h2>

- Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin)

- Connect/log into Client-1 as a normal user (mydomain\<someuser>)

- On DC-1, on the C:\ drive, create 4 folders: “read-access”, “write-access”, “no-access”, “accounting”

<img src="https://github.com/kennethmoen/Network-File-Shares-and-Permissions/assets/145589069/b0926090-76ac-4bf0-a8cb-1100449057ae"/>


- Set the following permissions (share the folder) for the “Domain Users” group:
- Folder: “read-access”, Group: “Domain Users”, Permission: “Read”
- Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write”
- Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”
- (Skip accounting for now)

<img src="https://github.com/kennethmoen/Network-File-Shares-and-Permissions/assets/145589069/7051ca9e-a023-469c-ad46-a1943a9b9e47"/>


"/>
</p>

  <h2>Attempt to access file shares as a normal user</h2>
  
  On Client-1, navigate to the shared folder (start, run, \\dc-1)

  <img src="https://github.com/kennethmoen/Network-File-Shares-and-Permissions/assets/145589069/4911cc5f-1bd2-4c23-ac58-47cb561a3095"/>

  Try to access the folders you just created. Which folders can you access? Which folders can you create stuff in? 

  <img src="https://github.com/kennethmoen/Network-File-Shares-and-Permissions/assets/145589069/8265ba27-7c0a-41e7-b7e4-098e2109876a"/>

  You can see that some folders you can't access, some you can but can't create anything in.
  
  <img src="https://github.com/kennethmoen/Network-File-Shares-and-Permissions/assets/145589069/d9a58403-5a80-4095-a6b4-ad650ccc118a</p>

  In the picture below I went back into DC-1 created a new text document in read only, then demonstrated how you can open, but not edit the file with the given permissions.

  <img src="https://github.com/kennethmoen/Network-File-Shares-and-Permissions/assets/145589069/d203f0f0-4826-4b92-987b-323f62019648"/>

  
<p>

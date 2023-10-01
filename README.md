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

<p>
  <h2>Create an “ACCOUNTANTS” Security Group, assign permissions, an test access
</h2>
Go back to DC-1, in Active Directory, create a security group called “ACCOUNTANTS”
 <img src="https://github.com/kennethmoen/Network-File-Shares-and-Permissions/assets/145589069/5e66a111-15f8-42dd-8cc3-118142db41c7"/>

On the “accounting” folder you created earlier, set the following permissions:
Folder: “accounting”, Group: “ACCOUNTANTS”, Permissions: “Read/Write”
  
 <img src="https://github.com/kennethmoen/Network-File-Shares-and-Permissions/assets/145589069/0f6e06f3-008c-4293-9a59-a6c9f4516e09"/>

- On Client-1, as  <someuser>, try to access the accountants folder. It will fail.

- Log out of Client-1 as  <someuser>

  <img src="https://github.com/kennethmoen/Network-File-Shares-and-Permissions/assets/145589069/5a37a799-2cdd-439d-ba7c-c9ba3e7cd98a"/>

- On DC-1, make <someuser> a member of the “ACCOUNTANTS”  Security Group. Mine was baf.xuq.

<img src="https://github.com/kennethmoen/Network-File-Shares-and-Permissions/assets/145589069/a7729715-e5f3-47ad-99e9-017adabbf32d"/>

- Sign back into Client-1 as <someuser> and try to access the “accounting” share in \\DC-1\ - Does it work now?

 <img src="https://github.com/kennethmoen/Network-File-Shares-and-Permissions/assets/145589069/153a8271-25b2-431c-b1ea-1aa2c1eab157"/>
</p>

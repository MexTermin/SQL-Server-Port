# How to know SQL Server Port
### *Step 1*
- Open your SQL Management Studio
- Right Click in you SQL connection
- Click in New Query
- Paste and execute :
```
USE master
GO
xp_readerrorlog 0, 1, N'Server is listening on',N'', NULL, NULL, N'asc'
GO
```

<p>
it should show you the SQL Server Port. If this dont show you the port, do the next.
</p>

### *Step 2*
- Use Windows key(start) +  R
- Paste ` SQLServerManager15.msc ` and Enter
- Select ` SQL Server Network Configuration`
- Select your SQL Server Instance
- Right Click in `TCP/IP` and select enable
- Do click again and select properties
- Select IP Addresses tab and go to the end
- If you know what port is free for use write it in `TCP Port`, apply changes and save, leap the next step and go to the end step.

## How to know what Port is free
### *Step 3*
- Use Windows key(start) +  q
- find `cmd` and execute it with admin privileges.
- write `netstat -ano | findstr *PORT*`, replace  *PORT* for a por number, default SQl use 4033 or 4034, try this port
- if dont appear  a process listening in the console you can use it port in the previous step. Otherwise try another port.
- Do the previous step again and use that port in `TCP Port`

## Restart SQL Server
### *Step 4*
- Use Windows key(start) +  R
- Paste ` SQLServerManager15.msc ` and Enter
- Select ` SQL Server Services` and restar `SQL Server and SQL Server Browser`
- all ready, that is your SQL Server Port and you can use step 1 again.
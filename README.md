# sbmd-backup-mysql
<h1>SBMD - Simple Backup MySQL Database</h1>
This is a <strong>free and open source PHP script to Backup MySQL Database</strong>. The script creates the backup of the MySQL tables in SQL format and saves it into a ZIP file on server. The SBMD script can also restore the MySQL tables in your database from the SQL backup stored in ZIP archive.<br>
You can also Download, and Delete the ZIP archives with the SQL backup.
<h3>Features</h3>
- Simple and easy to use interface to Backup and Restore MySQL tables.<br>
- Supports both PDO and MySQLi for accessing MySQL databases in PHP.<br>
- You can select the MySQL tables which to backup.<br>
- The backup of the MySQL tables it is saved into a ZIP archive on server.<br>
- You can Restore, Download, and Delete the ZIP file with backup from server.<br>
- The script can be easily translated and used in other languages, without affecting the code.<br>
- Easily to integrate into a CMS or other PHP project to add the backup MySQL database functionality.
<h4>Requirements</h4>
- PHP 5.4+<br>
- Modern Browser with JavaScript enabled (Mozilla-Firefox, Google-Chrome, Opera, Internet-Explorer 9+).
<h3>Installation</h3>
<ol>
 <li>Copy the script on your server (with all its content).</li>
 <li>Set CHMOD 0755 (or 0777) permissions to the "<span class="sb">backup/</span>" folder on your server (it is used to store the ZIP files with the SQL backup).</li>
 <li>Access the "<span class="sb">sbmd/bkmysql.php</span>" file in your browser, with the address from server; for example: <span class="sbi">http://localhost/sbmd/bkmysql.php</span></li>
 <li>Add your connection data (MySQL server, Username, Password, Database name) to connect to your MySQL database. Then you can backup MySQL tables, and restore, download or delete the backup.</li>
</ol>
<h3>Other Specifications</h3>
&bull; If you want to save the ZIP files in other directory on your server, modify the value of the <span class="sb">$dir</span> variable in the "bkmysql.php" file (line 5).<br><br>
&bull; If you want to use the script in other language, translate the texts from the <span class="sb">lang_en.json</span> file and save it in other "lang_...json" file, with the indice of the language, for example for Chinese save the texts in the "lang_ch.json". The texts in the ".json" file must be stored in valid JSON format. Then, change the value of the <span class="sb">$lang</span> variable in the "bkmysql.php" file (line 4) with the same indice (<span class="sbi">$lang ='ch';</span>).
<h3>Advanced Usage</h3>
- If you want to use the <span class="sb">backupmysql</span> class into a CMS or other PHP project, include the <span class="sb">backupmysql.class.php</span> file in your project.<br>
- The object instance of the backupmysql class requires two arguments: the indice of the language (used for the "lang_...json" file; default "en"), and the directory name where the backup files are saved (default "backup/").<br>
Example:<br>
<pre>
include 'backupmysql.class.php';
$obj = new backupmysql('en', 'backup/');
</pre>
-  Then you can use these methods:
<ul>
 <li><span class="sb">setMysql($conn_data)</span> - store connection data in the <span class="sb">$mysql</span> property. Receives array with: <span class="sbi">['host'=>'mysql-server', 'user'=>'user-name', 'pass'=>'password', 'dbname'=>database-name]</span>.</li>
 <li><span class="sb">getTables()</span> - returns array with all the tables in database (database name stored in: <span class="sbi">mysql['dbname']</span> property).</li>
 <li><span class="sb">getListTables()</span> - returns array: <span class="sb">['f'=>'form', 'er'='error message']</span>. The "f" key contains a form with checkboxes with the tables returned by the <span class="sbi">getTables()</span> method.</li>
 <li><span class="sb">getSqlBackup($tables)</span> - returns a SQL string format with the backup of the tables from the <span class="sbi">$tables</span> parameter (array with the tables name to backup).</li>
 <li><span class="sb">saveBkZip($tables)</span> - creates ZIP archive with the SQL backup returned by the <span class="sbi">getSqlBackup($tables)</span> method, and saves the archive in the directory from the <span class="sbi">$dir</span> property. Receives array with the tables name to backup.</li>
 <li><span class="sb">getListZip()</span> - returns form with radio-buttons with all the ZIP archives stored in the folder added the <span class="sbi">$dir</span> property.</li>
 <li><span class="sb">restore($zp)</span> - restores the backup tables. The <span class="sbi">$zp</span> argument contains the name of the ZIP archive with the SQL file (stored in the folder added in the <span class="sbi">$dir</span> property).</li>
 <li><span class="sb">getZipFile($zip)</span> - returns the ZIP file for download, from the folder added in <span class="sbi">$dir</span> property. Receives the name of the ".zip" file.</li>
 <li><span class="sb">delFile($file)</span> - deletes the <span class="sbi">$file</span> from the folder added in <span class="sbi">$dir</span> property.</li>
</ul>
- By default, the backupmysql class uses MySQLi to connect to database. If the MySQLi extension is not available, the class will try to use PDO. If you want to make the default mode to PDO, set the <span class="sb">"pdo"</span> value to the <span class="sb">$conn_mod</span> property, in the <span class="sbi">backupmysql.class.php</span> file (line 114).
<br><hr>
 &bull; Home Page: <a href="http://coursesweb.net/php-mysql/simple-backup-mysql-database_s2" title="SBMD - Simple Backup MySQL Database">http://coursesweb.net/php-mysql/simple-backup-mysql-database_s2</a><br><br>
 - <span class="sbi">This script is Free, and Open Source. You can use, modify and publish it freely.<br>
"# respaldo_restaurar_bd" 

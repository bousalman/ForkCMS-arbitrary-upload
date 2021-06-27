# Fork CMS 5.9.2 arbitrary file upload vulnerability

the contents management system web application FORK CMS version 5.9.2 is prone to arbitrary file upload vulnerability. This vulnerability effects the forkcms application and the underlining Web server since attackers can achieve a remote code execution.

## How
Authenticated users can upload a new theme thru the Themes panel in the settings tab, it's possible to craft a custom zip file hosting a malicious code and .htaccess file to create arbitrary files on the Themes folder. .htaccess file will instruct the web server to allow running a new file type under the web application context. Successful attack will result an entire Web server compromise specially in shared hosting and also database access since the attackers can read/access the config files.

## Mitigation
To mitigate this issue quickly developers should sanitize files while uploading themes, to disallow the .htaccess file.

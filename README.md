cordova-simplefilemanagement
============================

This makes file/directory creation-deletion, red/write. download very simple.
you will need the cordova file plugins:

```
$ phonegap local plugin add https://git-wip-us.apache.org/repos/asf/cordova-plugin-file.git
$ phonegap local plugin add https://git-wip-us.apache.org/repos/asf/cordova-plugin-file-transfer.git
```

Here are simple examples on how to file/directory creation-deletion, red/write. download:


<html>
   
    <body>
       
        <script type="text/javascript" src="cordova.js"></script>
        
        
        <script type="text/javascript" src="painlessfs.js"></script>
        <script type="text/javascript">
           
           var start_examples =	function(){
		

				//
				//CREATE A DIRECTORY RECURSEVLY
				var a = new DirManager(); // Initialize a Folder manager
		        a.create_r('folder_a/folder_b',Log('complete/jorge'));

				//LIST A DIRECTORY 
				a.list('cosa', Log('List'));

		        //REMOVE A DIRECTORY RECURSEVLY
		        a.remove('folder_a/folder_b',Log('complete delte'), Log('delete fail'));

				//
				//FILES MANAGEMENT:
				//
		        var b = new FileManager();
		        // create an empty  FILE (simialr unix touch command), directory will be created recursevly if it doesnt exist
		        b.load_file('dira/dirb/dirc','demofile.txt',Log('file created'),Log('something went wrong'));
		        
		        // WRITE TO A FILE
		        b.write_file('dira/dirb/dirc/dird','demofile_2.txt','this is demo content',Log('wrote sucessful!'));

		        // READ A FILE
		        b.read_file('dira/dirb/dirc/dird','demofile_2.txt',Log('file contents: '),Log('something went wrong'));
		        
		        // download a file from a remote location and store it localy
		        b.download_file('http://www.greylock.com/teams/42-Josh-Elman','filder_a/dwonloads_folder/','target_name.html',Log('downloaded sucess'));
		       

				
		}

		//LOAD START EXAMPLES WHEN DOCUMENT IS READY
            document.addEventListener(
                'deviceready', 
                start_examples, 
                false
            );

             

        </script>
    </body>
</html>






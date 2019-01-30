node()
{
    try
		{
	
		def banchName ="${branchname}"
		print "${branchname}"
	    if (branchName.equals('develop')) 
			{
			 print "Building the develop branch "
			/***Calling the function developBranch if develop branch is being built***/
			 developBranch()
			}
		
	    else if (banchName == 'master') 
			{
			 print "Building the master branch "
			/***Calling the function masterBranch if master branch is being built***/
			 masterBranch()
			}
	    else  
			{
			 print "Building the feature branch"
			/***Calling the function featureBranch if feature branch is being built***/
			 featureBranch()
			}
		
		} 
	catch(e) 
		{
		currentBuild.result = "FAILED"	
		//notifyBuild(currentBuild.result)
		throw(e)
		} 
    finally 
		{
		print "echo final block"
		}	
	}
	
	
/***Function definition for masterBranch***/	
/***Build using maven, run the tests, push it to artifactory with jenkins build number as the version***/ 	

def masterBranch() 
	{
	    
	    	/***Download code from stash***/  
    stage'Download Code'
		download_stash_code()
	
	/***Perform maven clean***/ 
    stage'Clean'
	//	clean()
	
	/***Perform maven mUnit tests***/     	
	stage'mUnit Tests'
		//munit_tests()
		
	/***SoapUI Integration Tests***/ 
	stage'SoupUI Integration Testing'	
	//	download_soapUi_code()
	
	/***Publish the coverage report and junit reports***/			
	stage'Publish Reports'
	//	publish_junit()
	//	publish_html()
	
	/***Create zip package from the source code and push it to artifactory***/
	stage'Package & Publish'
	//	package_publish_artifactory_master()
	}
def developBranch() 
	{
	
	/***Download code from stash***/  
    stage'Download code'
		download_stash_code()
	
	/***Perform maven clean***/ 	        
    stage'Clean'
		//clean()
	
	/***Perform maven mUnit tests***/    	
	stage'mUnit Tests'
		//munit_tests()
	
	/***Publish the coverage report and junit reports***/  
	stage'Publish Reports'
		//publish_junit()
		//publish_html()
	
	/***Create zip package from the source code and push it to artifactory***/		  
    stage'Package & Publish'
	//	package_publish_artifactory()
   }
   
   
   
   
   def featureBranch() 
	{
	
	/***Download code from stash***/  
    stage'Download Code'
		download_stash_code()
	
	/***Perform maven clean***/ 
    stage'Clean'
	//	clean()
	
	/***Perform maven mUnit tests***/     	
	stage'mUnit Tests'
		//munit_tests()
		
	/***SoapUI Integration Tests***/ 
	stage'SoupUI Integration Testing'	
	//	download_soapUi_code()
	
	/***Publish the coverage report and junit reports***/			
	stage'Publish Reports'
	//	publish_junit()
	//	publish_html()
	
	/***Create zip package from the source code and push it to artifactory***/
	stage'Package & Publish'
	//	package_publish_artifactory_master()
		
	}


def download_stash_code()
	{
		print "echo clone stash for develop branch"
		//checkout scm
	}

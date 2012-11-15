## See the <a href="https://github.com/Bioconductor/githubCribsheet/wiki/">wiki</a> for notes and tips for using github with Biocondcutor
<!--
Every bioc/fhcrc project (including this one, the githubCribsheet) is a separate repository maintained under 

   https://github.com/Bioconductor
   
### Create your own project (aka repository, or 'repo'):

 * Register as a user:  https://github.com/signup/free
 * Send an email to pshannon AT fhcrc.org so that I can give you permissions to create your repo under Bioconductor.
 * Go to https://github.com/Bioconductor.  Sign in.
 * Create your new repo by clicking on the leftmost of the three buttons you will find at the top right corner of the page. 
 It has a '+' on it.
 * This takes you to a new page where you will be asked to name your project.
 * On this same page you can edit your repo's <b>README.md</b> which (like this file you are currently reading) records the central documentation for your project.
 * Save your changes to README.md by clicking on the <b>Commit Changes</b> button found at the bottom right corner of the page.

### Setup your computer for git 
  * <code>git config --global user.name  "your.github.account.name"
  * <code>git config --global user.email "you@place.com"</code>
  * configure the <b>credential.helper</b>. Alas, this step differs by operating system because passwords are saved in different ways on osx, linux and windows.   Please get the right instructions for your computer at https://help.github.com/articles/set-up-git
 

### Clone the project onto your own computer

 * cd toSomeDirectoryOfYourChoice
 * <code> git clone https://github.com/Bioconductor/githubCribsheet.git</code> with these results
     * a <b>local repo</b> is created 
     * a <b>working copy</b> is created
     * thus <b>three</b> versions of the code exist

### Using SSH keys
 * If you want to use ssh keys instead of https to connect, see this guide: https://help.github.com/articles/generating-ssh-keys
 * The command to clone the project is then <code>git clone git@github.com:Bioconductor/githubCribsheet.git</code>

### Overview of basic operations

 * Making changes to your <b>working copy</b> propagate them to <b>BOTH</b> of your repos:
    * Add some text to REAMDE.md, whose contents you originall created at the github website
    * git diff README.md will report differences between your <b>local repo</b> and your <b>working copy</b>
    * update the <b>local repo</b>:  
        <code> git commit -m "added one line, modifying my local working copy" README.md</code>
    * update <b>github</b>: 
        <code> git push</code>
    * make sure your <b>local repo</b> and <b>working copy</b> have a record of the update 
      you just did to the <b>github repo</b>:   <code>git pull</code>

  
### Add a user to your project

 * The new user needs a github login id
 * From the project home page, click the <b>Admin</b> button
 * Click the <b>Teams</b> button
 * Click the <b>Owners</b> button
 * Enter the new user's github id

### From SVN to git and back ??

Does this work? Who knows.

I explored git / svn a little last night. It seems there is 'git svn'
(separate from git but widely available), and that steps might be

1. Make a repository on github, e.g., http://github.com/mtmorgan/test

2. clone the svn repository locally

  git svn clone \
      https://hedgehog.fhcrc.org/bioconductor/trunk/madman/Rpacks/graph
	  
This pulls in all the revision history but I think instead it might
make sense to limit that (e.g., to the last time the version was
bumped during a release) by making a directory, initiating a git
repository, fetching a particular revision from svn, and then rebasing
to the current version
	  
    mkdir graph && cd graph
      git svn init \
          https://hedgehog.fhcrc.org/bioconductor/trunk/madman/Rpacks/graph
    git svn fetch -r64680
	git svn rebase
				  
and then I see
				  
	$ git log --oneline
	4aea3d4 The following previously deprecated functions have been made
	b11e47e bumped version numbers after creating 2.10 branch
				  
3. add information about the git repository

    git remote add origin \
	    http://github.com/Bioconductor-mentored/graph.git
		
4. push the svn clone to github

    git push -u origin master
  
this gets us a github repository with a snapshot of our svn; my
handiwork is at
  
    https://github.com/mtmorgan/test
	
We could then git going on all of our revisions and finally...
	
5. When done and ready to send back to Bioconductor's svn tree
	
	git svn dcommit 

-->

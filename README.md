## Notes and tips for using github with Biocondcutor

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
 * <code> git clone git://github.com/Bioconductor/githubCribsheet.git</code> with these results
     * a <b>local repo</b> is created 
     * a <b>working copy</b> is created
     * thus <b>three</b> versions of the code exist
    
### Overview of basic operations

 * Making changes to your <b>working copy</b> propagate them to <b>BOTH</b> of your repos:
    * Add some text to REAMDE.md, whose contents you originall created at the github website
    * git diff README.md will report differences between your <b>local repo</b> and your <b>working copy</b>
    * update the <b>local repo</b>:  
        <code> git commit -m "added one line, modifying my local working copy" README.md</code>
    * update <b>github</b>: 
        <code> git push git@github.com:Bioconductor/githubCribsheet.git</code>
    * make sure your <b>local repo</b> and <b>working copy</b> have a record of the update 
      you just did to the <b>github repo</b>:   <code>git pull</code>

  
### Add a user to your project

 * The new user needs a github login id
 * From the project home page, click the <b>Admin</b> button
 * Click the <b>Teams</b> button
 * Click the <b>Owners</b> button
 * Enter the new user's github id



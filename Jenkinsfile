@Library('mylibrary')_
node('built-in')
{
    stage('Cont Down-Master')
    {
        cicd.newGit("maven")
    }
    stage('Cont Build-Master')
    {
        cicd.newMaven()
    }
    stage('Cont Depl-Master')
    {
        cicd.newDeploy("shareLibrary","172.31.21.34","textapp")
    }
    stage('Cont Test-Master')
    {
        cicd.newGit("FunctionalTesting")
        cicd.executeSelenium("shareLibrary")
    }
    stage('Cont Deliv-Master')
    {
        cicd.newDeploy("shareLibrary","172.31.25.234","prodapp")
    }
}

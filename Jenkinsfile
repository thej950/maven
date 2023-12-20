@Library('thej950Library')_
node('built-in'){
    stage("Download Code"){
          cicd1.newGit("maven")
    }
    stage("Build code"){
        cicd1.newBuild()
    }
    stage("Continues Deploy  into QA servers"){
        cicd3.newDeploy("project1","vagrant","10.10.10.52","testproject1")
    }
    stage("Testing"){
        cicd1.newGit("FunctionalTesting")
        cicd.runSelenium("project1")
    }
    stage("continuos Deploy into production servers"){
        cicd3.newDeploy("project1","vagrant","10.10.10.53","prodproject1")
    }
}

pipeline{
  agent any
//   tools {python "python"}
  
  parameters{
    text(
      name: "pythonFile",
      description: "please enter the name of python file",
      trim: "true"
    )
  }
  stages{
    stage("execute python code"){
      steps{
//         bat 'C:/Users/VAIBHAV/AppData/Local/Programs/Python/Python38/python.exe methodtest.py'
        bat "C:/Users/VAIBHAV/AppData/Local/Programs/Python/Python38/python.exe ${params.name}"
      }
    }
  }
}

pipeline{
  agent any
  stages{
    stage('#1.Checkout'){
      steps{
        git url:'https://github.com/sejalhule03/DOCKER-B2.git', branch: 'main'
      }
    }

     stage('#2.Build the Image'){
      steps{
        bat 'docker build -t mywebsite .'
      }
    }

     stage('#3.Stop all old contianers'){
      steps{
        bat 'docker stop mycont || exit 0'
        bat 'docker rm mycont || exit 0'
      }
    } 
    
    stage('#4.Run the Image - Containeriaze'){
      steps{
        bat 'docker run -d -p 4001:80 --name mycont mywebsite'
      }
    }
  }
}

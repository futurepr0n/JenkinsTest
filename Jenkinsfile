node{
       stage('Preparation') { 
            // for display purposes
            echo 'Download the code from GitHub'
            // Get some code from a GitHub repository
            git 'https://github.com/futurepr0n/JenkinsTest.git'
            // Set up the Python Environment and dependencies         
            discordSend description: "**Build:** " + env.BUILD_TAG + "\n**Starting Test:** Go!", footer: "JenkinsTest", link: env.BUILD_URL, result: currentBuild.currentResult, title: JOB_NAME + " Build #" + BUILD_NUMBER, webhookURL: "https://discordapp.com/api/webhooks/725819926019047525/u2pGRTVXR9yCDzNnzhRgqlN4GiBgMmywTRUuyTagWQG9RmWAyDt6OSHYHWg7ObJlLVj9"
       }
        
        def varsFile = "var_file.txt"
        def content = readFile varsFile
        def lines = content.split("\n")
        for(l in lines){
                String variable = "${l.split(" ")[1].split("=")[0]}"
                String value = l.split(" ")[1].split("=")[1]
                sh ("echo env.$variable = \\\"$value\\\" >> var_to_exp.groovy") 
         }
         load var_to_exp.groovy
}

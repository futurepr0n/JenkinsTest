node{
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

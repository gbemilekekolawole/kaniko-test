// pipeline {
//     agent {
//         kubernetes {
//             // namespace 'your-namespace'
//             // label 'kaniko-agent'
//             // yaml {
//             //     // Pod template for Kaniko
//             //     apiVersion: v1
//             //     kind: Pod
//             //     spec:
//             //       containers:
//             //       - name: kaniko
//             //         image: gcr.io/kaniko-project/executor:latest
//             //         args:
//             //           - --dockerfile=./Dockerfile
//             //           - --destination=gcr.io/your-project/your-image:latest
//             //         volumeMounts:
//             //           - name: source-code
//             //             mountPath: /workspace
//             //       volumes:
//             //         - name: source-code
//             //           persistentVolumeClaim:
//             //             claimName: my-pvc
//             // }
//         }
//     }
//     stages {
//         stage('Build and Push') {
//             steps {
//                 sh 'kubectl get pods -w' // Wait for the Kaniko Pod to be ready
//             }
//         }
//     }
// }

podTemplate (inheritFrom: 'kaniko'){
    node(POD_LABEL) {

        container('kaniko') {
            sh '/kaniko/executor --dockerfile=Dockerfile --context=dir://. --destination=uk-london-1.ocir.io/lrt72gqbkttc/agenttest:1.0'
        }

    }

}

podTemplate(yaml: """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: fedora32
    image: fedora:32
    command:
    - cat
    tty: true
"""
) {
    node(POD_LABEL) {
      container("fedora32") {
        sh "mkdir -p /root/test"
      }
    }
}

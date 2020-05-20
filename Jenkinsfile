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
    volumeMounts:
    - name: workdir
      mountPath: /root/test
  initContainers:
  - name: busybox
    image: busybox
    command:
    - sh
    args:
    - -c
    - echo "Hello world" > /work-dir/hello_world
    volumeMounts:
    - name: workdir
      mountPath: /work-dir
  volumes:
  - name: workdir
    emptyDir: {}
"""
) {
    node(POD_LABEL) {
      container("fedora32") {
        sh "ls -al /root/test"
      }
    }
}

# Class OpenShift Demo for DO180-Auburn

1. Launch app using github repo
   - oc new-app [--name \<optional name\>] \<git repo.git\>
   - also:
     - oc new-app {image name} [... other options]
     - oc new-app --image={some registry} [... other options]
     - oc new-app --template={template name} [... other options]    
2. Troubleshoot errors (private repo)
   - oc status
   - oc status --suggest
   - oc logs -f \<pod name\> [\<container name\>]
     - if more than one container in pod, must specify pod name
   - oc describe pod \<pod name\>
3. Make repo public then restart build
   - oc start-build \<build config name\>
   - oc get bc
4. Monitor app and pods for status of app (waiting for crash loop in pod status)
   - oc get pods
   - oc status
   - oc get all
5. Troubleshoot build issues again (rename to app.py)
6. Re-run build command
   - oc start-build ...
7. Demonstrate port forwarding to container
   - oc port-forward \<pod name\> \<local port\>:\<remote port\>
   - view information about pods/containers to determine correct port
8. Create route
   - view information about pods/containers to determine correct port
   - oc expose svc/\<service name\>
9. View route info
   - oc describe route
10. Connect in browser
11. Other commands to demonstrate
    - oc edit \<resource\> (open resource file in editor)
    - oc exec -h (execute command in container)
    - oc get projects
    - oc project \<project name\> (change projects)
    - oc delete all --selector app=\<app name\> (clear out everything with specific label)
    - oc get builds (view all builds, including failed)
    - oc logs build/\<app name-build number\>

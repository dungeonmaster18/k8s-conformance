# OpenEBS
Containerized Open Source Storage for Containers

## How to Reproduce

Install the quickstart from the guided template http://openebs.readthedocs.io/en/latest/install/on_premise_solutions.html 

Run the conformance test following the official guide:
```
$ curl -L https://raw.githubusercontent.com/cncf/k8s-conformance/master/sonobuoy-conformance.yaml | kubectl apply -f -

$ kubectl logs -f sonobuoy -n sonobuoy

# wait for the message below in the log
# no-exit was specified, sonobuoy is now blocking
```

Get the results:
```
$ kubectl cp sonobuoy:/tmp/sonobuoy/ ./results -n sonobuoy
$ tar xf results/*.tar.gz
```

Then grab `plugins/e2e/results/{e2e.log,junit_01.xml,nethealth.txt}`, add them to this PR.

Run 'kubectl version > version.txt' to get the version info, and add it to this PR.


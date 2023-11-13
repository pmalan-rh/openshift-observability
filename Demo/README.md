
Quarkus Super Heroes Demo deployment:

oc apply -f https://raw.githubusercontent.com/quarkusio/quarkus-super-heroes/main/deploy/k8s/java17-openshift.yml

change all http toutes to https, and allow http.

Make sure all imageStreams are valid, and if not search quay.io for correct image.


# Test-mirroring-github-codecommit
Test Mirroring between github and code commit 

tag v2.0.0
Tag v3.0.0


https://parisnakitakejser.medium.com/sync-your-aws-codecommit-repository-to-your-github-repository-for-public-code-sharing-or-private-dacd9dd5d592
First, we need to clone our primary repository
```
git clone --mirror git@github.com:minashafikthabet/Test-mirroring-github-codecommit.git
```
then you need to go into your repo folder and add the new remote repository.
```
cd Test-mirroring-github-codecommit.git
git remote add --mirror=fetch secondary codecommit::us-east-1://jcrew-temp@rackspace-mirror-poc
```
Now you are ready to fetch out on your origin (primary) remote repository, and after it pushes everything to your secondary remote repository.
```
git fetch origin
git push secondary --all
```
push Tags since it's not pushed with --all ( I Don't knw why? )
```
git push secondary --tags
```

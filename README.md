```
git clone https://github.com/kurtov/repoA.git repoA
cd repoA
touch A.txt
touch B.txt
git add .
git commit -m "init commit"
git branch branch1
git clone -l . ../repoB
cd ../repoB
git checkout branch1
touch C.txt
git add .
git commit -m "add C.txt"
git push
cd ../repoA
git checkout branch1
echo "hello world from repoA" >> C.txt
git add .
git commit -m "modify C.txt from repoA"
cd ../repoB 
echo "hello world from repoB" >> C.txt
git add .
git commit -m "modify C.txt from repoB"
git fetch
git merge
echo "hello world" > C.txt
git add .
git commit -m "resolve conflicg"
cd ../repoA
git remote add repoB ../repoB
git fetch repoB
git merge repoB/branch1
git push -u origin master
git push -u origin branch1
cd ../repoB
git remote add github https://github.com/kurtov/repoB.git
git push -u github master
git push -u github branch1
```

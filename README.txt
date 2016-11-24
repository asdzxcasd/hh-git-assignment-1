# 01
git init ./A
# 02
cd ./A
touch A B
git add A B
git commit -m "1st commit"
# 03
git branch branch1
# 04
cd ../
git clone ./A ./B
# 05
cd B
git checkout -b branch1 origin/branch1
touch C
git add C
git commit -m "2nd commit"
# 06
git push origin branch1
# 07
cd ../A
git checkout branch1
echo "line #1" > C
git add C
git commit -m "modified line #1 in file C"
# 08
cd ../B
echo "line #1 version2" > C
git add C
git commit -m "modified line #1 in file C"
# 09
git fetch origin
# 10
git merge
echo "line #1 merged" > C
git commit -a -m "merge conflicts"
# 11
cd ../A
git remote add repoB ../B
# 12
git pull repoB branch1

1.	Клонирование репозитория и знакомство с его структурой
git clone https://github.com/smartiqaorg/geometric_lib.git
cd geometric_lib/
git checkout develop
git checkout release
git log --all --pretty=oneline --graph
2.	Работа с веткой develop
git checkout main
git merge develop --no-ff
git log --all --pretty=oneline --graph
git reset --hard HEAD^
git log --all --pretty=oneline --graph
git merge develop --ff
git log --all --pretty=oneline --graph
3.	Работа с веткой release
git config merge.conflictstyle diff3
git config --global merge.tool meld
git checkout release
git rebase -i main
В редакторе:
pick 438b89a L-05: Add user agreement
squash 86edb1c L-05: Update Docs. Add user agreement info
git config --global mergetool.meld.path /c/Python26/meld-1.5.2/bin/meld
git mergetool
git rebase --continue
git log --all --pretty=oneline --graph
git checkout main 
git merge release --ff
git log --pretty=oneline --graph

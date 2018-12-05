# git reset
git reset 分為hard、soft、mixed三種<br>
在討論reset的三種方式之前，先來以圖示介紹git從改變資料到commit這段期間做了什麼<br><br>
1. Working Tree (工作目錄):  Git管理的實體資料夾，也就是我們實際操作的資料夾(檔案)<br>
2. Index (系統索引):  存放一堆需要被commit的(異動)文件內容集合，把檔案加入索引稱 Stage 或 Cache。<br>
3. Repository (檔案庫):  是Git存放檔案的位置，許多commit 版本紀錄於此。<br><br>
1. 剛開始 working tree 、 index 與 repository(HEAD)資料內容都是一致的<br>
![image]()</br></br>
2. 當實體檔案被異動後，此時 working tree 資料內容就會跟 index 及 repository(HEAD)的不一致，而Git知道該那些檔案(Tracked File)被異動過，直接將檔案狀態會調整為 modified (Unstaged files)。<br>
![image]()</br></br>
3. 當我們執行 git add 後，會將這些異動檔案內容加入 index 中 (Staged files)，所以此時working tree跟index資料內容是一致的，但他們與repository(HEAD)資料內容不一致。</br>
![image]()</br></br>
4. 接著執行 git commit 後，將Git索引中所有異動檔案內容提交至 Repository 中，建立出新的 commit 結點(HEAD)後，資料內容又會於 working tree 、 index 與 repository(HEAD) 中保持一致。</br>
![image]()</br></br>

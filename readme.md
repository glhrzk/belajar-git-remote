catatan pribadi yang akan dibaca kembali nantinya
yang di dapat dari hasil belajar di Youtube PZN

<b>list command Git dasar:</b>
- git config --list --show-origin (digunakan untuk melihat Seluruh Configuration)
- git status (digunakan untuk melihat perubahan yang terjadi dalam git, baik itu penambahan untrack dll)
- git add (digunakan untuk menambahkan file dari working directory ke stageddirectory)
- git commit -m (digunakan untuk melakukan commit atau menyimpan file secara permanen ke repository beserta message/pesan)
- git clean -f (digunakan untuk menghapus / undo terhadap file yang baru dibuat)
- git restore (digunakan untuk mengundo file yang sudah di edit, dengan catatan file tersebut masih didalam working directory, git restore pun bisa digunakan ketika file di hapus / membatalkan pengahapusan yang berada dalam working directory)
- git restore --staged (digunakan untuk mengundo file yang sudah di edit, dengan catatan file tersebut sudah didalam staged directory)
- git log (digunakan untuk melihat log commit)
- git log --oneline (digunakan untuk melihat log commit lebih rapih secara satu baris)
- git log --oneline --graph (digunakan untuk melihat log commit lebih rapih secara satu baris, dan menampilkan relasi dengan commit sebelumnya)
- git show idhash (digunakan untuk melihat detail commit berdasarkan hash)
- git diff hash1 hash1 (digunakan untuk melihat hasil akhir commit dan menampilkan hasil akhir dari commit tersebut)
- git difftool hash1 hash1 (digunakan untuk melihat hasil akhir commit dan menampilkan hasil akhir dari commit tersebut, dan dibuka melalui visutal studio code editor)
- git reset --mode idhash (digunakan untuk berpindah commit dan melakukan reset (tergantung dengan mode), ke sebelum atau sesudah. soft / mixed / hard )
(soft = merubah di staging index, mixed = merubah di working directory, hard = merubah di repository)
- git commit --amend -m "isi mesage" (digunakan untuk mengupdate commit sebelumnya, jika kita terlupa)
- git checkout idhash -- namafile (digunakan untuk melihat perubahan yang terjadi pada file commit tersebut/sebelumnya, staged)
- git checkout idhash (digunakan untuk berpindah commit, berbeda dengan git reset, git commit tidak menghapus (hanya berpindah commit 1 ke commit lain))
- git revert idhash (digunakan untuk membatalkan perubahan pada commit sebelumnya dengan cara membuat commit BARU dengan file/script commit sebelumnya)
- git blame namafile (digunakan untuk melihat siapa yang melakukan perubahan/update dan mengcomit file tersebut)
- git config --global alias.ko "commit" (digunakan untuk membuat alias, jika perintah menggunakan space maka beri tanda petik 2)

list command Git branch: 
- git branch --list (menampilkan seluruh branch)
- git branch namaBranchBaru (membuat branch baru dari branch saat ini (this->branch))
- git switch namaBranchBaru (pindah branch)
- git checkout namaBranchBaru (pindah branch)
- git branch -m namaBranchBaru (untuk mengganti nama branch saat ini (this->branch))
- git branch --delete namaBranch (untuk menghapus branch (tidak boleh aktif pada branch saat ini))
- git branch -d namaBranch (untuk menghapus branch (tidak boleh aktif pada branch saat ini))
- git merge namaBranch (untuk merge branch tujuan dengan branch saat ini (this->branch))
(jika terjadi conflic pada saat merge maka kita harus mengeceknya secara satu persatu lalu me merge kan kembali)
- git cherry-pick idhash (untuk merge hanya satu commit (bukan seluruh branch), dengan branch saat ini (this->branch))
- git tag codetag idhash (untuk membuat referense terhadap snapshot/hasil comit)
- git tag -d tagname (untuk menghapus tag)
- git stash push -m 'message stash' (untuk menyimpan perubahan sementara working directory dan staging index)
- git stash apply stashid (untuk menerapkan perubahan ke working directory)
- git stash clear (untuk menghapus stash)
- git rebase tujuanBranch (untuk melakukan rebase, sebenernya sama dengan merger tapi rebase dibuat 1 timeline, dan penggunaannya berbeda, kita harus berada di branch yang ingin di copy, rebase berarti hanya melakukan rebase di branchnya saja (this->branch), commit di master tetap tidak berubah, kita perlu melakukan merger kembali)
- git merge --squash namaBranch (tidak beda jauh dengan merge hasil dari rebase, tetapi menjadikan semua commit dari branch yang merebase sebelumnya menjadi 1 commit alias di group, tetapi tidak secara otomatis di commit melaikan disimpan ke staging index terlebih dahulu)


list command Git Remote:
- ssh-keygen (digunakan untuk generate ssh)
- ssh -T git@github.com (untuk test koneksi login ssh ke github kita)
- git remote add namaRemote urlsshgit (digunakan untuk menambahkan remote repository git server)
- git remote get-url namaRemote (digunakan untuk melihat url remote repository git server)
- git remote rm namaRemote (digunakan untuk menghapus remote repository git server)
- git push namaRemote namaBranch (digunakan untuk mengsinkron/mengupload branch ke git server)
- git push namaRemote namaBranch:namaAlias (fungsinya sama seperti sebelumnya, tetapi namaAlias akan digunakan/rename ke repository git server)
- git push namaRemote --all (untuk push semua branch, nama branch akan mengikuti defaultnya)
- git push --delete namaRemote namaBranch (untuk menghapus branch di repository)
- git clone urlsshgit namaFolder (digunakan untuk mengclone atau mendownload project yang ada di repository server ke local, default branch utama/master)
- git branch -r (untuk melihat branch yang ada di remote repository git server)
- git fetch namaRemote 
- git fetch namaRemote namaBranch (untuk mengupdate fetch remote keseluruhan atau by branch, perlu diingat bahwa yang di update adalah branch REMOTE yang ada di local hasil clone/dsb, bukan branch local,jadi tidak akan ada perubahan di branch local kita sebelum di merge,)
- git diff branchLocal branchRemote (untuk melihat perbedaan dari hasil fetch diatas)
- git pull namaRemote
- git pull namaRemote namaBranch (untuk mengupdate local branch ke branch repository, sama saja seperti melakukan fetch + merge secara berurutan)
- git push namaRemote namaTag (mengirim tag ke remote repository secara satu persatu)
- git push namaRemote --tags (mengirim semua tag ke remote repository)
- git fetch namaRemote namaTag (mengambil tag dari remote repository)
- git fetch namaRemote (juga bisa digunakan untuk mengambil semua tag di repository)
- git push --delete namaRemote namaTag (menghapus tag di repository)
- pull request ( ketika kita membuat branch baru dari branch utama dan membuat fitur dari branch baru tersebut, ketika fitur tersebut ingin digabungkan dengan branch utama maka kita pull request, sama saja dengan merge, tetapi dilakukan di sisi server dan lebih mudah untuk me review )
- git merge namaRemote namaBranch (untuk merge branch dari remote ke local)
- git submodule add -urlrepo -namaFolder (digunakan untuk menambahkan modul berupa repository (nested repo))
- git submodule update --remote namaFolder (update submodule tertentu)
- git submodule update --remote (update semua submodule) 
- git submodule init (untuk mengaktifkan submodule pada clone project, karena defaultnya tidak aktif dan tidak mendownloadnya, maka lakukan submodule update untuk downloadnya)
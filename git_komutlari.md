# Git Komutları

- > git config --global user.name "Omer Apaydin"
- > git config --global user.email omerapaydin90@gmail.com

- > git status // Git kontrolü
- > git init // Projeye git ekler
- > rm -rf .git // Projeden git'i siler
- > git add test1.txt // Seçilen dosyayı staging e ekler
- > git rm --cached test1.txt // Seçilen dosyayı staging alanından çıkarır
- > git add . // Tüm dosyaları staging ekler
- > git restore test1.txt // Seçilen dosyayı stagingden önceye çevirir
- > git commit -m "Git mesajı" // Commit yapar
- > git log // Yapılan commitleri listeler
- > git branch // Hangi branchte olduğunu gösterir
- > git branch chapter2 // Yeni branch oluşturur
- > git switch chapter2 // Seçilen branche girer
- > git merge chapter2 // Chapter2 yi main ile birleştirdi

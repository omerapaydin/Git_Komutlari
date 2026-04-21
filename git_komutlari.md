# Git Komutları

- Git - Version Control System (VCS)

- Dağıtık yapıda çalışan, dosya ve kod değişikliklerini zaman içinde izlemeyi, yönetmeyi ve geri almayı sağlayan bir versiyon kontrol sistemidir.

1. Working Directory → Kod üzerinde çalıştığın yer
2. Staging Area → Commit’e hazırlık alanı
3. Repository (Git history) → Commitlerin kaydedildiği yer

## git config

- Bu iki komutu yazmamızın sebebi, Git’e “bu commitleri kim yapıyor?” bilgisini vermektir
- Takım projelerinde kim neyi yaptı net görünür

* > git config --global user.name "Omer Apaydin"
* > git config --global user.email omerapaydin90@gmail.com

## Projeye Git eklemek

- > git status // Working directory ve staging area’daki değişikliklerin mevcut durumunu gösterir.
- > git init // Bulunulan dizini bir Git repository’sine dönüştürerek .git klasörünü oluşturur.
- > rm -rf .git // Repository’ye ait tüm Git geçmişini ve yapılandırmasını silerek projeyi version control dışına çıkarır.

## Staging Area

- Working directory’de yapılan değişikliklerin commit’e gönderilmeden önce seçilip hazırlandığı ara katmandır (index)

- > git add test1.txt // Belirtilen dosyadaki değişiklikleri staging alanına ekler.
- > git add . // Bulunulan dizindeki tüm değişiklikleri staging area’ya ekler.
- > git restore test1.txt // Working directory’deki değişiklikleri son commit (veya staging) durumuna geri alır.
- > git rm --cached test1.txt // Seçilen dosyayı staging alanından çıkarır

## Commit

- Staging area’daki değişikliklerin, bir mesaj (commit message) ile birlikte repository’nin versiyon geçmişine eklenmesidir.

- > git commit -m "Git mesajı" // Commit yapar
- > git log // Yapılan commitleri listeler

## Branch (Dal)

- Bir repository içinde, ana kodu etkilemeden farklı özelliklerin veya değişikliklerin bağımsız olarak geliştirildiği paralel geliştirme hattıdır. Kısaca aynı projenin kopyası ama ayrı bir çalışma hattı

- > git branch // Hangi branchte olduğunu gösterir
- > git branch chapter2 // Yeni branch oluşturur
- > git switch chapter2 // Seçilen branche girer
- > git merge chapter2 // Chapter2 yi main ile birleştirdi

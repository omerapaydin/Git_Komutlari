# Git Komutları

- Git - Version Control System (VCS)

- Dağıtık yapıda çalışan, dosya ve kod değişikliklerini zaman içinde izlemeyi, yönetmeyi ve geri almayı sağlayan bir versiyon kontrol sistemidir.

1. Working Directory → Kod üzerinde çalıştığın yer
2. Staging Area → Commit’e hazırlık alanı
3. Repository (Git history) → Commitlerin kaydedildiği yer

---

## git config

- Bu iki komutu yazmamızın sebebi, Git’e “bu commitleri kim yapıyor?” bilgisini vermektir
- Takım projelerinde kim neyi yaptı net görünür

* > git config --global user.name "Omer Apaydin"
* > git config --global user.email omerapaydin90@gmail.com

---

## Projeye Git eklemek

- > git status // Working directory ve staging area’daki değişikliklerin mevcut durumunu gösterir.
- > git init // Bulunulan dizini bir Git repository’sine dönüştürerek .git klasörünü oluşturur.
- > rm -rf .git // Repository’ye ait tüm Git geçmişini ve yapılandırmasını silerek projeyi version control dışına çıkarır.

---

## Staging Area

- Working directory’de yapılan değişikliklerin commit’e gönderilmeden önce seçilip hazırlandığı ara katmandır (index)

- > git add test1.txt // Belirtilen dosyadaki değişiklikleri staging alanına ekler.
- > git add . // Bulunulan dizindeki tüm değişiklikleri staging area’ya ekler.
- > git restore test1.txt // Working directory’deki değişiklikleri son commit (veya staging) durumuna geri alır.
- > git rm --cached test1.txt // Seçilen dosyayı staging alanından çıkarır

---

## Commit

- Staging area’daki değişikliklerin, bir mesaj (commit message) ile birlikte repository’nin versiyon geçmişine eklenmesidir.

- > git commit -m "Git mesajı" // Commit yapar
- > git log // Yapılan commitleri listeler

---

## Branch (Dal)

- Bir repository içinde, ana kodu etkilemeden farklı özelliklerin veya değişikliklerin bağımsız olarak geliştirildiği paralel geliştirme hattıdır. Kısaca aynı projenin kopyası ama ayrı bir çalışma hattı

- > git branch // Mevcut repository’deki tüm branch’leri listeler ve aktif branch’i gösterir.
- > git branch chapter2 // chapter2 adında yeni bir branch oluşturur.
- > git switch chapter2 // Seçilen branche girer

---

## Merge

- Farklı branch’lerde (dallar) yapılan değişiklikleri birleştirmek demektir.

- > git merge chapter2 // Chapter2 yi main ile birleştirdi

### Conflict (çatışma) konusu

- Eğer aynı satırları iki branch’te farklı değiştirdiysen:
  - Git “hangisi doğru?” diye sorar
  - buna merge conflict denir
- Sen de manuel düzeltirsin.

---

## Commitler Arası Gezmek

- > git checkout {gidilecek commit id} // Artık bir branch’te değilsin. Sadece geçmişte bir noktaya bakıyorsun

---

## Reset

- Reset, commit geçmişini geri sarar.
- > git reset --hard {CommitId} // Son commit’i tamamen siler. Dosyaları da eski haline getirir

- A --- B --- C (HEAD)
- > git reset --hard B // C commit’i yok olur

---

## Revert

- Revert, commit’i silmez. Onun etkisini tersine çeviren yeni bir commit oluşturur
- > git revert {CommitId}

- A --- B --- C (HEAD)
- > git revert C // A --- B --- C --- D
                                ↑
                      D = C’yi geri alan commit

* Push ettiysen → revert kullan
* Local’deysen → reset kullanabilirsin

---

## Stash

- Çalışıyorsun ama branch değiştireceksin ya da acil başka işe geçmen lazım: Commit atmak istemiyorsun ama yaptığın değişiklikler de kaybolmasın.

- > git stash // Değişiklikleri gizli bir yere alır. Çalışma alanın temizlenir
- > git stash apply // Değişiklikleri geri getirir (stash silinmez)
- > git stash pop // Geri getirir + stash’i siler

---

## Bilgisayarındaki projeyi uzaktaki bir repo’ya (örn. GitHub) bağlamak.

- > git remote add origin https://github.com/kullanici/proje.git // Link GitHub’daki repo’nun adresidir. Github'da Yeni repo oluşturulur. Adres kopyalanır

- > git push -u origin main // Artık projeni GitHub’a gönderebilirsin

---

## Git Push

- Local (senin bilgisayarındaki) commit’leri remote repo’ya (örn. GitHub) göndermek için kullanılır.
- > git push -u origin main // Bu komutu bir kez çalıştırdıktan sonra
- > git push // Artık yazman yeterli

- Eğer remote’ta senden farklı commit varsa: push reddedilir. Önce:
- > git pull // yapman gerekir

---

## Git Fetch

- > git fetch origin

- Sadece indirir (güvenli)
- Remote’taki değişiklikleri indirir
- Ama senin local branch’ine dokunmaz
- “Ne değişmiş?” diye bakarsın ama projeni bozmaz

---

## Git Pull

- > git pull origin main
- Hem indirir. Hem senin branch’inle birleştirir

---

- git fetch → “Ne var ne yok bakayım”
- git pull → “Getir ve projeye uygula”

# SCROLL DOWN FOR ENGLISH

# Merhaba arkadaşlar bugün yine Hemi Network node'umun durduğunu görünce kafam attı ve restart scripti yazdım, sonra dedimki bunu arkadaşlarımla da paylaşmalıyım (bir damla gözyaşı pıt'lı gülen surat emojisi) Böylelikle bu repoda sizinle Hemi Network node için oto-restart kurulumunu paylaşacağım.

![image](https://github.com/user-attachments/assets/1ba22765-17c1-4fd8-a651-0e32e800e379)


Öncelikle, ihtimal vermiyorum ama eğer hemi node'unuz çalışıyorsa durdurun ve aşağıdaki adımlarla başlayın.

1) ilk olarak hemi network'ün bulunduğu dizine bir "restart_hemi.sh" dosyası oluşturalım.


2) ``` nano restart_hemi.sh ``` komutu ile scriptin içine girelim.
   
3) Ctrl + O (kaydet) ile kaydedelim ve Ctrl + X (kapat) ile çıkalım.
Scriptimizin içi boş, ama doldursak bile bu halde bu dosyayı çalıştıramayacağız. 

4) Öncelikle dosyanın izinlerini düzenlememiz gerekiyor ki dosya çalıştırılabilir olsun.

``` sudo chmod +x restart_hemi.sh ``` Bu komut ile bu script dosyasına kendi kullanıcımız için çalıştırma izni verdik.

5) Şimdi scriptimizi "nano" ile tekrar yukarıdaki gibi açıp, içerisine aşağıdaki kodları yapıştıracağız. Ardından ctrl +x, y, enter tuşlarına bu sırayla basarak script dosyasını kaydedip dosyadan çıkış yapalım.

```
#!/bin/bash

restart_count=0
restart_log="restart_log.txt"

while true; do
    # Start the application
    ./popmd

    # Increment the restart count and write to the log file
    ((restart_count++))
    echo "Restart $restart_count at $(date)" >> $restart_log

    # Uygulama çökerse veya durursa, döngü yeniden başlar
    echo "Uygulama durdu. 5 saniye sonra yeniden başlatılacak..."
    sleep 5
done
```
6) Herşey hazır ``` ./restart_hemi.sh ``` ile scriptimizi çalıştıralım.
   

7) Eğer  ``` bash: ./restart_hemi.sh: Permission denied ``` hatası alırsanız, tekrardan ``` sudo chmod +x restart_hemi.sh ``` komutunu çalıştırın ve Betiği tekrar çalıştırın: ``` ./restart_hemi.sh ```
   

8) Eğer  ``` bash: ./restart_hemi.sh: /bin/bash^M: bad interpreter: Text file busy ``` hatası alırsanız, aşağıdaki komutla dos2unix kurun
    
   
``` sudo apt-get install dos2unix ``` 


9) Ardından şu komutla restart_hemi.sh dosyasını Unix formatına çevirin:
    
``` dos2unix restart_hemi.sh ```


10) Betiği tekrar çalıştırın:
    
``` ./restart_hemi.sh ```

# Hepsi Bu kadar! Kendinize İyi Bakın! Repoyu yıldızlamayı ve arkadaşlarınızla paylaşmayı unutmayın!

# Bu tarz repolar için [Github profilimi](https://github.com/geocmsk) ve [ X hesabımı](https://x.com/cwitchking) takip ederseniz çok mutlu ve motive olurum.



# ENGLISH VERSION

# Hello friends today when I saw that my Hemi Network node stopped again, I got mad and wrote a restart script, then I said I should share this with my friends (smiley face with a teardrop emoji) So I will share the auto-restart setup for Hemi Network node with you in this repo.

![image](https://github.com/user-attachments/assets/1ba22765-17c1-4fd8-a651-0e32e800e379)

First of all, I don't think it's possible, but if your hemi node is running, stop it and start with the steps below.

1) First, let's create a "restart_hemi.sh" file in the directory where the hemi network is located.

2) Let's enter the script with the command ``` nano restart_hemi.sh ```.

3) Let's save it with Ctrl + O (save) and exit with Ctrl + X (close).
Our script is empty, but even if we fill it in, we won't be able to run this file.

4) First, we need to edit the permissions of the file so that it can be executable.

``` sudo chmod +x restart_hemi.sh ``` With this command, we gave the execution permission to this script file for our own user.

5) Now, we will open our script again with "nano" as above and paste the following codes into it. Then, let's save the script file by pressing ctrl +x, y, enter in this order and exit the file.

```
#!/bin/bash

restart_count=0
restart_log="restart_log.txt"

while true; do
# Start the application
./popmd

# Increment the restart count and write to the log file
((restart_count++))
echo "Restart $restart_count at $(date)" >> $restart_log

# If the application crashes or stops, the loop starts again
echo "The application has stopped. It will restart in 5 seconds..."
sleep 5
done
```
6) Everything is ready, let's run our script with ``` ./restart_hemi.sh ```.

7) If you get the error ``` bash: ./restart_hemi.sh: Permission denied ```, run the command ``` sudo chmod +x restart_hemi.sh ``` again and run the script again: ``` ./restart_hemi.sh ```

8) If you get the error ``` bash: ./restart_hemi.sh: /bin/bash^M: bad interpreter: Text file busy ```, install dos2unix with the following command

``` sudo apt-get install dos2unix ```

9) Then convert the restart_hemi.sh file to Unix format with the following command:

``` dos2unix restart_hemi.sh ```

10) Run the script again:

``` ./restart_hemi.sh ```

# That's all! Take Care of Yourself! Don't forget to star the repo and share it with your friends!

# I would be very happy and motivated if you follow my [Github profile](https://github.com/geocmsk) and [X account](https://x.com/cwitchking) for such repos.

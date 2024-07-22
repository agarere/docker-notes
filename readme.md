Docker Notları
--------------

0.Docker Kurulumu
-----------------
	-> Docker resmi sitesinden docker destop uygulaması indirilip kurulur.


1.Docker Hub Hesabı Açılması
----------------------------
	-> Docker Hub sitesinden kayıt olmak gerekiyor. 


2.Docker Container Nasıl Çekilir?
---------------------------------
	-> docker pull <image_name>


3.Image'ler nasıl listelenir?
-----------------------------
	-> docker images

	
4.Image nasıl çalıştırılır?
---------------------------
	-> docker run <image_name>
	-> Bu komut çalıştırıldığı zaman localde bu image var mı kontrol eder.
	   Bu image localde varsa direkt çalıştırılır. Eğer bu image localde yoksa,
	   Dockerhub'dan bu image çekilir ve çalıştırılır.
	-> Docker run yapıldığı zaman bu image'in çalışması için bir container oluşturulur.
	   Bu container içerisinde bu image çalıştırılır.
	-> Docker run yapılınca çalıştırılan container aslında bir process'dir.
	   Yani aynı image'ı kullanarak birden fazla aynı image ile container(process) çalıştırılabilir.

	 
5.Up olan container'ları nasıl listelersin?
-------------------------------------------
	-> docker ps
	-> Geçmişe dönük çalıştırılmış ve kapatılmış olan container'ları listelemek için;
	   docker ps -a
	-> Aktif olan containerları görmek için;
	   docker container ls
	-> Aktif/Pasif olan tüm container'ları görmek için;
	   docker container ls -a

	
6.Container isimlendirme
------------------------
	-> docker run --name <container_name> <image_name>

	
7.Container çalıştırma ve durdurma
----------------------------------
	-> docker start <container_name>
	-> docker stop <container_name>
	-> docker stop <container_id>

	
8.Container ve image silmek
---------------------------
	-> docker rm <container_name>
	-> docker rm <container_id>
	-> docker rm <image_name>

	
9.Tag ile işlem yapmak
----------------------
	-> docker run redis:5
	-> burada redisin 5 ile başlayan tag imageını indirip çalıştırır.
	

10.Image tag nasıl verilir?
---------------------------
	-> docker image tag <old_image_name> <new_image_name>


11.Arka planda çalışması için (Detach Mode)
-------------------------------------------
	-> docker run -d <image_name>
	-> -d parametresi detach modda çalışmasını sağlar. 
	   Böylece console bu işlem ile blocklanmamış olur.
	   

12.Arka planda çalışan Container'ın loglarını görmek için (Attach Mode)
-----------------------------------------------------------------------
	-> docker attach <container_id>
	

13.Container loglarını görüntülemek için
----------------------------------------
	-> docker container logs <container_id>
	-> başladığından itibaren üretilen logların hepsini gösterir.
	-> attach ile bakınca o an  attach ettikten sonraki logları görürsün.


14.Konsoldan kullanıcı girişi alan bir uygulama ise
---------------------------------------------------
	-> docker run -it <image_name>
	-> it: interactive terminal anlamına geliyor.


15.Port Mapping
---------------
	-> docker run -p DIŞ_PORT:İÇ_PORT <image_name>
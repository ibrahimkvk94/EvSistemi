Yapılan Güncellemeler:
Furnicatalogue scripti web sayfası üzerinde tasarımsal değişikliğe gidilmiştir.
Furnicatalogue scripti web sayfası üzerine filtremele sistemi eklenerek mobilya ismiyle arama scripti eklenmiştir.
Objectspawner scripti üzerinde yerleşim işlemleri için yardımcı text eklendi.
Objectspawner scripti üzerinde komutlar güncelleştirildi.
Objectspawner scripti üzerinde Mobilya id'si üzerinden düzenleme ve silme işlemleri eklendi.
MF-housing-mod üzerinde kapı çıkışında yakınındaki oyuncuları davet et (Z Tuşu ile) menüsü eklendi. (Bu menünün kontrolleri henüz yapılamadı İşlevselliği testlerinizin sonuçlarını beklemekte)
MF-housing-mod gardorap sisteminde kasa erişimi eklendi.
MF-housing-mod üzerinde disc-inventoryhud bağlantısı eklendi.

Gerekli Scriptler:
essentialmode
Script Kurulum:
Dosya içerisinde bulunan sql dosyalarını veritabanına enjekte ediyoruz
Ardından ise scripti resources içine koyuyoruz.
Start işlemlerini yapıyoruz
(ŞİMDİLİK) Sunucu başlatıldığında objectspawner' scriptine restart atıyoruz.


Scripten Kareler:


SPOYLER: V1.0


Scriptten Video:

Bu kısım yapım aşamasındadır.


Script İndirme Bağlantısı:

Virüs : Kontrol Noktası
Link. : İndirme Noktası
Script Komutları:
Mobilya sayfasına erişim : /Mobilya
Yerleştirilmiş mobilyaların ID'lerine erişim : /Mobilyalar
Id üzerinden mobilya düzenleme : /mobilyadüzenle id Örn: /mobilyadüzenle 175
Id üzerinden mobilya silme : /mobilyasil id Örn: /mobilyasil 175
-------------
Ev davet sistemi : /davet id
Ev dolap sistemi :/ayarla
Ev anahtar verme: /anahtarver
Ev anahtar geri alma : /anahtaral



Önemli Not:
Video ve Resimlerde gözüken mobilya resimleri ve mobilya itemleri script içeriğine dahil olmayıp ücretsiz paylaşımı yapılmayacaktır. Ortaya çıkan işçiliği kendiniz uğraşmayıp hızlı (Ücretli) edinmek istiyorsanız HyperQR#4581Discord adresinden tarafıma ulaşabilirsiniz.

Furnicatalogue Scriptini Kullanan ve Sadece Filtreleme Kısmını İsteyenler İçin:
index.html sayfası sonuna aşağıdaki kodları ekleyiniz.

Kod:
<script>
jQuery.expr[':'].contains = function(a, i, m) {
    return jQuery(a).text().toUpperCase()
        .indexOf(m[3].toUpperCase()) >= 0;
};

$(document).ready(function () {
    // keyup ile inputa herhangi bir değer girilince fonksiyonu tetikliyoruz
    $("#searchTags").keyup(function(){
        // inputa yazılan değeri alıyoruz
        var value = $("#searchTags").val();
        // eğer input içinde değer yoksa yani boşsa tüm menüyü çıkartıyoruz
        if(value.length==0){
            $(".grid-item").show();
        // arama yapılmışsa ilk olarak tüm menüyü gizliyoruz ve girilen değer ile eşleşen kısmı çıkarıyoruz
        }else{
            $(".grid-item").hide();
            $(".grid-item:contains("+value+")").show();
        }
    });
});
</script>
İndex.html'de background div'i içerisine aşağıdaki kodları ekleyiniz.
Kod:
            <div id="location" style="margin-left:80%; margin-top: 10%;width: 100px;">
                Filtreleme : <input id='searchTags' type='text' placeholder="Aranacak Kelime">
            </div>
Mobilya Ekleme:
furnicatalogue scripti içerisinde bulunan furni.lua'ya numaraları devam ettirecek eklemeleri yapınız.,
Örn: [8]={[4]="Bitki",[3] = "p_int_jewel_plant_01",[1] ="Saksı8",[2] =1446},
[8] sıra numarası en son numaradan devam ediniz.
[4] ürün kategorisi 4 sabit hangi kategori olduğunu belirtiniz.
[3] oyunun içerisinde bulunan obje isimleri.
[1] web sayfasında görülecek ismi
[2] ürünün satış fiyatı

Bu aşamadan sonra ürünün görselini jpg olacak şekilde img klasörüne atıp resource dosyasına gerekli tanıtma işlemini yaptırın.
Bu adımlarla uğraşmak istemiyorsanız hazır 300'e yakın objeye sadece 20 TL'ye ulaşmak için discord üzerinden iletişim kurun.

Bilinen Hatalar:
Sunucu yeniden başladığında ilk veritabanı bağlantısı yapılırken hata vermekte dolayısıyla sunucuyu başlatır başlatmak scripti restartlamak gerekmektedir.(Bu hata üzerinde çalışmam sürüyor sonraki güncelleme ile bunu gidereceğim)
/Mobilyalar komutu çalışması için tekrar olarak yazılması gerekmektedir.
MF-housing-mod üzerinde ışık problemi mevcuttur.
MF-housing-mod davet sistemi aktif midir belirlenemedi.

Güncellemeler :
Script deneme aşamasında olduğu için mobilya ev dışında da kullanılabiliniyordu. Bu kapatıldı.

# EvSistemi
Bu script hcankara35(ibrahim KAVAK) tarafından orjinal tasarımların üzerinde güncellenmiş ve yeniden kodlanmıştır.

[B]Yapılan Güncellemeler:[/B]
[LIST=1]
[*][B]Furnicatalogue scripti web sayfası üzerinde tasarımsal değişikliğe gidilmiştir.[/B]
[*][B]Furnicatalogue scripti web sayfası üzerine filtremele sistemi eklenerek mobilya ismiyle arama scripti eklenmiştir.[/B]
[*][B]Objectspawner scripti üzerinde yerleşim işlemleri için yardımcı text eklendi.[/B]
[*][B]Objectspawner scripti üzerinde komutlar güncelleştirildi.[/B]
[*][B][B]Objectspawner scripti üzerinde Mobilya id'si üzerinden düzenleme ve silme işlemleri eklendi.[/B][/B]
[*][B][B]MF-housing-mod üzerinde kapı çıkışında yakınındaki oyuncuları davet et (Z Tuşu ile) menüsü eklendi. (Bu menünün kontrolleri henüz yapılamadı İşlevselliği testlerinizin sonuçlarını beklemekte)[/B][/B]
[*][B][B][B][B]MF-housing-mod gardorap sisteminde kasa erişimi eklendi.[/B][/B][/B][/B]
[*][B][B][B][B][B][B]MF-housing-mod üzerinde disc-inventoryhud bağlantısı [B][B][B][B]eklendi[/B][/B][/B][/B].[/B][/B][/B][/B][/B][/B]
[/LIST]

[B]Gerekli Scriptler:[/B]
[LIST=1]
[*][URL='https://github.com/kanersps/essentialmode/releases/latest']essentialmode[/URL]
[/LIST]
[B]Script Kurulum:[/B]
[LIST=1]
[*]Dosya içerisinde bulunan sql dosyalarını veritabanına enjekte ediyoruz
[*]Ardından ise scripti resources içine koyuyoruz.
[*]Start işlemlerini yapıyoruz
[*](ŞİMDİLİK) Sunucu başlatıldığında objectspawner' scriptine restart atıyoruz.
[/LIST]


[B]Scripten Kareler:

[SPOILER="v1.0"][/SPOILER][/B][SPOILER="v1.0"]

[ATTACH type="full" alt="18338"]18338[/ATTACH]
[ATTACH type="full" alt="18337"]18337[/ATTACH]
[ATTACH type="full" alt="18336"]18336[/ATTACH]
[ATTACH type="full" alt="18335"]18335[/ATTACH]

[ATTACH type="full" alt="18334"]18334[/ATTACH]
[ATTACH type="full" alt="18333"]18333[/ATTACH]

[ATTACH type="full" alt="18332"]18332[/ATTACH]


[/spoiler][SPOILER="v1.0"]

[/SPOILER]


[B]Scriptten Video:[/B]

Bu kısım yapım aşamasındadır.


[B]Script İndirme Bağlantısı:[/B]

[LIST=1]
[*]Virüs : [URL='https://www.virustotal.com/gui/file/9f8c3ce7010311dda06f9b5475063f1dc78c9c100c7c6ece2dd07c403479cef5/detection']Kontrol Noktası[/URL]
[*]Link. :[URL='https://github.com/ibrahimkvk94/EvSistemi.git'] İndirme Noktası[/URL]
[/LIST]
[B]Script Komutları:[/B]
   Mobilya sayfasına erişim : /Mobilya
   Yerleştirilmiş mobilyaların ID'lerine erişim : /Mobilyalar
   Id üzerinden mobilya düzenleme  : /mobilyadüzenle id Örn: /mobilyadüzenle 175
   Id üzerinden mobilya silme  : /mobilyasil id Örn: /mobilyasil 175
-------------
   Ev davet sistemi : /davet id
   Ev dolap sistemi :/ayarla
   Ev anahtar verme: /anahtarver
   Ev anahtar geri alma : /anahtaral



[B]Önemli Not:[/B]
Video ve Resimlerde gözüken mobilya resimleri ve mobilya itemleri script içeriğine dahil olmayıp ücretsiz paylaşımı yapılmayacaktır. Ortaya çıkan işçiliği kendiniz uğraşmayıp hızlı (Ücretli) edinmek istiyorsanız HyperQR#4581Discord adresinden tarafıma ulaşabilirsiniz.

[B]Furnicatalogue Scriptini Kullanan ve Sadece Filtreleme Kısmını İsteyenler İçin:[/B]
index.html sayfası sonuna aşağıdaki kodları ekleyiniz.

[CODE]<script>
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
</script>[/CODE]

İndex.html'de  background div'i içerisine aşağıdaki kodları ekleyiniz.
[CODE]            <div id="location" style="margin-left:80%; margin-top: 10%;width: 100px;">
                Filtreleme : <input id='searchTags' type='text' placeholder="Aranacak Kelime">
            </div>[/CODE]

[B]Mobilya Ekleme:[/B]
   furnicatalogue scripti içerisinde bulunan furni.lua'ya numaraları devam ettirecek eklemeleri yapınız.,
Örn: [8]={[4]="Bitki",[3]  =  "p_int_jewel_plant_01",[1] ="Saksı8",[2] =1446},
   [8] sıra numarası en son numaradan devam ediniz.
   [4] ürün kategorisi 4 sabit hangi kategori olduğunu belirtiniz.
   [3] oyunun içerisinde bulunan obje isimleri.
   [1] web sayfasında görülecek ismi
   [2] ürünün satış fiyatı

Bu aşamadan sonra ürünün görselini jpg olacak şekilde img klasörüne atıp resource dosyasına gerekli tanıtma işlemini yaptırın.
Bu adımlarla uğraşmak istemiyorsanız hazır 300'e yakın objeye sadece 20 TL'ye ulaşmak için discord üzerinden iletişim kurun.

[B]Bilinen Hatalar:[/B]
[LIST=1]
[*]Sunucu yeniden başladığında ilk veritabanı bağlantısı yapılırken hata vermekte dolayısıyla sunucuyu başlatır başlatmak scripti restartlamak gerekmektedir.(Bu hata üzerinde çalışmam sürüyor sonraki güncelleme ile bunu gidereceğim)
[*]/Mobilyalar komutu çalışması için tekrar olarak yazılması gerekmektedir.
[*]MF-housing-mod üzerinde ışık problemi mevcuttur.
[*]MF-housing-mod davet sistemi aktif midir belirlenemedi.
[/LIST]

[B]Güncellemeler : [/B]
[LIST=1]
[*]Script deneme aşamasında olduğu için mobilya ev dışında da kullanılabiliniyordu. Bu kapatıldı.
[/LIST]

# Diijkstra-algoritmasi
Dijkstra Algoritması ile En Kısa Yol ve Performans Analizi
Bu proje, C programlama dili kullanılarak komşuluk listesi (adjacency list) yapısı ile oluşturulmuş bir grafta, Dijkstra Algoritması yardımıyla en kısa yolun bulunmasını sağlamaktadır. Kod, yalnızca rotayı hesaplamakla kalmaz, aynı zamanda algoritmanın iterasyon sayısı, karşılaştırma sayısı ve çalışma süresi gibi verilerini de sunarak bir performans analizi imkanı tanır.

Proje İçeriği ve Özellikleri
Dinamik Graf Yapısı: Graf, bellek dostu bir yaklaşım olan komşuluk listesi kullanılarak struct yapıları ile dinamik olarak oluşturulmuştur.

En Kısa Yol Hesaplama: Başlangıç düğümünden (A) hedef düğüme (G) kadar olan en düşük maliyetli rotayı ve toplam maliyeti hesaplar.

Performans Metrikleri: Algoritmanın çalışma sürecindeki iterasyon (döngü) sayısını ve gerçekleştirilen mantıksal karşılaştırma sayısını takip eder.

Süre Ölçümü: time.h kütüphanesi kullanılarak algoritmanın işlem süresi saniye cinsinden ölçülür.

Dinamik Maliyet Güncellemesi: Program çalışırken belirli bir kenarın (edge) maliyetini değiştirme ve güncel graf üzerinden algoritmayı tekrar çalıştırıp sonuçları karşılaştırma özelliği sunar.

Graf Yapısı
Graf, toplam 7 düğümden (V=7) oluşmaktadır. Kod içerisinde düğümler 0'dan 6'ya kadar numaralandırılmış olup, çıktılarda anlaşılırlığı artırmak adına harflerle (A, B, C, D, E, F, G) temsil edilmektedir.

0 -> A (Başlangıç Düğümü)

6 -> G (Hedef Düğümü)

Varsayılan graf üzerindeki kenarlar ve ağırlıkları kod içerisindeki addEdge fonksiyonları ile tanımlanmıştır.

Dosya Yapısı ve Fonksiyonlar
createEdge(): Yeni bir kenar oluşturur ve bellek tahsisi yapar.

addEdge(): Belirtilen başlangıç ve bitiş düğümleri arasına ağırlığı ile birlikte yeni bir kenar ekler.

updateEdgeWeight(): Belirtilen iki düğüm arasındaki kenarın ağırlığını verilen çarpan ile günceller.

minDistance(): Henüz işlenmemiş düğümler arasından başlangıca en yakın olan düğümü seçer.

printPath(): Önceki düğümleri (parent array) takip ederek başlangıçtan hedefe olan rotayı yazdırır.

dijkstra(): Ana algoritma fonksiyonudur. En kısa rotayı bulur ve performans analiz sonuçlarını ekrana basar.

Derleme ve Çalıştırma
Bu projeyi derlemek ve çalıştırmak için sisteminizde bir C derleyicisinin (örneğin GCC) kurulu olması gerekmektedir.

Terminal veya komut satırını açarak kaynak kodun bulunduğu dizine gidin ve aşağıdaki komutları sırasıyla çalıştırın:

Derlemek için:

Bash
gcc main.c -o dijkstra_analizi
Çalıştırmak için (Linux/macOS):

Bash
./dijkstra_analizi
Çalıştırmak için (Windows):

Bash
dijkstra_analizi.exe
Çalışma Senaryoları (Çıktı Analizi)
Program çalıştırıldığında iki farklı senaryo üzerinden sonuç üretir:

Birinci Çalıştırma (Normal Graf): Kodda başlangıçta tanımlanan standart kenar ağırlıkları kullanılarak A düğümünden G düğümüne en kısa yol bulunur.

İkinci Çalıştırma (Maliyet Güncellemesi): Belirli bir rotanın maliyeti (Örneğin B düğümünden D düğümüne olan maliyet) iki katına çıkarılır. Sistem bu değişikliği bildirir ve algoritma yeni maliyetler üzerinden en kısa yolu ve yeni rotayı tekrar hesaplar.

Her iki çalıştırma sonucunda da rotanın maliyeti, izlenen yol, iterasyon/karşılaştırma sayıları ve milisaniye bazında işlem süreleri ekrana yazdırılır. Bu sayede graf yapısındaki değişimlerin algoritma davranışına ve performansına etkisi gözlemlenebilir.

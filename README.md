
<div class="cat" id="top"> 
  <img src="./img_s.png" alt="cizgimmm">
  &#xa0;
</div>
<h1 align="center">Opensource Kaynak Kod Derleme ve Linkleme İşlemleri</h1>

<p align="center">
  <img alt="Github top language" src="https://img.shields.io/github/languages/top/otahsinb/BUILDING-OPENSOURCECODE">
  <img alt="Github stars" src="https://img.shields.io/github/stars/otahsinb/BUILDING-OPENSOURCECODE" />
</p>


<p align="center">
  <a href="#dart-açıklama">Açıklama</a> &#xa0; | &#xa0; 
  <a href="#sparkler-libtiff">LibTiff</a> &#xa0; | &#xa0;
  <a href="#octocat-zlib">Zlib</a> &#xa0; | &#xa0;
  <a href="#surfer-freetype">Freetype</a> &#xa0; | &#xa0;
  <a href="#dizzy-poco">Poco</a> &#xa0; | &#xa0;
  <a href="#art-openssl">OpenSSL</a> &#xa0; | &#xa0;
  <a href="#twisted_rightwards_arrows-odbc">ODBC</a> &#xa0; | &#xa0;
  <a href="#fish_cake-mysql-client">MySQL Client</a> &#xa0; | &#xa0;
  <a href="#dvd-postgresql-client">PostGreSQL Client</a> &#xa0; | &#xa0;
  <a href="#factory-d12">D12</a> &#xa0; | &#xa0;
  <a href="#sparkles-d34">D34</a> &#xa0; | &#xa0;
  <a href="https://github.com/otahsinb" target="_blank">Yazar</a>
</p>

<br>

## :dart: Açıklama ##

 Bu alan opensource projelerini güncel işletim sistemlerinde derleyerek kullanma adımlarını içermektedir.
 
:heavy_check_mark: Kaynak Kodlar :heavy_check_mark: Araçlar :heavy_check_mark: Derleme Adımları :heavy_check_mark: Linker Ayarları :heavy_check_mark: Best Practices

## :sparkler: LibTiff ##
 
 libtiff is a set of C functions (a library) that support the manipulation of TIFF image files. The library requires an ANSI C compilation environment for building and presumes an ANSI C environment for use.
 
 libtiff provides interfaces to image data at several layers of abstraction (and cost).
 
 At the highest level image data can be read into an 8-bit/sample, ABGR pixel raster format without regard for the underlying data organization, colorspace, or compression scheme.
 
 high-level interface the library provides scanline-, strip-, and tile-oriented interfaces that return data decompressed but otherwise untransformed. These interfaces require that the application first identify the organization of stored data and select either a strip-based or tile-based API for manipulating data. At the lowest level the library provides access to the raw uncompressed strips or tiles, returning the data exactly as it appears in the file.
 
 build tree configuration is useful for building multiple targets from a single source tree and building from a read-only source tree (e.g. CD-ROM)
 
 
  ```sh
    .
    ├── Tag Image File Format (TIFF) bir görüntü format türüdür.
    ├── Açıkkaynaklı olarak geliştirilen ve yaygınlaştırılan LibTiff yazılımı ile Tiff formatındaki görüntüler üzerinde data manupülasyonu yapılabilmektedir.
    ├── Görüntü okuma, yazma, depolama ve çeşitli yetenekleri bulunmaktadır.
    ├── Yazılım 32 ve 64 bitlik makinelerde çalışabilmektedir.
    ├── 16 bitlik makinelerde de çalışabilir fakat sıkıştırma gibi çeşitli yetenekler kısıtlanmış olacaktır.
    ├── LibTiff ANCI C derleme ortamında build edilebilir.
    └── C dilinde yazılmış TIFF görüntü dosyalarında veri manüpülasyonu yapılmasını sağlayan yetenekleri vardır.
  ```

<details>
  <summary> :musical_score: Adım Adım Derleme :musical_score: </summary> <br />
   
  |:musical_score:|   Linkten (http://www.libtiff.org/) Kaynak Kodları İndiriniz...🡓🡓🡓    |
  | ------- | --- |
  
  |:musical_score:|   Microsoft Visual C++ 2022 kurulumu yapılır.    |
  | ------- | --- |
  
  |:musical_score:|   Zip veya Tar.gz olarak indirilen LibTiff dosyası WinRar benzeri bir yardımcı program ile açılarak extract edilir. |
  | ------- | --- |
  
  |:musical_score:|   İndirilen dosyanın alanında gelinir ve MSVC++ aracı sağ tık menüsünden açılır. Bu işlem yapıldıktan sonra .vs isimli dosya bu alanda açılacaktır.  ${PROJECT_SOURCE_DIR}/tiff-4.5.0 |
  | ------- | --- |
  
  |:musical_score:|   MSVC++ın Developer Command Prompt alanı açılır ve aşağıdaki komutlar sırası ile çağrılır. Olması gereken klasör alanı: ${PROJECT_SOURCE_DIR}/tiff-4.5.0 |
  | ------- | --- |
  
  ```sh
  mkdir buildx86
  cd buildx86
  cmake ..
  ```
  Yukarıdaki yapı ile build tree oluşturulacak ve sonradan üretilen dosyalar kaynak kod alanından uzak tutulacaktır.
  
  ```
  cmake --build . --config Release
  cd buildx86\libtiff\Release
  ```
  
  |:musical_score:|  Release klasörü altına üretilen dosyalar kopyalanarak \lib olarak adlandırılan yeni bir klasörün içine kopyalanır. Programın diğer dosyaları libtiff içindedir ve  \include isimli bir klasörün altına kopyalanır. |
  | ------- | --- |
  
  |:musical_score:|  Projenin external klasörü altındaki lib ve include alanları uygun olarak ayarlandığında LibTiff programı kullanıma hazırdır.  |
  | ------- | --- |
  
  |:musical_score:|   ``` ```  |
  | ------- | --- |
   
   
</details>


<a href="#top">Back to top</a>

## :octocat: Zlib ##

    .
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    └── 


<details>
  
  <summary> Adım Adım Derleme </summary> <br />
  
  :musical_score: Kaynak Kodları (Aşağıdaki Linkten Kaynak Kodları İndiriniz...🡓🡓🡓)
  ```sh
  https://hackingcpp.com/cpp/cheat_sheets.html
  ```
  
</details>


<a href="#top">Back to top</a>

## :surfer: Freetype ##

    .
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    └── 


<details>
  
  <summary> Adım Adım Derleme </summary> <br />
  
  :musical_score: Kaynak Kodları (Aşağıdaki Linkten Kaynak Kodları İndiriniz...🡓🡓🡓)
  ```sh
  https://hackingcpp.com/cpp/cheat_sheets.html
  ```
  
</details>


<a href="#top">Back to top</a>

## :dizzy: Poco ##

    .
    ├── 
    ├── 
    └── 


<details>
  
  <summary> Adım Adım Derleme </summary> <br />
  
  :musical_score: Kaynak Kodları (Aşağıdaki Linkten Kaynak Kodları İndiriniz...🡓🡓🡓)
  ```sh
  https://hackingcpp.com/cpp/cheat_sheets.html
  ```
  
</details>

<a href="#top">Back to top</a>

## :art: OpenSSL ##

    .
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    └── 


<details>
  
  <summary> Adım Adım Derleme </summary> <br />
  
  :musical_score: Kaynak Kodları (Aşağıdaki Linkten Kaynak Kodları İndiriniz...🡓🡓🡓)
  ```sh
  https://hackingcpp.com/cpp/cheat_sheets.html
  ```
  
</details>


<a href="#top">Back to top</a>


## :twisted_rightwards_arrows: ODBC ##

    .
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    └── 



<details>
  
  <summary> Adım Adım Derleme </summary> <br />
  
  :musical_score: Kaynak Kodları (Aşağıdaki Linkten Kaynak Kodları İndiriniz...🡓🡓🡓)
  ```sh
  https://hackingcpp.com/cpp/cheat_sheets.html
  ```
  
</details>


<a href="#top">Back to top</a>


## :fish_cake: MySQL Client ##

    .
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    └── 
    

<details>
  
  <summary> Adım Adım Derleme </summary> <br />
  
  :musical_score: Kaynak Kodları (Aşağıdaki Linkten Kaynak Kodları İndiriniz...🡓🡓🡓)
  ```sh
  https://hackingcpp.com/cpp/cheat_sheets.html
  ```
  
</details>
  
<a href="#top">Back to top</a>

## :dvd: PostGreSQL Client ##

    .
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    └── 


<details>
  
  <summary> Adım Adım Derleme </summary> <br />
  
  :musical_score: Kaynak Kodları (Aşağıdaki Linkten Kaynak Kodları İndiriniz...🡓🡓🡓)
  ```sh
  https://hackingcpp.com/cpp/cheat_sheets.html
  ```
  
</details>


<a href="#top">Back to top</a>

## :factory: D12 ##

    .
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    └── 


<details>
  
  <summary> Adım Adım Derleme </summary> <br />
  
  :musical_score: Kaynak Kodları (Aşağıdaki Linkten Kaynak Kodları İndiriniz...🡓🡓🡓)
  ```sh
  https://hackingcpp.com/cpp/cheat_sheets.html
  ```
  
</details>

<a href="#top">Back to top</a>

## :sparkles: D34 ##

    .
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    ├── 
    └── 


<details>
  
  <summary> Adım Adım Derleme </summary> <br />
  
  :musical_score: Kaynak Kodları (Aşağıdaki Linkten Kaynak Kodları İndiriniz...🡓🡓🡓)
  ```sh
  https://hackingcpp.com/cpp/cheat_sheets.html
  ```
  
</details>

Made with :clock12: :clock3:  :clock6:  :clock9: by otahsinb.\
&#xa0;

<a href="#top">Back to top</a>

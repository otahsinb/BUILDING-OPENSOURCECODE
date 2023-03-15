
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
  
  |:musical_score:|   İndirilen dosyanın alanında gelinir ve MSVC++ aracı sağ tık menüsünden açılır. |
  | ------- | --- |
  | :musical_score: | Bu işlem yapıldıktan sonra .vs isimli dosya bu alanda açılacaktır. |
  
  |:musical_score:|   MSVC++ın Developer Command Prompt alanı açılır ve aşağıdaki komutlar sırası ile çağrılır.🡓🡓🡓 |
  | ------- | --- |
  |:arrow_forward:|   ``` mkdir buildx86 ``` |
  |:arrow_forward:|   ``` cd buildx86 ``` |
  |:arrow_forward:|   ``` cmake .. ``` |

  
  |:musical_score:|   Yukarıdaki yapı ile build tree oluşturulacaktır. Aşağıdaki komutlar ile *.lib ve *.dll dosyaları elde edilir.🡓🡓🡓 |
  | ------- | --- |
  |:arrow_forward:|   ``` cmake --build . --config Release ``` |
  |:arrow_forward:|   ``` cd buildx86\libtiff\Release ``` |

  |:musical_score:|  Release klasörü altına üretilen dosyalar kopyalanarak \lib olarak adlandırılan yeni bir klasörün içine kopyalanır.|
  | ------- | --- |
  
  |:musical_score:|  Programın diğer dosyaları libtiff içindedir ve \include isimli bir klasörün altına kopyalanır. |
  | ------- | --- |
  |:musical_score:|  Windows geliştirme ortamı için derleme işlemi tamamlanmıştır. |
  
  |:musical_score:|  Programın çalışmasını kontrol etmek için demo.cxx isimli bir dosya açınız . |
  | ------- | --- |
  |:musical_score:|  Aşağıdaki kodu kopyalarak demo.cxx dosyası içine koyunuz. |
  
  ```c
#include <stdio.h>
#include "tiffio.h"

int main(int argc, const char* argv[])
{
    if (argc < 2) {
        printf("Usage: demo [TIFF file]\n");
        return 0;
    }
    const char* pszImageFile = argv[1];
    TIFF* tif = TIFFOpen(pszImageFile, "r");
    if (tif) {
        uint32 imageWidth, imageLength;
        uint16 compression;
        TIFFGetField(tif, TIFFTAG_IMAGEWIDTH, &imageWidth);
        TIFFGetField(tif, TIFFTAG_IMAGELENGTH, &imageLength);
        TIFFGetField(tif, TIFFTAG_COMPRESSION, &compression);
        printf("imageWidth %d, imageLength %d \n\n", imageWidth, imageLength);
        switch(compression) {
            case COMPRESSION_LZW:
                printf("COMPRESSION_LZW \n\n");
                break;
            case COMPRESSION_OJPEG:
                printf("COMPRESSION_OJPEG \n\n");
                break;
            case COMPRESSION_JPEG:
                printf("COMPRESSION_JPEG \n\n");
                break;
        }
        TIFFClose(tif);
    }
    return 0;
}
  ```
  |:musical_score:|  Yukarıdaki kodu derlendiğini kontrol etmek için CMakeLists.txt isimli bir dosya açınız . |
  | ------- | --- |
  |:musical_score:|  Aşağıdaki kodu kopyalarak demo.cxx dosyası içine koyunuz. |
                 
  ```c
  cmake_minimum_required (VERSION 2.6)
  project (demo)
  MESSAGE( STATUS "PROJECT_NAME: " ${PROJECT_NAME} )
  link_directories("${PROJECT_SOURCE_DIR}/lib") 
  include_directories("${PROJECT_SOURCE_DIR}/include/")
  # Add the executable
  add_executable(demo demo.cxx)
  target_link_libraries (demo "tiff")
  add_custom_command(TARGET demo POST_BUILD 
          COMMAND ${CMAKE_COMMAND} -E copy_if_different
          "${PROJECT_SOURCE_DIR}/lib/tiff.dll"              
          $<TARGET_FILE_DIR:demo>)
  ```
  |:musical_score:|   ki komutlar ile *.lib ve *.dll dosyaları elde edilir.🡓🡓🡓 |
  | ------- | --- |
  |:arrow_forward:|   ```  ``` |
  |:arrow_forward:|   ```  ``` |
                 
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

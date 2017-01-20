---
title: "Verwenden von C++ AMP in Windows Store-Apps"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
caps.latest.revision: 14
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von C++ AMP in Windows Store-Apps
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie können C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\) in der [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App verwenden, um Berechnungen anhand des Grafikprozessors \(Graphics Processing Unit, GPU\) oder anderer rechnergestützter Beschleuniger auszuführen.   bietet jedoch keine APIs, um mit Windows\-Runtime\-Typen direkt zu arbeiten, und die Windows\-Runtime stellt keinen Wrapper für  bereit.  Wenn Sie Windows\-Runtime\-Typen im Code verwenden \(einschließlich selbst erstellter\), müssen sie in Typen konvertiert werden, die mit  kompatibel sind.  
  
## Überlegungen zur Leistung  
 Wenn Sie [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]\) verwenden, um die [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App zu erstellen, empfiehlt es sich, POD \(Plain Old Data\)\-Typen zusammen mit zusammenhängendem Speicher \(z. B. `std::vector` oder Arrays im C\-Format\) für Daten zu verwenden, die mit C\+\+ AMP verwendet werden.  Damit können Sie eine höhere Leistung erzielen als durch Verwenden von Nicht\-POD\-Typen oder Windows RT\-Containern, da kein Marshallen auftreten muss.  
  
 Damit Sie in einem C\+\+ AMP\-Kernel auf Daten zugreifen können, die auf diese Weise gespeichert sind, umschließen Sie einfach den `std::vector`\- oder Arrayspeicher in einer `concurrency::array_view` und verwenden die Arrayansicht dann in einer `concurrency::parallel_for_each`\-Schleife:  
  
```cpp  
// simple vector addition example  
std::vector<int> data0(1024, 1);  
std::vector<int> data1(1024, 2);  
std::vector<int> data_out(data0.size(), 0);  
  
concurrency::array_view<int, 1> av0(data0.size(), data0);  
concurrency::array_view<int, 1> av1(data1.size(), data1);  
concurrency::array_view<int, 1> av2(data_out.size(), data2);   
  
av2.discard_data();  
  
concurrency::parallel_for_each(av0.extent, [=](concurrency::index<1> idx) restrict(amp)  
{  
  av2[idx] = av0[idx] + av1[idx];  
});  
  
```  
  
## Marshallen von Windows\-Runtime\-Typen  
 Wenn Sie mit Windows\-Runtime\-APIs arbeiten, möchten Sie möglicherweise  für Daten verwenden, die in einem Windows\-Runtime\-Container wie `Platform::Array<T>^` oder in komplexen Datentypen wie Klassen oder Strukturen gespeichert sind, die mit dem `ref`\- oder `value`\-Schlüsselwort deklariert werden.  In diesen Fällen ist zusätzliche Arbeit erforderlich, um die Daten für C\+\+ AMP verfügbar zu machen.  
  
### Platform::Array\<T\>^, wobei T ein POD\-Typ ist  
 Wenn ein `Platform::Array<T>^` auftritt und T ein POD\-Typ ist, können Sie auf den zugrunde liegenden Speicher zugreifen, indem Sie die `get`\-Memberfunktion verwenden:  
  
```cpp  
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API  
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));  
  
```  
  
 Wenn T kein POD\-Typ ist, verwenden Sie die im folgenden Abschnitt beschriebene Technik, um die Daten mit C\+\+ AMP zu verwenden.  
  
### Windows\-Runtime\-Typen: Verweisklassen und Wertklassen  
 C\+\+ AMP unterstützt keine komplexen Datentypen.  Dies umfasst Nicht\-POD\-Typen sowie alle Typen, die anhand des `ref`\- oder `value`\-Schlüsselworts deklariert werden.  Wenn ein nicht unterstützter Typ in einem `restrict(amp)`\-Kontext verwendet wird, wird ein Kompilierzeitfehler generiert.  
  
 Wenn ein nicht unterstützter Typ auftritt, können Sie die interessanten Teile seiner Daten in ein `concurrency::array`\-Objekt kopieren.  Mit diesem Ansatz des manuellen Kopierens werden nicht nur die Daten für C\+\+ AMP verfügbar gemacht. Er kann zusätzlich die Leistung verbessern, indem der Datenort maximiert und sichergestellt wird, dass Daten, die nicht verwendet werden, nicht in den Beschleuniger kopiert werden.  Sie können die Leistung weiter verbessern, indem Sie ein *Stagingarray* verwenden. Dies ist eine spezielle Art von `concurrency::array`, das einen Hinweis für die AMP\-Laufzeit bereitstellt, dass das Array für eine häufige Übertragung zwischen ihm und anderen Arrays im angegebenen Beschleuniger optimiert werden sollte.  
  
```cpp  
// pixel_color.h  
ref class pixel_color sealed  
{  
 public:   
  pixel_color(Platform::String^ color_name, int red, int green, int blue)   
  {  
    name = color_name;  
    r = red;  
    g = green;  
    b = blue;  
  }  
  
  property Platform::String^ name;   
  property int r;  
  property int g;  
..property int b;  
};  
  
// Some other file  
std::vector<pixel_color^> pixels (256);   
  
for(pixel_color ^pixel : pixels)   
{  
  pixels.push_back(ref new pixel_color("blue", 0, 0, 255));  
}  
// Create the accelerators  
auto cpuAccelerator = concurrency::accelerator(concurrency::accelerator::cpu_accelerator);  
auto devAccelerator = concurrency::accelerator(concurrency::accelerator::default_accelerator);  
  
// Create the staging arrays  
concurrency::array<float, 1> red_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);  
concurrency::array<float, 1>  blue_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);   
  
// Extract data from the complex array of structs into staging arrays.  
concurrency::parallel_for(0, 256, [&](int i)  
{   
  red_vec[i] = pixels[i]->r; blue_vec[i] = pixels[i]->b;  
});  
  
// Array views are still used to copy data to the accelerator  
concurrency::array_view<float, 1> av_red(red_vec);  
concurrency::array_view<float, 1> av_blue(blue_vec);  
  
// Change all pixels from blue to red.  
concurrency::parallel_for_each(av_red.extent, [=](index<1> idx) restrict(amp)  
{  
  av_red[idx] = 255;  
  av_blue[idx] = 0;  
});  
  
```  
  
## Siehe auch  
 [Erstellen Ihrer ersten Windows Store\-App mit C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=249073)   
 [Erstellen von Windows\-Runtime\-Komponenten in C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=249076)
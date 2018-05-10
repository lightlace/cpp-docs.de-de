---
title: Verwenden von C++ AMP in uwp-Apps | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5736c84f21535222de5659780968efd98e1467da
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="using-c-amp-in-uwp-apps"></a>Verwenden von C++ AMP in uwp-Apps
Sie können C++ AMP (C++ Accelerated Massive Parallelism) in Ihrer app (Universelle Windows Plattform) verwenden, um Berechnungen anhand der GPU (Graphics Processing Unit) oder anderer rechnergestützter Beschleuniger auszuführen. bietet jedoch keine APIs, um mit Windows-Runtime-Typen direkt zu arbeiten, und die Windows-Runtime stellt keinen Wrapper für  bereit. Wenn Sie Windows-Runtime-Typen im Code verwenden (einschließlich selbst erstellter), müssen sie in Typen konvertiert werden, die mit  kompatibel sind.  
  
## <a name="performance-considerations"></a>Überlegungen zur Leistung  
 Bei Verwendung von [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]) zum Erstellen Ihrer app (Universelle Windows Plattform) wird empfohlen, dass Sie Plain Old Data (POD) Typen zusammen mit zusammenhängendem Speicher verwenden – z. B. `std::vector` oder Arrays im C-Stil – für Daten, die verwendet werden mit C++ AMP. Damit können Sie eine höhere Leistung erzielen als durch Verwenden von Nicht-POD-Typen oder Windows RT-Containern, da kein Marshallen auftreten muss.  
  
 Damit Sie in einem C++ AMP-Kernel auf Daten zugreifen können, die auf diese Weise gespeichert sind, umschließen Sie einfach den `std::vector`- oder Arrayspeicher in einer `concurrency::array_view` und verwenden die Arrayansicht dann in einer `concurrency::parallel_for_each`-Schleife:  
  
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
  
## <a name="marshaling-windows-runtime-types"></a>Marshallen von Windows-Runtime-Typen  
 Wenn Sie mit Windows-Runtime-APIs arbeiten, möchten Sie möglicherweise  für Daten verwenden, die in einem Windows-Runtime-Container wie `Platform::Array<T>^` oder in komplexen Datentypen wie Klassen oder Strukturen gespeichert sind, die mit dem `ref`- oder `value`-Schlüsselwort deklariert werden. In diesen Fällen ist zusätzliche Arbeit erforderlich, um die Daten für C++ AMP verfügbar zu machen.  
  
### <a name="platformarrayt-where-t-is-a-pod-type"></a>Platform:: Array\<T > ^, wobei T ein POD-Typ ist  
 Wenn ein `Platform::Array<T>^` auftritt und T ein POD-Typ ist, können Sie auf den zugrunde liegenden Speicher zugreifen, indem Sie die `get`-Memberfunktion verwenden:  
  
```cpp  
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API  
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));
```  
  
 Wenn T kein POD-Typ ist, verwenden Sie die im folgenden Abschnitt beschriebene Technik, um die Daten mit C++ AMP zu verwenden.  
  
### <a name="windows-runtime-types-ref-classes-and-value-classes"></a>Windows-Runtime-Typen: Verweisklassen und Wertklassen  
 C++ AMP unterstützt keine komplexen Datentypen. Dies umfasst Nicht-POD-Typen sowie alle Typen, die anhand des `ref`- oder `value`-Schlüsselworts deklariert werden. Wenn ein nicht unterstützter Typ in einem `restrict(amp)`-Kontext verwendet wird, wird ein Kompilierzeitfehler generiert.  
  
 Wenn ein nicht unterstützter Typ auftritt, können Sie die interessanten Teile seiner Daten in ein `concurrency::array`-Objekt kopieren. Mit diesem Ansatz des manuellen Kopierens werden nicht nur die Daten für C++ AMP verfügbar gemacht. Er kann zusätzlich die Leistung verbessern, indem der Datenort maximiert und sichergestellt wird, dass Daten, die nicht verwendet werden, nicht in den Beschleuniger kopiert werden. Sie können die Leistung weiter verbessern, indem eine *stagingarray*, dies ist eine besondere Form der `concurrency::array` , die bietet eines Hinweis für die AMP-Laufzeit, die auf das Array für eine häufige Übertragung zwischen ihm und anderen Arrays optimiert werden sollte die angegebenen Beschleuniger.  
  
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
    property int b;  
};  
  
// Some other file  
  
std::vector<pixel_color^> pixels (256);
  
for (pixel_color ^pixel : pixels)   
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
        red_vec[i] = pixels[i]->r;  
        blue_vec[i] = pixels[i]->b;  
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
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen Sie Ihrer ersten uwp-app mit C++](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)   
 [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)


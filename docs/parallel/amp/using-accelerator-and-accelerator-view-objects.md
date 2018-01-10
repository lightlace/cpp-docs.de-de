---
title: Verwenden von Accelerator und "accelerator_view"-Objekten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8cc676407a88979679a362b3d36f361614524432
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="using-accelerator-and-acceleratorview-objects"></a>Verwenden von accelerator-Objekten und accelerator_view-Objekten
Können Sie die [Accelerator](../../parallel/amp/reference/accelerator-class.md) und ["accelerator_view"](../../parallel/amp/reference/accelerator-view-class.md) Klassen an das Gerät oder den Emulator zum Ausführen von C++ AMP-Code auf. Ein System kann über mehrere Geräte oder Emulatoren verfügen, die sich im Hinblick auf die Größe des Arbeitsspeichers, Unterstützung von freigegebenem Arbeitsspeicher, Debugunterstützung oder Unterstützung doppelter Genauigkeit unterscheiden. C++ Accelerated Massive Parallelism (C++ AMP) stellt APIs bereit, die Sie verwenden können, um die verfügbaren Zugriffstasten zu prüfen, eine als Standardvorlage festzulegen, mehrere accelerator_view-Objekte für mehrere Aufrufe von parallel_for_each festzulegen und spezielle Debugaufgaben auszuführen.  
  
## <a name="using-the-default-accelerator"></a>Verwenden der Standardzugriffstaste  
 Die C++ AMP-Laufzeit wählt eine Standardzugriffstaste aus, sofern Sie keinen Code schreiben, um eine bestimmte Taste auszuwählen. Die Laufzeit wählt die Standardzugriffstaste wie folgt aus:  
  
1.  Eine Zugriffstaste, die das Debuggen unterstützt, wenn die Anwendung im Debugmodus ausgeführt wird.  
  
2.  Andernfalls die Zugriffstaste, die von der CPPAMP_DEFAULT_ACCELERATOR-Umgebungsvariablen angegeben wird, falls sie festgelegt ist.  
  
3.  Andernfalls ein nicht emuliertes Gerät.  
  
4.  Andernfalls das Gerät, das über den größte verfügbaren Speicherplatz verfügt.  
  
5.  Andernfalls ein Gerät, das nicht mit der Anzeige verbunden ist.  
  
 Außerdem gibt die Laufzeit den `access_type` `access_type_auto` für die Standardzugriffstaste an. Dies bedeutet, dass die Standardzugriffstaste freigegebenen Arbeitsspeicher verwendet, wenn dieser unterstützt wird und wenn ihre Leistungsmerkmale (Bandbreite und Wartezeit) dem dedizierten (nicht freigegebener) Speicher entsprechen.  
  
 Sie können die Eigenschaften der Standardzugriffstaste bestimmen, indem Sie die Standardzugriffstaste erstellen und ihre Eigenschaften überprüfen. Das folgende Codebeispiel legt den Pfad, die Größe des Zugriffstastenspeichers, die Unterstützung des freigegebenen Arbeitsspeichers, die Unterstützung doppelter Genauigkeit und die eingeschränkte Unterstützung doppelter Genauigkeit für die Standardzugriffstaste fest.  
  
```cpp  
void default_properties() {  
    accelerator default_acc;  
    std::wcout << default_acc.device_path << "\n";  
    std::wcout << default_acc.dedicated_memory << "\n";  
    std::wcout << (accs[i].supports_cpu_shared_memory ?   
        "CPU shared memory: true" : "CPU shared memory: false") << "\n";  
    std::wcout << (accs[i].supports_double_precision ?   
        "double precision: true" : "double precision: false") << "\n";  
    std::wcout << (accs[i].supports_limited_double_precision ?   
        "limited double precision: true" : "limited double precision: false") << "\n";  
}  
 
```  
  
### <a name="cppampdefaultaccelerator-environment-variable"></a>CPPAMP_DEFAULT_ACCELERATOR-Umgebungsvariable  
 Sie können die CPPAMP_DEFAULT_ACCELERATOR-Umgebungsvariable festlegen, um den Pfad `accelerator::device_path` der Standardzugriffstaste anzugeben. Der Pfad ist von der Hardware abhängig. Der folgende Code verwendet die `accelerator::get_all`-Funktion, um eine Liste der verfügbaren Zugriffstasten abzurufen und anschließend den Pfad und die Eigenschaften jeder Zugriffstaste anzuzeigen.  
  
```cpp  
void list_all_accelerators()  
{  
    std::vector<accelerator> accs = accelerator::get_all();  
  
    for (int i = 0; i <accs.size(); i++) {  
        std::wcout << accs[i].device_path << "\n";  
        std::wcout << accs[i].dedicated_memory << "\n";  
        std::wcout << (accs[i].supports_cpu_shared_memory ?   
            "CPU shared memory: true" : "CPU shared memory: false") << "\n";  
        std::wcout << (accs[i].supports_double_precision ?   
            "double precision: true" : "double precision: false") << "\n";  
        std::wcout << (accs[i].supports_limited_double_precision ?   
            "limited double precision: true" : "limited double precision: false") << "\n";  
    }  
}  
```  
  
## <a name="selecting-an-accelerator"></a>Auswählen einer Zugriffstaste  
 Um eine Zugriffstaste auszuwählen, rufen Sie mit der `accelerator::get_all`-Methode eine Liste der verfügbaren Zugriffstasten ab und wählen Sie eine Taste auf Grundlage ihrer Eigenschaften aus. Dieses Beispiel zeigt, wie Sie die Zugriffstaste mit dem größten Arbeitsspeicher auswählen:  
  
```cpp  
void pick_with_most_memory()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
    accelerator acc_chosen = accs[0];  
    
    for (int i = 0; i <accs.size(); i++) {  
        if (accs[i].dedicated_memory> acc_chosen.dedicated_memory) {  
            acc_chosen = accs[i];  
        }  
    }  
 
    std::wcout << "The accelerator with the most memory is "    
        << acc_chosen.device_path << "\n"  
        << acc_chosen.dedicated_memory << ".\n";  
}  
```  
  
> [!NOTE]
>  Eine der Zugriffstasten, die von `accelerator::get_all` zurückgegeben werden, ist die CPU-Zugriffstaste. Sie können auf der CPU-Zugriffstaste keinen Code ausführen. Um die CPU-Zugriffstaste herauszufiltern, vergleichen Sie den Wert von der [Device_path](reference/accelerator-class.md#device_path) -Eigenschaft der Zugriffstaste, die von zurückgegeben wird `accelerator::get_all` mit dem Wert der [Accelerator:: cpu_accelerator](reference/accelerator-class.md#cpu_accelerator). Weitere Informationen finden Sie im Abschnitt "Spezielle Zugriffstasten" in diesem Artikel.  
  
## <a name="shared-memory"></a>Freigegebener Arbeitsspeicher  
 Freigegebener Arbeitsspeicher ist der Arbeitsspeicher, auf den sowohl die CPU als auch die Zugriffstaste zugreifen kann. Durch die Verwendung von freigegebenem Arbeitsspeicher entfällt bzw. reduziert sich der Mehraufwand zum Kopieren von Daten zwischen CPU und der Zugriffstaste erheblich. Obwohl der Arbeitsspeicher freigegeben wird, kann darauf nicht von CPU und der Zugriffstaste gleichzeitig zugegriffen werden. In diesem Fall kommt es zu einem nicht definierten Verhalten. Die Zugriffstaste Eigenschaft [Supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) gibt `true` , wenn die Zugriffstaste freigegebenen Arbeitsspeicher unterstützt und die [Default_cpu_access_type](reference/accelerator-class.md#default_cpu_access_type) Eigenschaft ruft die standardmäßigen ab[Access_type](reference/concurrency-namespace-enums-amp.md#access_type) für den auf belegten Speicherplatz der `accelerator`– z. B. `array`s, die mit der `accelerator`, oder `array_view` Objekte zugegriffen wird, auf die `accelerator`. 
  
 Die C++ AMP-Laufzeit wählt automatisch den besten standardmäßigen `access_type` für jedes `accelerator`-Objekt aus. Die Leistungsmerkmale (Bandbreite und Wartezeit) von freigegebenem Arbeitsspeicher können beim Lesen und/oder Schreiben über die CPU jedoch schlechter sein als die des dedizierten (nicht freigegebenen) Zugriffstastenspeichers. Wenn freigegebener Arbeitsspeicher beim Lesen und Schreiben über die CPU die gleiche Leistung zeigt wie dedizierter Arbeitsspeicher verwendet die Laufzeit standardmäßig `access_type_read_write`; andernfalls wählt die Laufzeit einen konservativeren standardmäßigen `access_type` aus und ermöglicht es der Anwendung, ihn zu überschreiben, wenn die Speicherzugriffmuster seiner Berechnungskernel von einem anderen `access_type` profitieren.  
  
 Das folgende Codebeispiel zeigt, wie bestimmt wird, ob die Standardzugriffstaste freigegebenen Arbeitsspeicher unterstützt, und der Standardzugriffstyp überschrieben und ein `accelerator_view`-Objekt daraus erstellt wird.  
  
```cpp  
#include <amp.h>  
#include <iostream>  
  
using namespace Concurrency;  
  
int main()  
{  
    accelerator acc = accelerator(accelerator::default_accelerator);  
  
    // Early out if the default accelerator doesn’t support shared memory.  
    if (!acc.supports_cpu_shared_memory)  
    {  
        std::cout << "The default accelerator does not support shared memory" << std::endl;  
        return 1;  
    }  
  
    // Override the default CPU access type.  
    acc.set_default_cpu_access_type(access_type_read_write);  
  
    // Create an accelerator_view from the default accelerator. The  
    // accelerator_view reflects the default_cpu_access_type of the  
    // accelerator it’s associated with.  
    accelerator_view acc_v = acc.default_view;  
}  
```  
  
 Ein `accelerator_view`-Objekt spiegelt immer das `default_cpu_access_type`-Objekt des `accelerator`-Objekts wider, dem es zugeordnet ist, und stellt keine Schnittstelle zum Überschreiben oder Ändern seines `access_type`-Objekts bereit.  
  
## <a name="changing-the-default-accelerator"></a>Ändern der Standardzugriffstaste  
 Sie können die Standardzugriffstaste ändern, indem Sie die `accelerator::set_default`-Methode aufrufen. Sie können die Standardzugriffstaste nur einmal pro App-Ausführung ändern. Die Änderung muss erfolgen, bevor Code auf dem GPU-Computer ausgeführt wird. Alle folgenden Funktionsaufrufe zum Ändern der Zugriffstaste geben `false` zurück. Wenn Sie eine andere Tastenkombination in einem Aufruf von `parallel_for_each` verwenden möchten, lesen Sie den Abschnitt "Verwenden mehrerer Zugriffstasten" in diesem Artikel. Im folgenden Codebeispiel wird die Standardzugriffstaste auf eine Taste festgelegt, die nicht emuliert, nicht mit einer Anzeige verbunden ist und doppelte Genauigkeit unterstützt.  
  
```cpp  
bool pick_accelerator()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
    accelerator chosen_one;  
 
    auto result = std::find_if(accs.begin(), accs.end(), 
        [] (const accelerator& acc) {  
            return !acc.is_emulated && 
                acc.supports_double_precision && 
                !acc.has_display;  
        });
  
    if (result != accs.end()) {  
        chosen_one = *(result);
    }
  
    std::wcout <<chosen_one.description <<std::endl;  
    bool success = accelerator::set_default(chosen_one.device_path);
    return success;  
}  
```  
  
## <a name="using-multiple-accelerators"></a>Verwenden mehrerer Zugriffstasten  
 Es gibt zwei Möglichkeiten, mehrere Zugriffstasten in Ihrer App zu verwenden:  

-   Sie können übergeben `accelerator_view` -Objekten, die Aufrufe an die [Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) Methode.  
  
-   Sie können ein `array`-Objekt mit einem bestimmten `accelerator_view`-Objekts erstellen. Die C+ AMP-Laufzeit wählt das `accelerator_view`-Objekt aus dem aufgezeichneten `array`-Objekt im Lambda-Ausdruck aus.  
  
## <a name="special-accelerators"></a>Spezielle Zugriffstasten  
 Die Gerätepfade von drei speziellen Zugriffstasten sind als Eigenschaften der `accelerator`-Klasse verfügbar:  
  
- [Accelerator:: direct3d_ref-Datenmember](reference/accelerator-class.md#direct3d_ref): diese Zugriffstaste Singlethread-mithilfe von Software auf der CPU um eine generischen Grafikkarte zu emulieren. Sie wird standardmäßig für das Debuggen verwendet, ist jedoch in der Produktion nicht vorteilhaft, da sie langsamer ist als die Hardwarezugriffstasten. Außerdem ist sie nur im DirectX SDK und im Windows SDK verfügbar und wird mit großer Wahrscheinlichkeit nicht auf den Computern der Kunden installiert. Weitere Informationen finden Sie unter [Debuggen von GPU-Code](/visualstudio/debugger/debugging-gpu-code).  
  
- [Accelerator:: direct3d_warp-Datenmember](reference/accelerator-class.md#direct3d_warp): diese Zugriffstaste bietet eine alternative Lösung zum Ausführen des C++ AMP-Codes auf Multikern-CPUs, die Streaming SIMD Extensions (SSE) verwenden.  
  
- [Accelerator:: cpu_accelerator-Datenmember](reference/accelerator-class.md#cpu_accelerator): Sie können diese Zugriffstaste für die Einrichtung der staging-Arrays verwenden. Sie kann keinen C++ AMP-Code ausführen. Weitere Informationen finden Sie unter der [Stagingarrays in C++ AMP](http://go.microsoft.com/fwlink/p/?linkId=248485) Beitrag im Blog zur parallelen Programmierung in systemeigenem Code.  
  
## <a name="interoperability"></a>Interoperabilität  
 Die C++ AMP-Laufzeit unterstützt die Interoperabilität zwischen den `accelerator_view` Klasse und die Direct3D [ID3D11Device-Schnittstelle](http://go.microsoft.com/fwlink/p/?linkId=248488). Die [Create_accelerator_view](reference/concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view) -Methode übernimmt ein `IUnknown` -Schnittstelle und gibt ein `accelerator_view` Objekt. Die [Get_device](http://msdn.microsoft.com/en-us/8194125e-8396-4d62-aa8a-65831dea8439) -Methode übernimmt ein `accelerator_view` -Objekt und gibt eine `IUknown` Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Debuggen von GPU-Code](/visualstudio/debugger/debugging-gpu-code)   
 [accelerator_view-Klasse](../../parallel/amp/reference/accelerator-view-class.md)

---
title: "&#220;bersicht &#252;ber C++ AMP"
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
helpviewer_keywords: 
  - "C++ Accelerated Massive Parallelism, Anforderungen"
  - "C++ Accelerated Massive Parallelism, Architektur"
  - "C++ AMP"
  - "C++ Accelerated Massive Parallelism, Übersicht"
  - "C++ Accelerated Massive Parallelism"
ms.assetid: 9e593b06-6e3c-43e9-8bae-6d89efdd39fc
caps.latest.revision: 60
caps.handback.revision: "60"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;bersicht &#252;ber C++ AMP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C++ Accelerated Massive Parallelism (C++ AMP) beschleunigt die Ausführung von C++-Code, indem die Vorteile Daten parallel verarbeitender Hardware, beispielsweise ein Grafikprozessor (Graphics Processing Unit, GPU) auf einer separaten Grafikkarte, genutzt werden. Sie können mithilfe von C++ AMP mehrdimensionale Datenalgorithmen programmieren, sodass die Ausführung durch die parallele Verarbeitung auf heterogener Hardware beschleunigt werden kann. Das C++ AMP-Programmiermodell umfasst mehrdimensionale Arrays, Indizierung, Arbeitsspeicherübertragung, Kacheln und eine Bibliothek mathematischer Funktionen. Sie können C++ AMP-Spracherweiterungen verwenden, um zu steuern, wie Daten von der CPU zur GPU und umgekehrt verschoben werden, sodass Sie die Leistung verbessern können.  
  
## <a name="system-requirements"></a>Systemanforderungen  
  
- [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../../parallel/amp/includes/winsvr08_r2_md.md)] oder [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)]  
  
-   DirectX 11-Funktionsebene 11.0 oder aktuellere Hardware  
  
-   Für das Debuggen im Softwareemulator ist [!INCLUDE[win8](../../build/includes/win8_md.md)] oder [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)] erforderlich. Für das Debuggen auf der Hardware müssen Sie die Treiber für Ihre Grafikkarte installieren. Weitere Informationen finden Sie unter [GPU-Code Debuggen](../Topic/Debugging%20GPU%20Code.md).  
  
## <a name="introduction"></a>Einführung  
 Die folgenden beiden Beispielen veranschaulichen die primären Komponenten von C++ AMP. Angenommen, Sie möchten die entsprechenden Elemente zweier eindimensionaler Arrays addieren. Angenommen, Sie möchten möglicherweise hinzufügen `{1, 2, 3, 4, 5}` und `{6, 7, 8, 9, 10}` abrufen `{7, 9, 11, 13, 15}`. Ohne C++ AMP zu verwenden, schreiben Sie den folgenden Code, um die Zahlen zu addieren und die Ergebnisse anzuzeigen.  
  
```cpp  
  
#include <iostream>  
  
void StandardMethod() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        sumCPP[idx] = aCPP[idx] + bCPP[idx];  
    }  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        std::cout << sumCPP[idx] << "\n";  
    }  
}  
  
```  
  
 Die folgenden Teile des Codes sind wichtig:  
  
-   Daten: Die Daten bestehen aus drei Arrays. Alle haben den gleichen Rang (Eins) und die gleiche Länge (Fünf).  
  
-   Iteration: Die erste `for`-Schleife stellt einen Mechanismus für das Durchlaufen der Elemente in den Arrays bereit. Der Code, der zur Berechnung der Summen ausgeführt werden soll, befindet sich im ersten `for`-Block.  
  
-   Index: Über die Variable `idx` wird auf die einzelnen Elemente der Arrays zugegriffen.  
  
 Bei Verwendung von C++ AMP können Sie stattdessen den folgenden Code schreiben.  
  
```cpp  
  
#include <amp.h>  
#include <iostream>  
using namespace concurrency;  
  
const int size = 5;  
  
void CppAmpMethod() {  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[size];  
  
    // Create C++ AMP objects.  
    array_view<const int, 1> a(size, aCPP);  
    array_view<const int, 1> b(size, bCPP);  
    array_view<int, 1> sum(size, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(   
        // Define the compute domain, which is the set of threads that are created.  
        sum.extent,   
        // Define the code to run on each thread on the accelerator.  
 [=](index<1> idx) restrict(amp)  
    {  
        sum[idx] = a[idx] + b[idx];  
    }  
    );  
  
    // Print the results. The expected output is "7, 9, 11, 13, 15".  
    for (int i = 0; i < size; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 Es sind zwar die gleichen grundlegenden Elemente vorhanden, es werden jedoch C++ AMP-Konstrukte verwendet:  
  
-   Daten: Verwenden Sie C++-Arrays, um drei C++ AMP erstellen [Array_view](../../parallel/amp/reference/array-view-class.md) Objekte. Sie stellen vier Werte zur Verfügung, um ein `array_view`-Objekt zu erstellen: die Datenwerte, den Rang, den Elementtyp und die Länge des `array_view`-Objekts in jeder Dimension. Der Rang und der Typ werden als Typparameter übergeben. Die Daten und die Länge werden als Konstruktorparameter übergeben. In diesem Beispiel ist das an den Konstruktor übergebene C++-Array eindimensional. Der Rang und die Länge werden verwendet, um die rechteckige Form der Daten im `array_view`-Objekt zu erstellen, und die Datenwerte werden verwendet, um das Array zu füllen. Die Laufzeitbibliothek enthält auch die [array-Klasse](../../parallel/amp/reference/array-class.md), die über eine Schnittstelle, die ähnelt verfügt die `array_view` -Klasse und wird später in diesem Artikel erläutert.  
  
-   Iteration: Die [Parallel_for_each-Funktion (C++-AMP)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) bietet einen Mechanismus zum Durchlaufen der Datenelemente oder *compute-Domäne*. In diesem Beispiel wird die Compute-Domäne durch `sum.extent` angegeben. Der Code, der ausgeführt werden soll in einem Lambda-Ausdruck enthalten ist oder *Kernelfunktion*. Die Anweisung `restrict(amp)` gibt an, dass nur die Teilmenge der Programmiersprache C++ verwendet wird, die mit C++ AMP beschleunigt werden kann.  
  
-   Index: Die [index-Klasse](../../parallel/amp/reference/index-class.md) Variable `idx`, mit dem Rang eins der Rang übereinstimmt deklariert wird, die `array_view` Objekt. Mithilfe des Index kann auf die einzelnen Elemente der `array_view`-Objekte zugegriffen werden.  
  
## <a name="shaping-and-indexing-data-index-and-extent"></a>Strukturieren und Indizieren von Daten: Index und Umfang  
 Sie müssen die Datenwerte definieren und die Form der Daten deklarieren, bevor Sie den Kernelcode ausführen können. Alle Daten werden als Array (rechteckig) definiert, und Sie können das Array mit einem die oft ausgegebene Befehlszeilen  Rang (Anzahl der Dimensionen) definieren. Die Daten können in jeder Dimension von beliebiger Größe sein.  
  
### <a name="index-class"></a>index-Klasse  
 Die [index-Klasse](../../parallel/amp/reference/index-class.md) Gibt eine Position in der `array` oder `array_view` Objekt, indem der Offset vom Ursprung in jeder Dimension in einem Objekt gekapselt. Wenn Sie auf eine Position im Array zugreifen, übergeben Sie ein `index`-Objekt an den Indizierungsoperator `[]` statt einer Liste mit ganzzahligen Indizes. Sie können die Elemente in jeder Dimension zugreifen, mit der [Array::Operator()-Operator](../Topic/array::operator\(\)%20Operator.md) oder [array_view::Operator()-Operator](../Topic/array_view::operator\(\)%20Operator.md).  
  
 Im folgenden Beispiel wird ein eindimensionaler Index erstellt, der das dritte Element in einem eindimensionalen `array_view`-Objekt angibt. Der Index wird verwendet, um das dritte Element im `array_view`-Objekt auszugeben. Die Ausgabe lautet 3.  
  
```cpp  
 
int aCPP[] = {1, 2, 3, 4, 5};  
array_view<int, 1> a(5, aCPP);

index<1> idx(2);

std::cout <<a[idx] <<"\n";    
// Output: 3  
 
```  
  
 Im folgenden Beispiel wird ein zweidimensionaler Index erstellt, der das Element angibt, bei dem die Zeile = 1 und die Spalte = 2 in einem zweidimensionalen `array_view`-Objekt ist. Der erste Parameter im `index`-Konstruktor ist die Zeilenkomponente, und der zweite Parameter ist die Spaltenkomponente. Die Ausgabe ist 6.  
  
```cpp  
 
int aCPP[] = {1, 2, 3,  
    4, 5, 6};  
array_view<int, 2> a(2, 3, aCPP);

index<2> idx(1, 2);

std::cout <<a[idx] <<"\n";  
// Output: 6  
 
```  
  
 Im folgenden Beispiel wird ein dreidimensionaler Index erstellt, der das Element angibt, bei dem die Tiefe = 0, die Zeile = 1 und die Spalte = 3 in einem dreidimensionalen `array_view`-Objekt ist. Beachten Sie, dass der erste Parameter die Tiefenkomponente, der zweite Parameter die Zeilenkomponente und der dritte Parameter die Spaltenkomponente ist. Die Ausgabe ist 8.  
  
```cpp  
 
int aCPP[] = {  
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,   
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};  
 
array_view<int, 3> a(2, 3, 4, aCPP);

// Specifies the element at 3, 1, 0.  
index<3> idx(0, 1, 3);

std::cout <<a[idx] <<"\n";  
 
// Output: 8  
 
```  
  
### <a name="extent-class"></a>extent-Klasse  
 Die [Extent-Klasse](../../parallel/amp/reference/extent-class-cpp-amp.md) Gibt die Länge der Daten in jeder Dimension der `array` oder `array_view` Objekt. Sie können einen Wertebereich erstellen und diesen verwenden, um ein `array`- oder `array_view`-Objekt zu erstellen. Sie können den Wertebereich eines vorhandenen `array`- oder `array_view`-Objekts auch abrufen. Im folgenden Beispiel wird die Länge des Wertebereichs in jeder Dimension eines `array_view`-Objekts ausgegeben.  
  
```cpp  
 
int aCPP[] = {  
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,   
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};  
// There are 3 rows and 4 columns, and the depth is two.  
array_view<int, 3> a(2, 3, 4, aCPP);

std::cout <<"The number of columns is " <<a.extent[2] <<"\n";  
std::cout <<"The number of rows is " <<a.extent[1] <<"\n";  
std::cout <<"The depth is " <<a.extent[0]<<"\n";  
std::cout <<"Length in most significant dimension is " <<a.extent[0] <<"\n";  
 
```  
  
 Im folgenden Beispiel wird ein `array_view`-Objekt erstellt, das die gleichen Dimensionen wie das Objekt im vorherigen Beispiel hat, aber in diesem Beispiel wird ein `extent`-Objekt statt expliziter Parameter im `array_view`-Konstruktor verwendet.  
  
```cpp  
 
int aCPP[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24};  
extent<3> e(2, 3, 4);

array_view<int, 3> a(e, aCPP);

std::cout <<"The number of columns is " <<a.extent[2] <<"\n";  
std::cout <<"The number of rows is " <<a.extent[1] <<"\n";  
std::cout <<"The depth is " <<a.extent[0] <<"\n";  
 
```  
  
## <a name="moving-data-to-the-accelerator-array-and-arrayview"></a>Verschieben von Daten in die Beschleunigung: array und array_view  
 In der Laufzeitbibliothek sind zwei Datencontainer definiert, die verwendet werden, um Daten in den Beschleuniger zu verschieben. Sie sind der [array-Klasse](../../parallel/amp/reference/array-class.md) und der [Array_view-Klasse](../../parallel/amp/reference/array-view-class.md). Die `array`-Klasse ist eine Containerklasse, die eine tiefe Kopie der Daten erstellt, wenn das Objekt erstellt wird. Die `array_view`-Klasse ist eine Wrapperklasse, die die Daten kopiert, wenn die Kernelfunktion auf die Daten zugreift. Wenn die Daten auf dem Quellgerät benötigt werden, werden sie zurückkopiert.  
  
### <a name="array-class"></a>array-Klasse  
 Wenn ein `array`-Objekt erstellt wird und Sie einen Konstruktor verwenden, der einen Zeiger auf das Dataset enthält, wird im Beschleuniger eine tiefe Kopie der Daten erstellt. Die Kernelfunktion ändert die Kopie im Beschleuniger. Wenn die Ausführung der Kernelfunktion beendet ist, müssen Sie die Daten zurück in die Quelldatenstruktur kopieren. Im folgenden Beispiel wird jedes Element in einem Vektor mit 10 multipliziert. Nachdem die Kernelfunktion beendet ist, den [vektorkonvertierungsoperator]--Brokenlink--(.. /Topic/Array::Operator%20std::Vector%3Cvalue_type%3e%20Operator.MD)is verwendet, um die Daten zurück in das Vektorobjekt zu kopieren.  
  
```cpp  
 
std::vector<int> data(5);

for (int count = 0; count <5; count++)   
{  
    data[count] = count;  
}  
 
array<int, 1> a(5, data.begin(), data.end());

 
parallel_for_each(
    a.extent, 
 [=, &a](index<1> idx) restrict(amp)  
 {  
    a[idx] = a[idx]* 10;  
 });

 
data = a;  
for (int i = 0; i <5; i++)   
{  
    std::cout <<data[i] <<"\n";  
}  
 
```  
  
### <a name="arrayview-class"></a>array_view-Klasse  
 Die `array_view`-Klasse verfügt über fast dieselben Member wie die `array`-Klasse, aber das zugrunde liegende Verhalten ist unterschiedlich. Die Daten, die dem `array_view`-Konstruktor übergeben werden, werden nicht wie beim `array`-Konstruktor im Grafikprozessor repliziert. Stattdessen werden die Daten in den Beschleuniger kopiert, wenn die Kernelfunktion ausgeführt wird. Wenn Sie zwei `array_view`-Objekte erstellen, die dieselben Daten verwenden, verweisen daher beide `array_view`-Objekte auf denselben Arbeitsspeicherbereich. In diesem Fall müssen Sie jeden Multithreaded-Zugriff synchronisieren. Der Hauptvorteil bei der Verwendung der `array_view`-Klasse besteht darin, dass Daten nur verschoben werden, wenn es erforderlich ist.  
  
### <a name="comparison-of-array-and-arrayview"></a>Vergleich von "array" und "array_view"  
 In der folgenden Tabelle werden die Übereinstimmungen und Unterschiede zwischen der `array`- und der `array_view`-Klasse zusammengefasst.  
  
|Beschreibung|array-Klasse|array_view-Klasse|  
|-----------------|-----------------|-----------------------|  
|Zeitpunkt der Bestimmung des Rangs|Beim Kompilieren|Beim Kompilieren|  
|Zeitpunkt der Bestimmung des Wertebereichs|Zur Laufzeit|Zur Laufzeit|  
|Form|Rechteckig|Rechteckig|  
|Datenspeicher|Ist ein Datencontainer|Ist ein Datenwrapper|  
|Kopieren|Explizit und tiefe Kopie während der Definition|Implizite Kopie, wenn von der Kernelfunktion darauf zugegriffen wird|  
|Abrufen von Daten|Durch Kopieren der Arraydaten zurück in ein Objekt im CPU-Thread|Durch den direkten Zugriff von der `array_view` -Objekts oder durch Aufrufen der [array_view:: Synchronize-Methode](../Topic/array_view::synchronize%20Method.md) weiterhin auf die Daten im ursprünglichen Container zugreifen.|  
  
### <a name="shared-memory-with-array-and-arrayview"></a>Freigegebener Speicher mit array und array_view  
 Freigegebener Arbeitsspeicher ist der Arbeitsspeicher, auf den sowohl die CPU als auch die Zugriffstaste zugreifen kann. Durch die Verwendung von freigegebenem Arbeitsspeicher entfällt bzw. reduziert sich der Mehraufwand zum Kopieren von Daten zwischen CPU und der Zugriffstaste erheblich. Obwohl der Arbeitsspeicher freigegeben wird, kann darauf nicht von CPU und der Zugriffstaste gleichzeitig zugegriffen werden. In diesem Fall kommt es zu einem nicht definierten Verhalten.  
  
 Mithilfe von `array`-Objekten kann die Verwendung von freigegebenem Arbeitsspeicher präzise gesteuert werden, sofern die zugeordnete Zugriffstaste dies unterstützt. Ob eine Zugriffstaste freigegebenen Arbeitsspeicher unterstützt wird von der Zugriffstaste bestimmt [Supports_cpu_shared_memory](../Topic/accelerator::supports_cpu_shared_memory%20Data%20Member.md) ab `true` Wenn freigegebener Arbeitsspeicher unterstützt. Wenn freigegebener Arbeitsspeicher unterstützt wird, der Standardwert [Access_type-Enumeration](../Topic/access_type%20Enumeration.md) für Speicher wird durch Zuordnungen auf der Zugriffstaste bestimmt die `default_cpu_access_type` Eigenschaft. Standardmäßig wird für `array`- und `array_view`-Objekte der gleiche `access_type` wie für das primäre zugeordnete `accelerator`-Objekt verwendet.  
  
 Durch Festlegen der [Array:: cpu_access_type-Datenmember](../Topic/array::cpu_access_type%20Data%20Member.md) Eigenschaft ein `array` explizit, Sie können präzise steuern und Verwendung von freigegebenem Speicher verwendet wird, so dass Sie die app für die Hardware die Leistungsmerkmale, basierend auf der Speicherzugriffsmuster seiner berechnungskernel optimieren können. Ein `array_view`-Objekt verfügt über das gleiche `cpu_access_type`-Objekt wie das `array`, dem es zugeordnet ist; oder wenn das array_view-Objekt ohne eine Datenquelle erstellt wird, spiegelt sein `access_type`-Objekt die Umgebung, in der die erste Speicherbelegung erfolgte. Das bedeutet, dass es sich bei einem Erstzugriff durch den Host (CPU) so verhält, als ob es über eine CPU-Datenquelle erstellt wurde und es gibt das `access_type`-Objekt des  `accelerator_view`-Objekts frei, das durch die Erfassung zugeordnet wird. Wenn jedoch auf sie zunächst von einem `accelerator_view`-Objekt zugegriffen wird, dann verhält es sich, als ob es über ein `array`-Objekt erstellt wurde, das auf diesem `accelerator_view`-Objekt erstellt wurde. Es wird das `array`-Objekt des `access_type`-Objekts freigegeben.  
  
 Das folgende Codebeispiel zeigt, wie Sie bestimmen, ob die Standardzugriffstaste freigegebenen Arbeitsspeicher unterstützt, und erstellt anschließend mehrere Arrays mit verschiedenen cpu_access_type-Konfigurationen.  
  
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
  acc.default_cpu_access_type = access_type_read_write  
  
  // Create an accelerator_view from the default accelerator. The  
  // accelerator_view inherits its default_cpu_access_type from acc.  
  accelerator_view acc_v = acc.default_view;  
  
  // Create an extent object to size the arrays.  
  extent<1> ex(10);  
  
  // Input array that can be written on the CPU.  
  array<int, 1> arr_w(ex, acc_v, access_type_write);  
  
  // Output array that can be read on the CPU.  
  array<int, 1> arr_r(ex, acc_v, access_type_read);  
  
  // Read-write array that can be both written to and read from on the CPU.  
  array<int, 1> arr_rw(ex, acc_v, access_type_read_write);  
}  
  
```  
  
## <a name="executing-code-over-data-parallelforeach"></a>Ausführen von Code zu Daten: parallel_for_each  
 Die [Parallel_for_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) Funktion definiert den Code, der von der Beschleuniger die Daten in der `array` oder `array_view` Objekt. Betrachten Sie den folgenden Code aus der Einführung dieses Themas.  
  
```cpp  
  
#include <amp.h>  
#include <iostream>  
using namespace concurrency;  
  
void AddArrays() {  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5] = {0, 0, 0, 0, 0};  
  
    array_view<int, 1> a(5, aCPP);  
    array_view<int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
  
    parallel_for_each(  
        sum.extent,   
 [=](index<1> idx) restrict(amp)  
        {  
            sum[idx] = a[idx] + b[idx];  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 Die `parallel_for_each`-Methode akzeptiert zwei Argumente, eine Compute-Domäne und einen Lambda-Ausdruck.  
  
 Die *compute-Domäne* ist ein `extent` Objekt oder ein `tiled_extent` Objekt, das den Satz von Threads zum Erstellen für die parallele Ausführung definiert. Für jedes Element in der Compute-Domäne wird ein Thread generiert. In diesem Fall ist das `extent`-Objekt eindimensional und hat fünf Elemente. Daher werden fünf Threads gestartet.  
  
 Die *Lambda-Ausdruck* definiert den Code, der in jedem Thread ausgeführt. Die Erfassungsklausel `[=]`, gibt an, dass der Text des Lambda-Ausdrucks zugreift alle erfasste Variablen anhand des Werts in diesem Fall sind `a`, `b`, und `sum`. In diesem Beispiel wird in der Parameterliste eine eindimensionale `index`-Variable mit dem Namen `idx` erstellt. Der Wert von `idx[0]` beträgt im ersten Thread null und wird in jedem nachfolgenden Thread um eins erhöht. Die Anweisung `restrict(amp)` gibt an, dass nur die Teilmenge der Programmiersprache C++ verwendet wird, die mit C++ AMP beschleunigt werden kann.  In die eingeschränkten Funktionen mit dem Modifizierer einschränken beschriebenen [einschränken (C++-AMP)](../../cpp/restrict-cpp-amp.md). Weitere Informationen finden Sie unter [Lambda-Ausdruckssyntax](../../cpp/lambda-expression-syntax.md).  
  
 Der Lambdaausdruck kann den auszuführenden Code enthalten oder eine separate Kernelfunktion aufrufen. Die Kernelfunktion muss den `restrict(amp)`-Modifizierer enthalten. Das folgende Beispiel entspricht dem vorherigen Beispiel, jedoch wird eine separate Kernelfunktion aufgerufen.  
  
```cpp  
  
#include <amp.h>  
#include <iostream>  
using namespace concurrency;  
  
void AddElements(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)  
{  
    sum[idx] = a[idx] + b[idx];  
}  
  
void AddArraysWithFunction() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5] = {0, 0, 0, 0, 0};  
  
    array_view<int, 1> a(5, aCPP);  
    array_view<int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
  
    parallel_for_each(  
        sum.extent,   
 [=](index<1> idx) restrict(amp)  
        {  
            AddElements(idx, sum, a, b);  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
## <a name="accelerating-code-tiles-and-barriers"></a>Beschleunigen von Code: Kacheln und Barrieren  
 Sie können eine zusätzliche Beschleunigung erreichen, indem Sie Kacheln verwenden. Kacheln unterteilt die Threads in gleiche rechteckige Teilmengen oder *Kacheln*. Sie bestimmen die geeignete Kachelgröße auf der Basis des Datasets und des Algorithmus, den Sie programmieren. Für jeden Thread, haben Sie Zugriff auf den *globalen* Position eines Datenelements relativ zum gesamten `array` oder `array_view` und den Zugriff auf die *lokale* Position relativ zu der Kachel. Die Verwendung des lokalen Indexwerts vereinfacht den Code, da Sie keinen Code schreiben müssen, um globale Indexwerte in lokale zu übersetzen. Um Kacheln zu verwenden, rufen die [Extent:: Tile-Methode](../Topic/extent::tile%20Method.md) in der Compute-Domäne, in der `parallel_for_each` -Methode, und Verwenden einer [Tiled_index](../../parallel/amp/reference/tiled-index-class.md) -Objekt im Lambda-Ausdruck.  
  
 In typischen Anwendungen sind die Elemente in einer Kachel auf irgendeine Weise verknüpft, und der Code muss in der gesamten Kachel auf Werte zugreifen und diese verfolgen. Verwenden der [Tile_static-Schlüsselwort](../../cpp/tile-static-keyword.md) Schlüsselwort und die [tile_barrier:: Wait-Methode](../Topic/tile_barrier::wait%20Method.md) dies zu erreichen. Der Gültigkeitsbereich einer Variablen, die das Schlüsselwort `tile_static` aufweist, erstreckt sich über eine komplette Kachel, und für jede Kachel wird eine Instanz der Variablen erstellt. Sie müssen sich um die Synchronisierung des Kachel-Threadzugriffs auf die Variable kümmern. Die [tile_barrier:: Wait-Methode](../Topic/tile_barrier::wait%20Method.md) beendet die Ausführung des aktuellen Threads, bis alle Threads in der Kachel den Aufruf erreicht haben `tile_barrier::wait`. Damit können Sie Werte der gesamten Kachel akkumulieren, indem Sie `tile_static`-Variablen verwenden. Anschließend können Sie alle Berechnungen beenden, für die der Zugriff auf alle Werte erforderlich ist.  
  
 Im folgenden Diagramm wird ein zweidimensionales Array mit Samplingdaten dargestellt, das in Kacheln angeordnet ist.  
  
 ![Indexwerte in einer gekachelten Erweiterung](../../parallel/amp/media/camptiledgridexample.png "CampTiledGridExample")  
  
 Im folgenden Codebeispiel werden die Samplingdaten aus dem vorherigen Diagramm verwendet. Im Code wird jeder Wert in der Kachel durch den Durchschnitt der Werte in der Kachel ersetzt.  
  
```cpp  
 
// Sample data:  
int sampledata[] = {  
    2, 2, 9, 7, 1, 4,  
    4, 4, 8, 8, 3, 4,  
    1, 5, 1, 2, 5, 2,  
    6, 8, 3, 2, 7, 2};  
 
// The tiles:  
// 2 2    9 7    1 4  
// 4 4    8 8    3 4  
//  
// 1 5    1 2    5 2  
// 6 8    3 2    7 2  
 
// Averages:  
int averagedata[] = {   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
};  
 
array_view<int, 2> sample(4, 6, sampledata);

array_view<int, 2> average(4, 6, averagedata);

 
parallel_for_each(*// Create threads for sample.extent and divide the extent into 2 x 2 tiles.  
    sample.extent.tile<2,2>(), 
 [=](tiled_index<2,2> idx) restrict(amp)  
 { *// Create a 2 x 2 array to hold the values in this tile.  
    tile_static int nums[2][2]; *// Copy the values for the tile into the 2 x 2 array.  
    nums[idx.local[1]][idx.local[0]] = sample[idx.global]; *// When all the threads have executed and the 2 x 2 array is complete, find the average.  
    idx.barrier.wait();
int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1]; *// Copy the average into the array_view.  
    average[idx.global] = sum / 4;  
 });

 
for (int i = 0; i <4; i++) {  
    for (int j = 0; j <6; j++) {  
    std::cout <<average(i,j) <<" ";  
 }  
    std::cout <<"\n";  
}  
 
// Output:  
// 3 3 8 8 3 3  
// 3 3 8 8 3 3  
// 5 5 2 2 4 4  
// 5 5 2 2 4 4  
 
```  
  
## <a name="math-libraries"></a>Mathematische Bibliotheken  
 C++ AMP enthält zwei mathematische Bibliotheken. Die Bibliothek mit doppelter Genauigkeit in die [Concurrency:: precise_math-Namespace](../../parallel/amp/reference/concurrency-precise-math-namespace.md) bietet Unterstützung für Funktionen mit doppelter Genauigkeit. Sie unterstützt auch Funktionen mit einfacher Genauigkeit, obwohl die Unterstützung doppelter Genauigkeit auf der Hardware noch benötigt wird. Entspricht der [Spezifikation C99 (ISO/IEC 9899)](http://go.microsoft.com/fwlink/LinkId=225887). Der Beschleuniger muss doppelte Genauigkeit vollständig unterstützen. Sie können bestimmen, unabhängig davon, ob es durch Überprüfen des Werts von der [Accelerator:: supports_double_precision-Datenmember](../Topic/accelerator::supports_double_precision%20Data%20Member.md). Schnelle Math-Bibliothek in der [Concurrency:: fast_math-Namespace](../../parallel/amp/reference/concurrency-fast-math-namespace.md), einen anderen Satz von mathematischen Funktionen enthält. Diese Funktionen, die nur `float`-Operanden unterstützen, werden schneller ausgeführt, sind jedoch nicht so präzise wie die Funktionen in der mathematischen Bibliothek mit doppelter Genauigkeit. Die Funktionen sind in der Headerdatei \<amp_math.h> enthalten und alle mit `restrict(amp)` deklariert. Die Funktionen in der \< Cmath> Header-Datei importiert werden sowohl die `fast_math` und `precise_math` Namespaces. Die `restrict` -Schlüsselwort verwendet, um die Unterscheidung der \< Cmath> Version und die C++ AMP-Version. Der folgende Code berechnet mithilfe der schnellen Methode den Logarithmus zur Basis 10 jedes Werts, der in der Berechnungsdomäne enthalten ist.  
  
```cpp  
  
#include <amp.h>  
#include <amp_math.h>  
#include <iostream>  
using namespace concurrency;  
  
void MathExample() {  
  
    double numbers[] = { 1.0, 10.0, 60.0, 100.0, 600.0, 1000.0 };  
    array_view<double, 1> logs(6, numbers);  
  
    parallel_for_each(  
        logs.extent,  
 [=] (index<1> idx) restrict(amp) {  
            logs[idx] = concurrency::fast_math::log10(logs[idx]);  
        }  
    );  
  
    for (int i = 0; i < 6; i++) {  
        std::cout << logs[i] << "\n";  
    }  
}  
  
```  
  
## <a name="graphics-library"></a>Grafikbibliothek  
 C++ AMP enthält eine Grafikbibliothek, die für die Programmierung beschleunigter Grafikfunktionen entwickelt wurde. Diese Bibliothek wird nur auf Geräten verwendet, die systemeigene Grafikfunktionen unterstützen. Die Methoden sind der [Concurrency:: Graphics-Namespace](../../parallel/amp/reference/concurrency-graphics-namespace.md) und sind in der Headerdatei \< amp_graphics.h > enthalten. Die Grafikbibliothek enthält die folgenden Hauptkomponenten:  
  
- [Texture-Klasse](../../parallel/amp/reference/texture-class.md): können Sie die Textur-Klasse zum Erstellen von Texturen aus dem Speicher oder aus einer Datei. Texturen ähneln Arrays, da sie Daten enthalten, und sie ähneln Containern in der Standardvorlagenbibliothek (STL) hinsichtlich Zuweisungs- und Kopienkonstruktion. Weitere Informationen finden Sie unter [STL-Containern](../../standard-library/stl-containers.md). Die Vorlagenparameter für die `texture`-Klasse sind der Elementtyp und der Rang. Der Rang kann 1, 2 oder 3 lauten. Der Elementtyp kann einer der Typen kurzer Vektoren sein, die später in diesem Artikel beschrieben werden.  
  
- [Writeonly_texture_view-Klasse](../../parallel/amp/reference/writeonly-texture-view-class.md): bietet lesegeschützten Zugriff auf jede Textur.  
  
- [Kurze Vektor Bibliothek](assetId:///4c4f5bed-c396-493b-a238-c347563f645f): definiert einen Satz von Typen kurzer Vektoren der Länge 2, 3 und 4 auf der Grundlage von `int`, `uint`, `float`, `double`, [Norm](../../parallel/amp/reference/norm-class.md), oder [Unorm](../../parallel/amp/reference/unorm-class.md).  
  
## <a name="includewin8appnamelongtokenwin8appnamelongmdmd-apps"></a>[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps  
 Sie können C++ AMP wie andere C++-Bibliotheken in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps verwenden. In diesen Artikeln wird beschrieben, wie C++ AMP-Code in Apps verwendet wird, die mit C++, C#, Visual Basic oder JavaScript erstellt werden:  
  
- [Verwenden von C++ AMP in Windows Store-Apps](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)  
  
- [Exemplarische Vorgehensweise: Erstellen einer grundlegenden Komponente für Windows-Runtime in C++ und Aufrufen von JavaScript](http://go.microsoft.com/fwlink/p/LinkId=249077)  
  
- [Bing Maps-Reise-Optimierer, eine Windows Store-app in JavaScript und C++](http://go.microsoft.com/fwlink/p/LinkId=249078)  
  
- [Gewusst wie: Verwenden von C++ AMP from c# mithilfe von Windows-Runtime](http://go.microsoft.com/fwlink/p/LinkId=249080)  
  
- [Gewusst wie: Verwenden von C++ AMP from c#](http://go.microsoft.com/fwlink/p/LinkId=249081)  
  
- [Aufrufen systemeigener Funktionen aus verwaltetem Code](../../dotnet/calling-native-functions-from-managed-code.md)  
  
## <a name="c-amp-and-concurrency-visualizer"></a>C++ AMP und Parallelitätsschnellansicht  
 Die Nebenläufigkeitsschnellansicht unterstützt u. a. das Analysieren der Leistung des C++ AMP-Codes. Diese Artikel beschreiben diese Funktionen:  
  
- [GPU-Aktivitätsdiagramm](../Topic/GPU%20Activity%20Graph.md)  
  
- [GPU-Aktivität (Paging)](../Topic/GPU%20Activity%20\(Paging\).md)  
  
- [GPU-Aktivität (dieser Prozess)](../Topic/GPU%20Activity%20\(This%20Process\).md)  
  
- [GPU-Aktivität (andere Prozesse)](../Topic/GPU%20Activity%20\(Other%20Processes\).md)  
  
- [Kanäle (Threadansicht)](../Topic/Channels%20\(Threads%20View\).md)  
  
- [Analysieren von C++ AMP-Code mit der Parallelitätsschnellansicht](http://go.microsoft.com/fwlink/LinkID=253987&clcid=0x409)  
  
## <a name="performance-recommendations"></a>Empfehlungen zur Leistung  
 Modulo und Division ganzer Zahlen ohne Vorzeichen weisen eine erheblich bessere Leistung als Modulo und Division ganzer Zahlen mit Vorzeichen auf. Es wird empfohlen, ganze Zahlen ohne Vorzeichen zu verwenden, sofern möglich.  
  
## <a name="see-also"></a>Siehe auch  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Lambda-Ausdruckssyntax](../../cpp/lambda-expression-syntax.md)   
 [(Referenz (c++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)   
 [Parallele Programmierung in systemeigenem Code](http://go.microsoft.com/fwlink/p/LinkId=238472)

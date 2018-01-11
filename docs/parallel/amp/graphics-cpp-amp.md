---
title: (Grafiken (c++ AMP) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 190a98a4-5f7d-442e-866b-b374ca74c16f
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c9e1b8c6205560e7ea07b529acff3ccfe9db4ea6
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="graphics-c-amp"></a>Grafiken (C++ AMP)
C++ AMP enthält einige APIs in der [Concurrency:: Graphics](../../parallel/amp/reference/concurrency-graphics-namespace.md) Namespace, die Sie verwenden können, auf die texturunterstützung auf GPUs zugreifen. Es folgen einige gängige Szenarien:  
  
-   Können Sie die [Textur](../../parallel/amp/reference/texture-class.md) Klasse als Datencontainer für die Berechnung und die Ausnutzung der *räumliche Positionierung* des Cache und der Layouts von Texturen von GPU-Hardware. Räumliche Stelle ist die Eigenschaft von Datenelementen, die sich physisch sehr ähneln.  
  
-   Die Runtime bietet effiziente Interoperabilität mit Shadern, die keine Compute-Shader sind. Pixel-, Eckpunkt-, Mosaik- und Hüllen-Shader verarbeiten oder produzieren häufig Texturen, die Sie in den C++ AMP-Berechnungen verwenden können.  
  
-   Die Grafik-APIs in C++ AMP stellen alternative Methoden für den Zugriff auf Puffer bereit, die mit Teilworten gepackt sind. Texturen dieser Formate, die darstellen, *Texel* (texturelemente), bestehen aus 8-Bit- oder 16-Bit-skalaren aufgebaut ermöglichen den Zugriff auf solche Speicher gepackten Daten zugegriffen werden.  
  
## <a name="the-norm-and-unorm-types"></a>Die Typen "norm" und "unorm"  
 Die `norm` und `unorm` Typen sind skalare Typen, die den Bereich der beschränken `float` Werte; Dies bezeichnet man *clamping*. Diese Typen können explizit aus anderen skalaren Typen erstellt werden. Bei der Umwandlung wird der Wert ist zunächst umgewandelt `float` und gebunden ist, klicken Sie dann in der entsprechenden Region, die von der Norm [-1.0, 1.0] oder "unorm" [0,0; 1,0] zugelassen wird. Das Umwandeln von +/- Unendlich gibt +/-1 zurück. Das Umwandeln von NaN ist nicht definiert. Ein "norm"-Wert kann ohne Datenverlust implizit aus einem unorm-Wert erstellt werden. Der implizite Konvertierungsoperator zu "float" ist für diese Typen definiert. Binäre Operatoren werden zwischen diesen Typen und anderen integrierten Skalartypen definiert, wie z. B. `float` und `int`: +, -, *, /, ==,! =, >, \<, > =, < =. Die zusammengesetzten Zuweisungsoperatoren werden ebenfalls unterstützt: +=, -=, \*=, / =. Der unäre Negationsoperator (-) wird für norm-Typen definiert.  
  
## <a name="short-vector-library"></a>Kurzvektorbibliothek  
 Die Kurzvektorbibliothek bietet einige Funktionen von der [Vektortyp](http://go.microsoft.com/fwlink/p/?linkid=248500) , die in "HLSL" definiert ist, und dient normalerweise zum Texel zu definieren. Ein Kurzvektor ist eine Datenstruktur, die ein bis vier Werte desselben Typs enthält. Die unterstützten Typen sind `double`, `float`, `int`, `norm`, `uint` und `unorm`. In der folgenden Tabelle werden Typnamen aufgeführt. Für jeden Typ gibt es auch eine entsprechende `typedef`, die keinen Unterstrich im Namen enthält. Die Typen, die Unterstriche sind der [Concurrency:: Graphics-Namespace](../../parallel/amp/reference/concurrency-graphics-namespace.md). Die Typen, die die Unterstriche haben befinden sich in der [Concurrency::graphics::direct3d Namespace](../../parallel/amp/reference/concurrency-graphics-direct3d-namespace.md) , damit sie deutlich von den ähnlich benannten grundlegenden Typen wie z. B. getrennt sind `__int8` und `__int16`.  
  
||Length 2|Die Länge 3|Länge 4|  
|-|--------------|--------------|--------------|  
|double|double_2<br /><br /> double2|double_3<br /><br /> double3|double_4<br /><br /> double4|  
|float|float_2<br /><br /> float2|float_3<br /><br /> float3|float_4<br /><br /> float4|  
|int|int_2<br /><br /> int2|int_3<br /><br /> int3|int_4<br /><br /> int4|  
|norm|norm_2<br /><br /> norm2|norm_3<br /><br /> norm3|norm_4<br /><br /> norm4|  
|uint|uint_2<br /><br /> uint2|uint_3<br /><br /> uint3|uint_4<br /><br /> uint4|  
|unorm|unorm_2<br /><br /> unorm2|unorm_3<br /><br /> unorm3|unorm_4<br /><br /> unorm4|  
  
### <a name="operators"></a>Operatoren  
 Wenn ein Operator zwischen zwei Kurzvektoren definiert wird, wird er auch zwischen einem Kurzvektor und einem Skalar definiert. Außerdem muss eine dieser Bedingungen erfüllt sein:  
  
-   Der Typ des Skalars muss mit dem Elementtyp des Kurzvektors identisch sein.  
  
-   Der Typ des Skalars kann implizit in den Elementtyp des Kurzvektors mit nur einer einzelnen benutzerdefinierten Konvertierung konvertiert werden.  
  
 Der Vorgang wird für jede Komponente einzeln zwischen der jeweiligen Komponente des Kurzvektors und dem Skalar durchgeführt. Folgende Operatoren sind gültig:  
  
|Operatortyp|Gültige Typen|  
|-------------------|-----------------|  
|Binäre Operatoren|Gültig für alle Typen: +, -, *,/,<br /><br /> Gültig für ganzzahlige Typen: %, ^, &#124; &, <\<, >><br /><br /> Die beiden Vektoren müssen dieselbe Größe haben, und das Ergebnis ist ein Vektor derselben Größe.|  
|Relationale Operatoren|Gültig für alle Typen: == und !=|  
|Zusammengesetzte Zuweisungsoperatoren|Gültig für alle Typen: +=, -=, * =, /=<br /><br /> Gültig für ganzzahlige Typen: % =, ^ =, &#124; =, & =, <\<= >> =|  
|Inkrementoperator und Dekrementoperator|Gültig für alle Typen: ++, --<br /><br /> Sowohl Präfixe als auch Suffixe sind gültig.|  
|Bitweiser NOT-Operator (~)|Gültig für ganzzahlige Typen.|  
|Unär-Operator|Gültig für alle Typen außer `unorm` und `uint`.|  
  
### <a name="swizzling-expressions"></a>Swizzeln von Ausdrücken  
 Die Kurzvektorbibliothek unterstützt das Accessorkonstrukt `vector_type.identifier`, um auf die Komponenten eines Kurzvektors zuzugreifen. Die `identifier`, dies wird auch bezeichnet als eine *swizzelnder Ausdruck*, gibt die Komponenten des Vektors. Der Ausdruck kann ein l-Wert oder ein r-Wert sein. Im Bezeichner für einzelne Zeichen möglicherweise: X, y, Z und w; oder "R", "g", "b", und ein. "X" und "R" 0-ten-Komponente, "y" und "g" Mittelwert der ersten Komponente usw. bedeuten. (Beachten Sie, dass "x" und "r" nicht im gleichen Bezeichner verwendet werden dürfen.) Daher geben "rgba" und "xyzw" dasselbe Ergebnis zurück. Zugriffsmethoden mit einzelnen Komponenten wie „x“ und „y“ sind Skalarwerttypen. Accessoren mit mehreren Komponenten sind Kurzvektortypen. Wenn Sie z. B. einen Vektor `int_4` mit dem Namen `fourInts` und den Werten 2, 4, 6 und 8 erstellen, dann gibt `fourInts.y` die ganze Zahl 4 wieder, und `fourInts.rg` gibt ein `int_2`-Objekt zurück, das die Werte 2 und 4 hat.  
  
## <a name="texture-classes"></a>Texturklassen  
 Viele GPUs haben Hardware und Caches, die für den Abruf von Pixeln und Texeln und zum Rendern von Images und Texturen optimiert sind. Die [Textur\<T, N >](../../parallel/amp/reference/texture-class.md) Klasse, die eine Containerklasse für texelobjekte ist, die Textur-Funktionen texturfunktionalität dieses GPUs verfügbar macht. Ein Texel kann Folgendes sein:  
  
-   Ein `int`-, `uint`-, `float`-, `double`-, `norm`- oder `unorm`-Skalar.  
  
-   Ein Kurzvektor, der zwei oder vier Komponenten enthält. Die einzige Ausnahme ist `double_4`, die unzulässig ist.  
  
 Das `texture`-Objekt kann über einen Rang von 1, 2 oder 3 verfügen. Das `texture`-Objekt kann nur als Verweis im Lambda eines Aufrufs auf `parallel_for_each` erfasst werden. Die Textur wird auf dem GPU-Computer als Direct3D-Texturobjekte gespeichert. Weitere Informationen zu Texturen und Texel in Direct3D, finden Sie unter [Einführung in die Texturen in Direct3D 11](http://go.microsoft.com/fwlink/p/?linkid=248502).  
  
 Der verwendete Texeltyp kann eines der vielen Texturformate haben, die in der Grafikprogrammierung verwendet werden. Beispielsweise kann ein RGBA-Format 32 Bit mit jeweils 8 Bit für das R-, G-, B- und A-Skalarelement verwenden. Die Texturhardware einer Grafikkarte kann auf der Grundlage des Formats auf die einzelnen Elemente zugreifen. Wenn Sie das RGBA-Format verwenden, kann die Texturhardware z. B. jedes 8-Bit-Element in ein 32-Bit-Formular extrahieren. In C++ AMP können Sie die Bits pro skalarem Element des Texels festlegen, damit Sie auf die einzelnen Skalarelemente im automatisch Code zugreifen können, ohne Bit-Verschiebung zu verwenden.  
  
### <a name="instantiating-texture-objects"></a>Instanziieren von Texturobjekten  
 Sie können ein Texturobjekt ohne Initialisierung deklarieren. Im folgenden Codebeispiel werden mehrere Texturobjekte deklariert.  
  
```cpp  
#include <amp.h>  
#include <amp_graphics.h>  
using namespace concurrency;  
using namespace concurrency::graphics;  
  
void declareTextures() {  
  
    // Create a 16-texel texture of int.   
    texture<int, 1> intTexture1(16);    
    texture<int, 1> intTexture2(extent<1>(16));   
  
    // Create a 16 x 32 texture of float_2.    
    texture<float_2, 2> floatTexture1(16, 32);    
    texture<float_2, 2> floatTexture2(extent<2>(16, 32));     
  
    // Create a 2 x 4 x 8 texture of uint_4.   
    texture<uint_4, 3> uintTexture1(2, 4, 8);    
    texture<uint_4, 3> uintTexture2(extent<3>(2, 4, 8));  
}  
  
```  
  
 Sie können auch einen Konstruktor auch verwenden, um ein `texture`-Objekt zu deklarieren und zu initialisieren. Im folgenden Codebeispiel wird ein `texture`-Objekt aus einem Vektor aus `float_4`-Objekten instanziiert. Der Wert für die Bits pro skalarem Element wird auf den Standardwert festgelegt. Sie können diesen Konstruktor nicht mit `norm`, `unorm` oder den Kurzvektoren von `norm` und `unorm` verwenden, da sie keinen Standardwert für Bits pro skalarem Element haben.  
  
```cpp  
#include <amp.h>  
#include <amp_graphics.h>  
#include <vector>  
using namespace concurrency;  
using namespace concurrency::graphics;  
  
void initializeTexture() {  
  
    std::vector<int_4> texels;  
    for (int i = 0; i < 768 * 1024; i++) {  
        int_4 i4(i, i, i, i);  
        texels.push_back(i4);  
    }  
  
texture<int_4, 2> aTexture(768, 1024, texels.begin(), texels.end());  
}  
```  
  
 Sie können ein `texture`-Objekt auch deklarieren und initialisieren, indem Sie eine Konstruktorüberladung verwenden, die einen Zeiger auf die Quelldaten, die Größe von Quelldaten in Bytes und die Bits pro skalarem Element verwendet.  
  
```cpp  
void createTextureWithBPC() { *// Create the source data.  
    float source[1024* 2];   
    for (int i = 0; i <1024* 2; i++) {  
    source[i] = (float)i;  
 }  
 *// Initialize the texture by using the size of source in bytes *// and bits per scalar element.  
    texture<float_2, 1> floatTexture(1024, source, (unsigned int)sizeof(source), 32U);

}  
```  
  
 Die Texturen in diesen Beispielen werden in der Standardansicht des Standardbeschleunigers erstellt. Sie können auch andere Überladungen des Konstruktors verwenden, wenn Sie ein `accelerator_view`-Objekt angeben möchten. Sie können kein Texturobjekt für einen CPU-Beschleuniger erstellen.  
  
 Es gibt Einschränkungen zur Größe der einzelnen Dimension des `texture`-Objekts, die in der folgenden Tabelle dargestellt sind. Wenn Sie die Grenzwerte überschreiten, wird ein Laufzeitfehler generiert.  
  
|Struktur|Größeneinschränkung|  
|-------------|---------------------|  
|Textur\<T, 1 >|16384|  
|Textur\<T, 2 >|16384|  
|Textur\<T, 2 >|2048|  
  
### <a name="reading-from-texture-objects"></a>Lesen in Texturobjekten  
 Erfahren Sie aus einer `texture` -Objekt unter Verwendung der [Texture::\[\]](reference/texture-class.md#operator_at), [Texture::Operator()-Operator](reference/texture-class.md#operator_call), oder [Texture:: Get-Methode](reference/texture-class.md#get). Die zwei Operatoren zurückgibt Wert, keinen Verweis. Daher können Sie nicht mit `texture` in ein `texture::operator\[\]`-Objekt schreiben.  
  
```cpp  
void readTexture() {  
    std::vector<int_2> src;      
    for (int i = 0; i <16 *32; i++) {  
    int_2 i2(i, i);

    src.push_back(i2);

 }  
 
    std::vector<int_2> dst(16* 32);

    array_view<int_2, 2> arr(16, 32, dst);

    arr.discard_data();

 
    const texture<int_2, 2> tex9(16, 32, src.begin(), src.end());

    parallel_for_each(tex9.extent, [=, &tex9] (index<2> idx) restrict(amp) { *// Use the subscript operator.        
    arr[idx].x += tex9[idx].x; *// Use the function () operator.        
    arr[idx].x += tex9(idx).x; *// Use the get method.  
    arr[idx].y += tex9.get(idx).y; *// Use the function () operator.    
    arr[idx].y += tex9(idx[0], idx[1]).y;   
 });

 
    arr.synchronize();

} 
 
```  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Texturchannel in einem Kurzvektor gespeichert werden und wie anschließend auf die einzelnen Skalarelemente als Eigenschaften des Kurzvektors zugegriffen wird.  
  
```cpp  
void UseBitsPerScalarElement() { *// Create the image data. *// Each unsigned int (32-bit) represents four 8-bit scalar elements(r,g,b,a values).  
    const int image_height = 16;  
    const int image_width = 16;  
    std::vector<unsigned int> image(image_height* image_width);

 
    extent<2> image_extent(image_height, image_width);

 *// By using uint_4 and 8 bits per channel, each 8-bit channel in the data source is *// stored in one 32-bit component of a uint_4.  
    texture<uint_4, 2> image_texture(image_extent, image.data(), image_extent.size()* 4U,  8U);

 *// Use can access the RGBA values of the source data by using swizzling expressions of the uint_4.  
    parallel_for_each(image_extent, 
 [&image_texture](index<2> idx) restrict(amp)   
 { *// 4 bytes are automatically extracted when reading.  
    uint_4 color = image_texture[idx];   
    unsigned int r = color.r;   
    unsigned int g = color.g;   
    unsigned int b = color.b;   
    unsigned int a = color.a;   
 });

}  
 
```  
  
 In der folgenden Tabelle werden die gültigen Bits pro Kanal für jeden Vektortyp aufgeführt.  
  
|Texturdatentyp|Gültige Bits pro skalarem Element|  
|-----------------------|-----------------------------------|  
|int, int_2, int_4<br /><br /> uint, uint_2, uint_4|8, 16, 32|  
|int_3, uint_3|32|  
|float, float_2, float_4|16, 32|  
|float_3|32|  
|double, double_2|64|  
|norm, norm_2, norm_4<br /><br /> unorm, unorm_2, unorm, 4|8, 16|  
  
### <a name="writing-to-texture-objects"></a>Schreiben in Texturobjekte  
 Verwenden der [Texture:: Set](reference/texture-class.md#set) Methode zum Schreiben in `texture` Objekte. Ein Texturobjekt kann schreibgeschützt sein oder Lese-/Schreibzugriff aufweisen. Damit ein Texturobjekt lesbar und beschreibbar ist, müssen die folgenden Bedingungen erfüllt sein:  

  
-   T ist nur eine skalare Komponente. (Kurzvektoren sind nicht zulässig.)  
  
-   T ist nicht `double`, `norm` oder `unorm`.  
  
-   Die `texture::bits_per_scalar_element`-Eigenschaft lautet 32.  
  
 Wenn alle drei Bedingungen nicht zutreffen, ist das `texture`-Objekt schreibgeschützt. Die ersten beiden Bedingungen werden während der Kompilierung überprüft. Ein Fehler wird generiert, wenn Sie über Code verfügen, der versucht, in ein `readonly`-Texturobjekt zu schreiben. Die Bedingung für `texture::bits_per_scalar_element` wird zur Laufzeit erkannt und die Laufzeit generiert die [Unsupported_feature](../../parallel/amp/reference/unsupported-feature-class.md) -Ausnahme aus, wenn Sie versuchen, das Schreiben in einen schreibgeschützten `texture` Objekt.  
  
 Im folgenden Codebeispiel werden Werte in ein Texturobjekt geschrieben.  
  
```cpp  
void writeTexture() {  
    texture<int, 1> tex1(16);

    parallel_for_each(tex1.extent, [&tex1] (index<1> idx) restrict(amp) {      
    tex1.set(idx, 0);

 });

 
}  
 
```  
  
### <a name="copying-texture-objects"></a>Kopieren von Texturobjekten  
 Sie können zwischen texturobjekten mithilfe von Kopieren der [Kopie](reference/concurrency-namespace-functions-amp.md#copy) Funktion oder die [Copy_async](reference/concurrency-namespace-functions-amp.md#copy_async) Funktion, wie im folgenden Codebeispiel wird dargestellt.  
  
```cpp  
void copyHostArrayToTexture() { *// Copy from source array to texture object by using the copy function.  
    float floatSource[1024* 2];   
    for (int i = 0; i <1024* 2; i++) {  
    floatSource[i] = (float)i;  
}  
    texture<float_2, 1> floatTexture(1024);

    copy(floatSource, (unsigned int)sizeof(floatSource), floatTexture);

 *// Copy from source array to texture object by using the copy function.  
    char charSource[16* 16];   
    for (int i = 0; i <16* 16; i++) {  
    charSource[i] = (char)i;  
 }  
    texture<int, 2> charTexture(16, 16, 8U);

    copy(charSource, (unsigned int)sizeof(charSource), charTexture);
*// Copy from texture object to source array by using the copy function.  
    copy(charTexture, charSource, (unsigned int)sizeof(charSource));

}  
 
```  
  
 Sie können auch kopieren aus einer Struktur in eine andere mithilfe der [Texture:: copy_to](reference/texture-class.md#copy_to) Methode. Die beiden Texturen können sich auf unterschiedlichen accelerator_views befinden. Wenn Sie in ein `writeonly_texture_view`-Objekt kopieren, werden die Daten in das zugrunde liegende `texture`-Objekt kopiert. Folgender Wert für Bits pro skalarem Element und Wertebereich müssen auf den Quell- und Ziel-`texture`-Objekten identisch sein. Wenn diese Anforderungen nicht erfüllt werden, löst die Laufzeit eine Ausnahme aus.  

  
## <a name="texture-view-classes"></a>Texturansichtsklassen  
 C++ AMP führt die [Texture_view-Klasse](../../parallel/amp/reference/texture-view-class.md) in [!INCLUDE[vs_dev12](../../atl-mfc-shared/includes/vs_dev12_md.md)]. Texturansichten unterstützen die gleichen Texel Typen und die Ränge als die [texture-Klasse](../../parallel/amp/reference/texture-class.md), aber im Gegensatz zu Texturen, bieten sie Zugriff auf zusätzliche Hardwarefunktionen wie textursampling und Mipmaps. Texturansichten unterstützen schreibgeschützten, lesegeschützten und Lese-Schreibzugriff auf die zugrunde liegenden Texturdaten.  
  
-   Schreibgeschützter Zugriff wird durch die `texture_view<const T, N>`-Vorlagenspezialisierung geboten, die Elemente mit 1, 2 oder 4 Komponenten, Textursampling und dynamischem Zugriff auf einen Bereich von Mipmapebenen unterstützt, die bei der Instanziierung der Ansicht bestimmt werden.  
  
-   Lesegeschützter Zugriff wird von der unspezialisierten Vorlagenklasse `texture_view<T, N>` ermöglicht, die Elemente unterstützt, die entweder 2 oder 4 Komponenten haben und auf eine einzelne Mipmapebene zugreifen können, die bei der Instanziierung der Ansicht bestimmt wird. Sampling wird nicht unterstützt.  
  
-   Lese-/Schreibzugriff wird von der unspezialisierten Vorlagenklasse `texture_view<T, N>`, wie z. B. Texturen, ermöglicht, die Elemente unterstützt, die nur eine Komponente haben. Die Ansicht kann auf eine einzelne Mipmapebene zugreifen, die bei der Instanziierung bestimmt wird. Sampling wird nicht unterstützt.  
  
 Texturansichten sind analog zu den Array-Sichten, verfügen jedoch nicht der automatische Verwaltung und Verschieben von Funktionalität, die die [Array_view-Klasse](../../parallel/amp/reference/array-view-class.md) bietet gegenüber der [array-Klasse](../../parallel/amp/reference/array-class.md). Auf `texture_view` kann nur in der Beschleunigeransicht zugegriffen werden, in der sich die zugrunde liegenden Texturdaten befinden.  
  
### <a name="writeonlytextureview-deprecated"></a>writeonly_texture_view veraltet  
 Für [!INCLUDE[vs_dev12](../../atl-mfc-shared/includes/vs_dev12_md.md)], C++ AMP bietet eine bessere Unterstützung für hardwaretexturfunktionen z. B. Sampling und Mipmaps, das vom konnte nicht unterstützt werden die [Writeonly_texture_view-Klasse](../../parallel/amp/reference/writeonly-texture-view-class.md). Die neu eingeführte `texture_view`-Klasse unterstützt eine Obermenge der Funktionen in `writeonly_texture_view`; daher ist `writeonly_texture_view` veraltet.  
  
 Es empfiehlt sich, dass Sie – zumindest für einen Code – `texture_view` für den Zugriff auf Funktionen zu verwenden, die zuvor von `writeonly_texture_view` bereitgestellt wurde. Vergleichen Sie die folgenden beiden Codebeispiele, in denen ein Texturobjekt geschrieben wird, das über zwei Komponenten (int_2) verfügt. Beachten Sie in beiden Fällen, dass die Ansicht, `wo_tv4`, durch den Wert im Lambda-Ausdruck erfasst werden muss. Es folgt ein Beispiel, in dem die neue Klasse `texture_view` verwendet wird:  
  
```cpp  
void write2ComponentTexture() {  
    texture<int_2, 1> tex4(16);

    texture_view<int_2, 1> wo_tv4(tex4);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {  
    wo_tv4.set(idx, int_2(1, 1));

 });

}  
```  
  
 Und hier sehen Sie ein Beispiel für die veraltete `writeonly_texture_view`-Klasse:  
  
```  
void write2ComponentTexture() {  
    texture<int_2, 1> tex4(16);

    writeonly_texture_view<int_2, 1> wo_tv4(tex4);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {     
    wo_tv4.set(idx, int_2(1, 1));

 });

}  
```  
  
 Wie Sie sehen können, sind die beiden Codebeispiele fast identisch, wenn Sie nur in die primäre Mipmapebene schreiben. Wenn Sie im vorhandenen Code `writeonly_texture_view` verwendet haben und diesen Code nicht verbessern möchten, müssen Sie ihn nicht ändern. Wenn Sie den Code jedoch weiterentwickeln möchten, empfiehlt es sich, ihn umzuschreiben und `texture_view` zu verwenden, da die hier enthaltenen Erweiterungen neue Hardwaretexturfunktionen unterstützen. Es folgen weitere Informationen zu diesen neuen Funktionen.  
  
 Weitere Informationen zum Veralten von `writeonly_texture_view`, finden Sie unter [Überblick über den Entwurf der Textur-Ansicht in C++ AMP](http://blogs.msdn.com/b/nativeconcurrency/archive/2013/07/25/overview-of-the-texture-view-design-in-c-amp.aspx) für die parallele Programmierung in systemeigenem Code.  
  
### <a name="instantiating-texture-view-objects"></a>Instanziieren von Texturansichtsobjekten  
 Die Deklaration einer `texture_view` ähnelt der Deklaration einer `array_view`, die einem `array` zugeordnet ist. Im folgenden Codebeispiel werden mehrere `texture`-Objekte und `texture_view`-Objekte deklariert, die ihnen zugeordnet werden.  
  
```  
#include <amp.h>  
#include <amp_graphics.h>  
using namespace concurrency;  
using namespace concurrency::graphics;  
  
void declareTextureViews()  
{  
    // Create a 16-texel texture of int, with associated texture_views.  
    texture<int, 1> intTexture(16);  
    texture_view<const int, 1> intTextureViewRO(intTexture);  // read-only  
    texture_view<int, 1> intTextureViewRW(intTexture);        // read-write  
  
    // Create a 16 x 32 texture of float_2, with associated texture_views.  
    texture<float_2, 2> floatTexture(16, 32);  
    texture_view<const float_2, 2> floatTextureViewRO(floatTexture);  // read-only  
    texture_view<float_2, 2> floatTextureViewRO(floatTexture);        // write-only  
  
    // Create a 2 x 4 x 8 texture of uint_4, with associated texture_views.  
    texture<uint_4, 3> uintTexture(2, 4, 8);  
    texture_view<const uint_4, 3> uintTextureViewRO(uintTexture);  // read-only  
    texture_view<uint_4, 3> uintTextureViewWO(uintTexture);        // write-only  
}  
```  
  
 Beachten Sie, wie eine Texturansicht mit nicht konstantem Elementtyp und einer Komponente Lese-/Schreibzugriff hat. Dagegen ist eine Texturansicht mit nicht konstantem Elementtyp und mehr als einer Komponente lesegeschützt. Texturansichten mit konstanten Elementtypen sind stets schreibgeschützt. Ist der Elementtyp jedoch nicht konstant, bestimmt die Anzahl von Komponenten im Element, ob die Ansicht Lese-/Schreibzugriff (1 Komponente) hat oder lesegeschützt (mehrere Komponenten) ist.  
  
 Der Elementtyp `texture_view` (seine Konstanz sowie die Anzahl der Komponenten) spielt ebenfalls eine Rolle bei der Frage, ob die Ansicht Textursampling unterstützt und wie auf Mipmapebenen zugegriffen werden kann:  
  
|Typ|Komponenten|Lesen|Write|Sampling|Mipmapzugriff|  
|----------|----------------|----------|-----------|--------------|-------------------|  
|Texture_view\<const T, N >|1, 2, 4|Ja|Nein (1)|Ja|Ja, kann indexiert werden. Bereich wird bei der Instanziierung bestimmt.|  
|Texture_view\<T, N >|1<br /><br /> 2, 4|Ja<br /><br /> Nein (2)|Ja<br /><br /> Ja|Nein (1)<br /><br /> Nein (1)|Ja, eine Ebene. Ebene wird bei der Instanziierung bestimmt.<br /><br /> Ja, eine Ebene. Ebene wird bei der Instanziierung bestimmt.|  
  
 In dieser Tabelle sehen Sie, dass schreibgeschützte Texturansichten die neuen Funktionen vollständig unterstützen, aber nicht in die Ansicht schreiben können. Beschreibbare Texturansichten sind insofern beschränkt, als dass sie auf eine Mipmapebene nur zugreifen können. Texturansichten mit Lese-/Schreibzugriff sind sogar spezialisierter als die beschreibbaren Ansichten, da für sie zusätzlich die Anforderung gilt, dass der Elementtyp der Texturansicht nur über eine Komponente verfügt. Beachten Sie, dass das Sampling nicht in beschreibbaren Texturansichten unterstützt wird, da es sich um einen auf das Lesen ausgerichteten Vorgang handelt.  
  
### <a name="reading-from-texture-view-objects"></a>Lesen in Texturansichtsobjekten  
 Wenn über eine Texturansicht in Texturdaten ohne Sampling gelesen wird, ähnelt dies dem Lesen in der Textur selbst mit der Ausnahme, dass Texturen durch eine Referenz erfasst werden, während Texturansichten durch einen Wert erfasst werden. Die folgenden beiden Codebeispiele veranschaulichen dies zunächst nur mit der `texture`:  
  
```  
void write2ComponentTexture() {  
    texture<int_2, 1> text_data(16);

    parallel_for_each(extent<1>(16), [&] (index<1> idx) restrict(amp) {  
    tex_data.set(idx, int_2(1, 1));

 });

}  
```  
  
 Es folgt das gleiche Beispiel, nun jedoch mit der `texture_view`-Klasse:  
  
```  
void write2ComponentTexture() {  
    texture<int_2, 1> tex_data(16);

    texture_view<int_2, 1> tex_view(tex_data);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {  
    tex_view.set(idx, int_2(1, 1));

 });

}  
```  
 Texturansichten, deren Elemente auf Gleitkommatypen basieren, z. B.float, float_2 oder float_4, sind auch mithilfe von Textursampling lesbar, sodass Hardwareunterstützung für unterschiedliche Filter- und Adressierungsmodi genutzt werden kann. C++ AMP unterstützt die beiden Filtermodi, die in Berechnungsszenarien am häufigsten verwendet werden – Punktfilterung (nächster Nachbar) und lineare Filterung (gewichteter Durchschnitt) – und die vier Adressierungsmodi Wrap, Mirror, Clamp und Border. Weitere Informationen zu adressierungsmodi, finden Sie unter [Address_mode-Enumeration](reference/concurrency-graphics-namespace-enums.md#address_mode).  
  
 Neben den Modi, die C++ AMP direkt unterstützt, können Sie auf andere Filtermodi und Adressierungsmodi der zugrunde liegenden Plattform zugreifen, indem Sie die Interop-APIs verwenden, um einen Textursampler anzunehmen, der unter direkter Verwendung der Plattform-APIs erstellt wurde. Beispielsweise unterstützt Direct3D andere Filtermodi wie z. B. anisotropische Filterung und kann für jede Dimension einer Textur eine andere Adressierung anwenden. Sie können einen Textursampler erstellen, dessen Koordinaten vertikal eingeschlossen, horizontal gespiegelt sind und für den mit anisotroper Filterung Stichproben erstellt wurden, indem Sie die Direct3D-APIs verwenden und dann den Sampler im C++ AMP-Code mit der Interop-API `make_sampler` nutzen. Weitere Informationen finden Sie unter [Textursampling in C++ AMP](http://blogs.msdn.com/b/nativeconcurrency/archive/2013/07/18/texture-sampling-in-c-amp.aspx) für die parallele Programmierung in systemeigenem Code.  
  
 Texturansichten unterstützen auch das Lesen von Mipmaps. Schreibgeschützte Texturansichten (die einen konstanten Elementtyp haben) bieten die höchste Flexibilität, da für eine Reihe von MIP-Ebenen, die bei der Instanziierung bestimmt werden, dynamisch eine Stichprobe erstellt werden kann und Elemente mit 1, 2 oder 4 Komponenten unterstützt werden. Texturansichten mit Lese/Schreibzugriff mit Elementen mit einer einzelnen Komponente unterstützen ebenfalls Mipmaps, jedoch nur auf einer Ebene, die bei der Instanziierung bestimmt wird. Weitere Informationen finden Sie unter [Textur mit Mipmaps](http://blogs.msdn.com/b/nativeconcurrency/archive/2013/08/22/texture-with-mipmaps.aspx) für die parallele Programmierung in systemeigenem Code.  
  
### <a name="writing-to-texture-view-objects"></a>Schreiben in Texturansichtsobjekten  
 Verwenden der [texture_view:: Get-Methode](reference/texture-view-class.md#get) zum Schreiben in die zugrunde liegende `texture` über die `texture_view` Objekt. Eine Texturansicht kann Lese-/Schreibzugriff haben, schreibgeschützt oder lesegeschützt sein. Damit eine Texturansicht beschreibbar ist, muss sie einen nicht konstanten Elementtyp haben. Damit eine Texturansicht lesbar und beschreibbar ist, darf der entsprechende Elementtyp nur eine Komponente haben. Anderenfalls ist die Texturansicht schreibgeschützt. Sie können zu einem bestimmten Zeitpunkt nur auf eine einzelne Mipmapebene einer Textur über eine Texturansicht zugreifen, und die Ebene wird bei der Instanziierung der Ansicht bestimmt.  
  
 Dieses Beispiel zeigt, wie in die zweitausführlichste Mipmapebene einer Textur mit 4 Mipmapebenen geschrieben wird. Die ausführlichste Mipmapebene ist Ebene 0.  
  
```  
// Create a texture that has 4 mipmap levels : 16x16, 8x8, 4x4, 2x2  
texture<int, 2> tex(extent<2>(16, 16), 16U, 4);

 
// Create a writable texture view to the second mipmap level :4x4  
texture_view<int, 2> w_view(tex, 1);

 
parallel_for_each(w_view.extent, [=](index<2> idx) restrict(amp)  
{  
    w_view.set(idx, 123);

});
```  
  
## <a name="interoperability"></a>Interoperabilität  

 Die C++ AMP-Laufzeit unterstützt die Interoperabilität zwischen `texture<T,1>` und die [ID3D11Texture1D Schnittstelle](http://go.microsoft.com/fwlink/p/?linkId=248503), das zwischen `texture<T,2>` und die [ID3D11Texture2D Schnittstelle](http://go.microsoft.com/fwlink/p/?linkId=255317), sowie zwischen `texture<T,3>`und [ID3D11Texture3D Schnittstelle](http://go.microsoft.com/fwlink/p/?linkId=255377). Die [Get_texture](reference/concurrency-graphics-direct3d-namespace-functions.md#get_texture) -Methode übernimmt ein `texture` -Objekt und gibt eine `IUnknown` Schnittstelle. Die [Make_texture](reference/concurrency-graphics-direct3d-namespace-functions.md#make_texture) -Methode übernimmt ein `IUnknown` Schnittstelle und eine `accelerator_view` -Objekt und gibt eine `texture` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [double_2-Klasse](../../parallel/amp/reference/double-2-class.md)   
 [double_3-Klasse](../../parallel/amp/reference/double-3-class.md)   
 [double_4-Klasse](../../parallel/amp/reference/double-4-class.md)   
 [float_2-Klasse](../../parallel/amp/reference/float-2-class.md)   
 [float_3-Klasse](../../parallel/amp/reference/float-3-class.md)   
 [float_4-Klasse](../../parallel/amp/reference/float-4-class.md)   
 [int_2-Klasse](../../parallel/amp/reference/int-2-class.md)   
 [int_3-Klasse](../../parallel/amp/reference/int-3-class.md)   
 [int_4-Klasse](../../parallel/amp/reference/int-4-class.md)   
 [norm_2-Klasse](../../parallel/amp/reference/norm-2-class.md)   
 [norm_3-Klasse](../../parallel/amp/reference/norm-3-class.md)   
 [norm_4-Klasse](../../parallel/amp/reference/norm-4-class.md)   
 [Short_vector-Struktur](../../parallel/amp/reference/short-vector-structure.md)   
 [Short_vector_traits-Struktur](../../parallel/amp/reference/short-vector-traits-structure.md)   
 [uint_2-Klasse](../../parallel/amp/reference/uint-2-class.md)   
 [uint_3-Klasse](../../parallel/amp/reference/uint-3-class.md)   
 [uint_4-Klasse](../../parallel/amp/reference/uint-4-class.md)   
 [unorm_2-Klasse](../../parallel/amp/reference/unorm-2-class.md)   
 [unorm_3-Klasse](../../parallel/amp/reference/unorm-3-class.md)   
 [unorm_4-Klasse](../../parallel/amp/reference/unorm-4-class.md)

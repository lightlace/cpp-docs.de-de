---
title: Auflistungen (C + c++ / CX) | Microsoft Docs
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
caps.latest.revision: "35"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5c97a264488e8b382091b24cdef8faae4c7bbfc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="collections-ccx"></a>Auflistungen (C++/CX)
In C + c++ / CX-Programm möglich der Container der Standardvorlagenbibliothek (STL) oder eines anderen benutzerdefinierten Auflistungstyps frei verwenden. Wenn Sie jedoch übergeben Sammlungen hin-und über die Windows-Runtime-anwendungsbinärdateischnittstelle (ABI) – beispielsweise an ein XAML-Steuerelement oder einen JavaScript-Client – müssen Sie Windows-Runtime-Auflistungstypen verwenden.  
  
 Windows-Runtime definiert die Schnittstellen für Auflistungen und verwandte Typen und C + c++ / CX stellt die konkreten C++-Implementierungen in der Headerdatei "Collection.h" bereit. Diese Abbildung zeigt die Beziehungen zwischen den Auflistungstypen:  
  
 ![C &#43; &#43; &#47; CX-Vererbungsstruktur für Auflistungstypen](../cppcx/media/cppcxcollectionsinheritancetree.png "CPPCXCollectionsInheritanceTree")  
  
-   Die [Platform::Collections::Vector-Klasse](../cppcx/platform-collections-vector-class.md) ähnelt der [std::vector-Klasse](../standard-library/vector-class.md).  
  
-   Die [Platform::Collections::Map-Klasse](../cppcx/platform-collections-map-class.md) ähnelt der [std::map-Klasse](../standard-library/map-class.md).  
  
-   Die[Platform::Collections::VectorView-Klasse](../cppcx/platform-collections-vectorview-class.md) und[Platform::Collections::MapView-Klasse](../cppcx/platform-collections-mapview-class.md) sind schreibgeschützte Versionen von `Vector` und `Map`.  
  
-   Iteratoren werden im [Platform::Collections-Namespace](../cppcx/platform-collections-namespace.md)definiert. Diese Iteratoren erfüllen die Anforderungen für STL-Iteratoren und ermöglichen die Verwendung von [std::find](../standard-library/algorithm-functions.md#find),  [std::count_if](../standard-library/algorithm-functions.md#count_if)und anderen STL-Algorithmen für einen beliebigen [Windows::Foundation::Collections](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.aspx) -Schnittstellentyp oder einen konkreten [Platform::Collections](../cppcx/platform-collections-namespace.md) -Typ. Beispielsweise bedeutet dies, dass Sie eine Auflistung in einer Windows-Runtime-Komponente durchlaufen werden können, die in c# erstellt wird und einen STL-Algorithmus darauf anwenden.  
  
    > [!IMPORTANT]
    >  Die Proxyiteratoren `VectorIterator` und `VectorViewIterator` verwenden die Proxyobjekte `VectoryProxy<T>` und `ArrowProxy<T>` , um eine Verwendung mit STL-Containern zu ermöglichen. Weitere Informationen finden Sie unter "VectorProxy-Elemente" weiter unten in diesem Artikel.  
  
-   Die C + c++ / CX--Auflistungstypen unterstützen, die die gleichen Threadsicherheitsgarantien STL-Containern unterstützen.  
  
-   [Windows::Foundation::Collections::IObservableVector](http://msdn.microsoft.com/library/windows/apps/br226052.aspx) und [Windows::Foundation::Collections::IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) definieren Ereignisse, die ausgelöst werden, wenn sich die Auflistung auf unterschiedliche Weise ändert. Durch Implementierung dieser Schnittstellen unterstützen  [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) und [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) eine Datenbindung mit XAML-Auflistungen. Wenn Sie beispielsweise einen `Vector` mit einer Datenbindung zu einem `Grid`haben und ein Element einer Auflistung hinzufügen, wird die Änderung in die Benutzeroberfläche des Rasters übernommen.  
  
## <a name="vector-usage"></a>Verwendung von Vektoren  
 Wenn Ihre Klasse verfügt über einen sequenzcontainer an eine andere Windows-Runtime-Komponente zu übergeben, verwenden Sie [Collections:: IVector\<T >](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) als Parameter oder Rückgabetyp und [Platform:: Collections::vector\<T >](../cppcx/platform-collections-vector-class.md) als konkrete Implementierung. Wenn Sie versuchen, einen `Vector` -Typ in einem öffentlichen Rückgabewert oder Parameter zu verwenden, wird der Compilerfehler C3986 ausgelöst. Sie können das Problem beheben, indem Sie den `Vector` in einen `IVector`ändern.  
  
> [!IMPORTANT]
>  Wenn Sie eine Sequenz im eigenen Programm übergeben, verwenden Sie entweder `Vector` oder `std::vector` , da sie effizienter als `IVector`sind. Verwenden Sie `IVector` nur, wenn Sie den Container über die ABI übergeben.  
>   
>  Das Windows-Runtime-Typsystem unterstützt nicht das Konzept von verzweigten Arrays und aus diesem Grund können Sie ein IVector übergeben < Platform:: Array\<T >> als Rückgabewert oder Methodenparameter. Um ein verzweigtes Array oder eine Sequenz von Sequenzen an die ABI zu übergeben, verwenden Sie `IVector<IVector<T>^>`.  
  
 `Vector<T>` stellt die Methoden bereit, die zum Hinzufügen, Entfernen und das Zugreifen auf Elemente in der Auflistung erforderlich sind, und kann implizit zu `IVector<T>`konvertiert werden. Sie können STL-Algorithmen auch bei Instanzen von `Vector<T>`verwenden. Das folgende Beispiel veranschaulicht die grundlegende Verwendung. Die [begin function](../cppcx/begin-function.md) und [end function](../cppcx/end-function.md) hier stammen vom Namespace `Platform::Collections` und nicht vom Namespace `std` .  
  
 [!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]  
  
 Wenn Sie vorhandenen Code verfügen, verwendet `std::vector` und möchten, in einer Windows-Runtime-Komponente verwenden, verwenden Sie nur eine der der `Vector` Konstruktoren, die akzeptiert eine `std::vector` oder ein Paar von Iteratoren zur erstellen eine `Vector` an dem Punkt, an dem Sie übergeben, die über die ABI-Auflistung. Im folgenden Beispiel wird gezeigt, wie der `Vector` -Bewegungskonstruktor zur effizienten Initialisierung von `std::vector`verwendet wird. Nach dem Verschiebungsvorgang ist die ursprüngliche `vec` -Variable nicht mehr gültig.  
  
 [!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]  
  
 Wenn Sie einen Vektor von Zeichenfolgen haben, die Sie an einem zukünftigen Punkt über die ABI übergeben müssen, müssen Sie entscheiden, ob die Zeichenfolgen zuerst als `std::wstring` -Typen oder als `Platform::String^` -Typen erstellt werden sollen. Wenn die Zeichenfolgen einen hohen Verarbeitungsaufwand erfordern, verwenden Sie `wstring`. Erstellen Sie andernfalls die Zeichenfolgen als `Platform::String^` -Typen, und vermeiden Sie den Aufwand einer späteren Konvertierung. Außerdem müssen Sie festlegen, ob diese Zeichenfolgen intern in einem `std:vector` oder in einem `Platform::Collections::Vector` abgelegt werden sollen. Im Allgemeinen sollten Sie `std::vector` verwenden und nur dann einen `Platform::Vector` erstellen, wenn Sie den Container über die ABI übergeben.  
  
## <a name="value-types-in-vector"></a>Werttypen im Vektor  
 Jedes in [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) gespeicherte Element muss einen Übereinstimmungsvergleich unterstützen, und zwar entweder implizit oder mithilfe eines benutzerdefinierten [std::equal_to](../standard-library/equal-to-struct.md) -Vergleichsoperators, den Sie bereitstellen. Alle Verweistypen und alle skalaren Typen unterstützen implizit Übereinstimmungsvergleiche. Für nicht skalare Werttypen wie [Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx)oder für benutzerdefinierte Vergleiche – z. B. `objA->UniqueID == objB->UniqueID`– müssen Sie ein benutzerdefiniertes Funktionsobjekt bereitstellen.  
   
  
## <a name="vectorproxy-elements"></a>VectorProxy-Elemente  
 [Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md) und [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) ermöglichen die Verwendung von `range for` -Schleifen und-Algorithmen wie [Std:: Sort](../standard-library/algorithm-functions.md#sort) mit einer [IVector\<T >](http://msdn.microsoft.com/en-us/library/windows/apps/br206631.aspx) Container. `IVector` -Elemente können jedoch nicht über C++-Zeigerdereferenzierungen aufgerufen werden; auf sie kann nur durch die [GetAt](http://msdn.microsoft.com/library/windows/apps/br206634.aspx) - und [SetAt](http://msdn.microsoft.com/library/windows/apps/br206642.aspx) -Methode zugegriffen werden. Daher verwenden diese Iteratoren die Proxyklassen `Platform::Details::VectorProxy<T>` und `Platform::Details::ArrowProxy<T>` , um Zugriff auf die einzelnen Elemente über die Operatoren `*`, `->`und `[]` zu ermöglichen, wie von STL gefordert. Streng genommen ist bei einer `IVector<Person^> vec`der Typ von `*begin(vec)` `VectorProxy<Person^>`. Allerdings ist das Proxyobjekt fast immer für Ihren Code transparent. Diese Proxyobjekte werden nicht dokumentiert, da sie nur für die interne Verwendung durch Iteratoren bestimmt sind. Es ist jedoch hilfreich zu wissen, wie der Mechanismus funktioniert.  
  
 Wenn Sie eine `range for` -Schleife über `IVector` -Container verwenden, verwenden Sie `auto&&` , damit die Iteratorvariable korrekt an die `VectorProxy` -Elemente gebunden werden kann. Wenn Sie `auto` oder `auto&`verwenden, wird die Compilerwarnung C4239 ausgelöst und `VectoryProxy` wird im Text der Warnung erwähnt.  
  
 Die folgende Abbildung zeigt ein Beispiel für eine `range for` -Schleife über eine `IVector<Person^>`. Beachten Sie, dass die Ausführung am Haltepunkt in Zeile 64 beendet wird. Im Fenster **Schnellüberwachung** wird angezeigt, dass die Iteratorvariable `p` tatsächlich eine `VectorProxy<Person^>` ist, die die Membervariablen `m_v` und `m_i` aufweist. Wenn Sie jedoch `GetType` für diese Variable aufrufen, gibt sie den identischen Typ zur Instanz `Person` `p2`zurück. Die Schlussfolgerung daraus: Obwohl möglicherweise `VectorProxy` und `ArrowProxy` in der **Schnellüberwachung**, in bestimmten Compilerfehlern des Debuggers oder an anderen Stellen angezeigt werden, müssen Sie sie in der Regel nicht explizit codieren.  
  
 ![VectorProxy in Bereich &#45; for-Schleife basierend](../cppcx/media/vectorproxy-1.png "VectorProxy_1")  
  
 Ein Szenario, in dem Sie Code um das Proxyobjekt herum schreiben müssen, ist, wenn Sie eine `dynamic_cast` für die Elemente durchführen müssen, zum Beispiel, wenn Sie nach XAML-Objekte eines bestimmten Typs in einer `UIElement` -Elementauflistung suchen. In diesem Fall müssen Sie zuerst das Element in [Platform::Object](../cppcx/platform-object-class.md)^ umwandeln und dann die dynamische Umwandlung ausführen:  
  
```  
  
void FindButton(UIElementCollection^ col)  
{  
    // Use auto&& to avoid warning C4239  
    for (auto&& elem : col)  
    {  
        Button^ temp = dynamic_cast<Button^>(static_cast<Object^>(elem));  
        if (nullptr != temp)  
        {  
            // Use temp...  
        }  
    }  
}  
```  
  
## <a name="map-usage"></a>Verwendung von Zuordnungen  
 Dieses Beispiel zeigt, wie Elemente eingefügt und in einer [Platform::Collections::Map](../cppcx/platform-collections-map-class.md)gesucht werden und wie die `Map` anschließend als schreibgeschützter [Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) -Typ zurückgegeben wird.  
  
 [!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]  
  
 Im Allgemeinen sollten Sie für die interne Zuordnungsfunktionalität aus Leistungsgründen vorzugsweise den Typ `std::map` verwenden. Wenn Sie den Container über die ABI übergeben müssen, erstellen Sie eine [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) von der [std::map](../standard-library/map-class.md) , und geben Sie den `Map` als eine [Windows::Foundation::Collections::IMap](http://msdn.microsoft.com/library/windows/apps/br226042.aspx)zurück. Wenn Sie versuchen, einen `Map` -Typ in einem öffentlichen Rückgabewert oder Parameter zu verwenden, wird der Compilerfehler C3986 ausgelöst. Sie können das Problem beheben, indem Sie den `Map` in einen `IMap`ändern. In einigen Fällen, beispielsweise wenn Sie nur wenige Suchen oder Einfügungen ausführen und die Auflistung häufig über die ABI übergeben, ist es möglicherweise weniger Aufwand, gleich `Platform::Collections::Map` zu verwenden und die Konvertierung von `std::map`zu vermeiden. Vermeiden Sie in jedem Fall Such- und Einfügevorgänge bei einer `IMap` , da diese der am wenigsten leistungsfähige der drei Typen ist. Konvertieren Sie in `IMap` nur dann, wenn Sie den Container über die ABI übergeben.  
  
## <a name="value-types-in-map"></a>Werttypen in der Zuordnung  
 Elemente in [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) werden sortiert. Jedes in `Map` zu speichernde Element muss den Kleiner-als-Vergleich in strenger, schwacher Reihenfolg unterstützen, und zwar entweder implizit oder mithilfe eines benutzerdefinierten [stl::less](../standard-library/less-struct.md) -Vergleichsoperators, den Sie bereitstellen. Skalare Typen unterstützen den Vergleich implizit. Für nicht skalare Werttypen wie `Windows::Foundation::DateTime`oder für benutzerdefinierte Vergleiche – z. B. `objA->UniqueID < objB->UniqueID`– müssen Sie einen benutzerdefinierten Vergleichsoperator bereitstellen.  
  
## <a name="collection-types"></a>Auflistungstypen  
 Auflistungen sind in vier Kategorien unterteilt: änderbare Versionen und schreibgeschützte Versionen von Sequenzauflistungen und assoziativen Auflistungen. Darüber hinaus C + c++ / CX verbessert die Auflistungen durch Bereitstellung von drei iteratorklassen, die den Zugriff auf Auflistungen vereinfachen. 
  
 Elemente einer änderbaren Auflistung können geändert werden, aber Elemente einer schreibgeschützten Auflistung, die als *Ansicht*bekannt ist, können nur gelesen werden. Elemente einer [:: Collections:: vector](../cppcx/platform-collections-vector-class.md) oder[:: Collections:: vectorview](../cppcx/platform-collections-vectorview-class.md) -Auflistung zugegriffen werden kann, mit der ein Iterator oder der Auflistung [Vector:: GetAt](../cppcx/platform-collections-vector-class.md#getat) und ein Index. Elemente einer assoziativen Auflistung kann zugegriffen werden, mithilfe der Auflistung [Map:: Lookup](../cppcx/platform-collections-map-class.md#lookup) und einen Schlüssel.  
  
 [Platform::Collections::Map-Klasse](../cppcx/platform-collections-map-class.md)  
 Eine änderbare, assoziative Auflistung. Zuordnungselemente sind Schlüssel-Wert-Paare. Sowohl das Suchen nach einem Schlüssel, um den zugeordneten Wert abzurufen, als auch das Durchlaufen aller Schlüssel-Wert-Paare werden unterstützt.  
  
 `Map` und `MapView` sind als Vorlagen für `<K, V, C = std::less<K>>`vorhanden. Daher können Sie den Vergleichsoperator anpassen.  Darüber hinaus sind `Vector` und `VectorView` auf `<T, E = std::equal_to<T>>` vorlagenbasiert, damit Sie das Verhalten von `IndexOf()`anpassen können. Dies ist vor allem für `Vector` und `VectorView` von Wertstrukturen wichtig. Um beispielsweise einen Vektor\<Windows::Foundation::DateTime >, müssen Sie einen benutzerdefinierten Vergleichsoperator bereitstellen, da "DateTime" nicht überlädt den Operator ==-Operator.  
  
 [Platform::Collections::MapView-Klasse](../cppcx/platform-collections-mapview-class.md)  
 Eine schreibgeschützte Version von `Map`.  
  
 [Platform::Collections::Vector Class](../cppcx/platform-collections-vector-class.md)  
 Eine änderbare Sequenzauflistung. `Vector<T>` unterstützt stetige und amortisierte stetige [Append](../cppcx/platform-collections-vector-class.md#append) -Direktzugriffsvorgänge.  
  
 [Platform::Collections::VectorView-Klasse](../cppcx/platform-collections-vectorview-class.md)  
 Eine schreibgeschützte Version von `Vector`.  
  
 [Platform::Collections::InputIterator-Klasse](../cppcx/platform-collections-inputiterator-class.md)  
 Ein STL-Iterator, der die Anforderungen eines STL-Eingabeiterators erfüllt.  
  
 [Platform::Collections::VectorIterator-Klasse](../cppcx/platform-collections-vectoriterator-class.md)  
 Ein STL-Iterator, der die Anforderungen eines änderbaren STL-Iterators mit Direktzugriff erfüllt.  
  
 [Platform::Collections::VectorViewIterator-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)  
 Ein STL-Iterator, der die Anforderungen eines STL-  `const` -Iterators mit Direktzugriff erfüllt.  
  
### <a name="begin-and-end-functions"></a>begin() und end() -Funktionen  
 Zur Vereinfachung der Verwendung von STLS zu verarbeiten `Vector`, `VectorView`, `Map`, `MapView`, und beliebige `Windows::Foundation::Collections` Objekte C + c++ / CX unterstützt Überladungen der der [begin-Funktion](../cppcx/begin-function.md) und [Ende Funktion](../cppcx/end-function.md) nicht-Memberfunktionen.  
  
 Die folgende Tabelle zeigt die verfügbaren Iteratoren und Funktionen auf.  
  
|Iterators|Funktionen|  
|---------------|---------------|  
|[Platform::Collections::VectorIterator\<T >](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> (Speichert intern [Collections:: IVector\<T >](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) und int.)|[Begin](../cppcx/begin-function.md)/ [End](../cppcx/end-function.md)([Collections:: IVector\<T >](http://msdn.microsoft.com/library/windows/apps/br206631.aspx))|  
|[Platform::Collections::VectorViewIterator\<T >](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> (Speichert intern [IVectorView\<T >](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^ und int.)|[Begin](../cppcx/begin-function.md)/ [End](../cppcx/end-function.md) ([IVectorView\<T >](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^)|  
|[Platform::Collections::InputIterator\<T >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Speichert intern [IIterator\<T >](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ und T.)|[Begin](../cppcx/begin-function.md)/ [End](../cppcx/end-function.md) ([IIterable\<T >](http://msdn.microsoft.com/library/windows/apps/br226024.aspx))|  
|[Platform::Collections::InputIterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Speichert intern [IIterator\<T >](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ und T.)|[Begin](../cppcx/begin-function.md)/ [End](../cppcx/end-function.md) ([IMap\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226042.aspx).|  
|[Platform::Collections::InputIterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Speichert intern [IIterator\<T >](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ und T.)|[begin](../cppcx/begin-function.md)/ [end](../cppcx/end-function.md) ([Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx))|  
  
### <a name="collection-change-events"></a>Änderungsereignisse bei Auflistungen  
 `Vector` und `Map` unterstützen Datenbindung in XAML-Auflistungen durch Implementieren von Ereignissen, die auftreten, wenn ein Auflistungsobjekt geändert oder zurückgesetzt wird oder wenn ein Element in einer Auflistung eingefügt, aus dieser entfernt oder geändert wird. Sie können zwar eigene Typen schreiben, die Datenbindung unterstützen, können jedoch nicht von `Map` oder von `Vector` erben, da diese Typen versiegelt sind.  
  
 Die Delegaten [Windows::Foundation::Collections::VectorChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206656.aspx) und [Windows::Foundation::Collections::MapChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) geben die Signaturen für Ereignishandler für Auflistungsänderungsereignisse an. Die öffentlichen Enumerationsklasse [Windows::Foundation::Collections::CollectionChange](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx) und die Verweisklassen `Platform::Collection::Details::MapChangedEventArgs` und `Platform::Collections::Details::VectorChangedEventArgs` speichern die Ereignisargumente, um herauszufinden, wodurch das Ereignis ausgelöst wurde. *`EventArgs` -Typen werden im `Details` -Namespace definiert, da Sie sie nicht explizit erstellen oder nutzen müssen, wenn Sie `Map` oder `Vector`verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Integrierte Typen](http://msdn.microsoft.com/en-us/acc196fd-09da-4882-b554-6c94685ec75f)   
 [Visual C++-Sprachreferenz](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)
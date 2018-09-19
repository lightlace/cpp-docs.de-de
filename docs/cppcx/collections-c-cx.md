---
title: Auflistungen (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67e5b086e57c90b9cb11779d8f3af167768a45fe
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103346"
---
# <a name="collections-ccx"></a>Auflistungen (C++/CX)

In einem C++ / CX-Programm verwenden, können Sie der Container der Standardvorlagenbibliothek (STL) oder eines anderen benutzerdefinierten Auflistungstyps frei verwenden vornehmen. Wenn Sie jedoch übergeben Sammlungen hin-und über die Windows-Runtime-anwendungsbinärdateischnittstelle (ABI) – z. B. an ein XAML-Steuerelement oder ein JavaScript-Client – müssen Sie Windows-Runtime-Auflistungstypen verwenden.

Die Windows-Runtime definiert die Schnittstellen für Auflistungen und verwandte Typen und C++ / CX stellt die konkreten C++-Implementierungen in der Headerdatei "Collection.h" bereit. Diese Abbildung zeigt die Beziehungen zwischen den Auflistungstypen:

![C&#43;&#43;&#47;CX-Vererbungsstruktur für Auflistungstypen](../cppcx/media/cppcxcollectionsinheritancetree.png "CPPCXCollectionsInheritanceTree")

- Die [Platform::Collections::Vector-Klasse](../cppcx/platform-collections-vector-class.md) ähnelt der [std::vector-Klasse](../standard-library/vector-class.md).

- Die [Platform::Collections::Map-Klasse](../cppcx/platform-collections-map-class.md) ähnelt der [std::map-Klasse](../standard-library/map-class.md).

- Die[Platform::Collections::VectorView-Klasse](../cppcx/platform-collections-vectorview-class.md) und[Platform::Collections::MapView-Klasse](../cppcx/platform-collections-mapview-class.md) sind schreibgeschützte Versionen von `Vector` und `Map`.

- Iteratoren werden im [Platform::Collections-Namespace](../cppcx/platform-collections-namespace.md)definiert. Diese Iteratoren erfüllen die Anforderungen für STL-Iteratoren und ermöglichen die Verwendung von [Std:: Find](../standard-library/algorithm-functions.md#find), [count_if](../standard-library/algorithm-functions.md#count_if), und anderen STL-Algorithmen für einen beliebigen [Collections](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.aspx) -Schnittstellentyp oder [Platform:: Collections](../cppcx/platform-collections-namespace.md) konkreten Typ. Beispielsweise bedeutet dies, dass Sie eine Sammlung in einer Windows-Runtime-Komponente durchlaufen können, die in c# erstellt wird und einen STL-Algorithmus darauf anwenden.

   > [!IMPORTANT]
   > Die Proxyiteratoren `VectorIterator` und `VectorViewIterator` verwenden die Proxyobjekte `VectoryProxy<T>` und `ArrowProxy<T>` , um eine Verwendung mit STL-Containern zu ermöglichen. Weitere Informationen finden Sie unter "VectorProxy-Elemente" weiter unten in diesem Artikel.

- C++ / CX--Auflistungstypen unterstützen die gleichen Threadsicherheitsgarantien wie STL-Containern.

- [Windows::Foundation::Collections::IObservableVector](/uwp/api/Windows.Foundation.Collections.IObservableVector_T_) und [Windows::Foundation::Collections::IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) definieren Ereignisse, die ausgelöst werden, wenn die Auflistung auf unterschiedliche Weise ändert. Durch Implementierung dieser Schnittstellen unterstützen  [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) und [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) eine Datenbindung mit XAML-Auflistungen. Wenn Sie beispielsweise einen `Vector` mit einer Datenbindung zu einem `Grid`haben und ein Element einer Auflistung hinzufügen, wird die Änderung in die Benutzeroberfläche des Rasters übernommen.

## <a name="vector-usage"></a>Verwendung von Vektoren

Wenn Ihre Klasse hat einen sequenzcontainer an eine andere Windows-Runtime-Komponente zu übergeben, verwenden Sie [Collections:: IVector\<T >](https://msdn.microsoft.com/library/windows/apps/br206631.aspx) als Parameter oder Rückgabetyp und [Platform:: Collections::vector\<T >](../cppcx/platform-collections-vector-class.md) als konkrete Implementierung. Wenn Sie versuchen, einen `Vector` -Typ in einem öffentlichen Rückgabewert oder Parameter zu verwenden, wird der Compilerfehler C3986 ausgelöst. Sie können das Problem beheben, indem Sie den `Vector` in einen `IVector`ändern.

> [!IMPORTANT]
> Wenn Sie eine Sequenz im eigenen Programm übergeben, verwenden Sie entweder `Vector` oder `std::vector` , da sie effizienter als `IVector`sind. Verwenden Sie `IVector` nur, wenn Sie den Container über die ABI übergeben.
>
> Der Windows-Runtime-Typsystem unterstützt nicht das Konzept von verzweigten Arrays, und Sie können nicht aus diesem Grund übergeben Sie ein IVector < Platform:: Array\<T >> als Rückgabewert oder Methodenparameter. Um ein verzweigtes Array oder eine Sequenz von Sequenzen an die ABI zu übergeben, verwenden Sie `IVector<IVector<T>^>`.

`Vector<T>` stellt die Methoden bereit, die zum Hinzufügen, Entfernen und das Zugreifen auf Elemente in der Auflistung erforderlich sind, und kann implizit zu `IVector<T>`konvertiert werden. Sie können STL-Algorithmen auch bei Instanzen von `Vector<T>`verwenden. Das folgende Beispiel veranschaulicht die grundlegende Verwendung. Die [begin function](../cppcx/begin-function.md) und [end function](../cppcx/end-function.md) hier stammen vom Namespace `Platform::Collections` und nicht vom Namespace `std` .

[!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]

Wenn Sie vorhandenen Code verfügen, die verwendet `std::vector` und Sie möchten, in einer Windows-Runtime-Komponente verwenden, verwenden Sie einfach eine der der `Vector` Konstruktoren, die akzeptiert eine `std::vector` oder ein Paar von Iteratoren zum Erstellen einer `Vector` an der Stelle, wo Sie übergeben, die die Auflistung über die ABI. Im folgenden Beispiel wird gezeigt, wie der `Vector` -Bewegungskonstruktor zur effizienten Initialisierung von `std::vector`verwendet wird. Nach dem Verschiebungsvorgang ist die ursprüngliche `vec` -Variable nicht mehr gültig.

[!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]

Wenn Sie einen Vektor von Zeichenfolgen haben, die Sie an einem zukünftigen Punkt über die ABI übergeben müssen, müssen Sie entscheiden, ob die Zeichenfolgen zuerst als `std::wstring` -Typen oder als `Platform::String^` -Typen erstellt werden sollen. Wenn die Zeichenfolgen einen hohen Verarbeitungsaufwand erfordern, verwenden Sie `wstring`. Erstellen Sie andernfalls die Zeichenfolgen als `Platform::String^` -Typen, und vermeiden Sie den Aufwand einer späteren Konvertierung. Außerdem müssen Sie festlegen, ob diese Zeichenfolgen intern in einem `std:vector` oder in einem `Platform::Collections::Vector` abgelegt werden sollen. Im Allgemeinen sollten Sie `std::vector` verwenden und nur dann einen `Platform::Vector` erstellen, wenn Sie den Container über die ABI übergeben.

## <a name="value-types-in-vector"></a>Werttypen im Vektor

Jedes in [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) gespeicherte Element muss einen Übereinstimmungsvergleich unterstützen, und zwar entweder implizit oder mithilfe eines benutzerdefinierten [std::equal_to](../standard-library/equal-to-struct.md) -Vergleichsoperators, den Sie bereitstellen. Alle Verweistypen und alle skalaren Typen unterstützen implizit Übereinstimmungsvergleiche. Für nicht skalare Werttypen wie [Windows::Foundation::DateTime](https://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx), oder für benutzerdefinierte Vergleiche – z. B. `objA->UniqueID == objB->UniqueID`– müssen Sie ein benutzerdefiniertes Funktionsobjekt bereitstellen.

## <a name="vectorproxy-elements"></a>VectorProxy-Elemente

[Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md) und [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) ermöglichen die Verwendung von `range for` -Schleifen und-Algorithmen wie [Std:: Sort](../standard-library/algorithm-functions.md#sort) mit einer [ IVector\<T >](https://msdn.microsoft.com/library/windows/apps/br206631.aspx) Container. Aber `IVector` Elemente können nicht zugegriffen werden, mithilfe C++-Zeiger zu dereferenzieren, sie können nur über zugegriffen werden [GetAt](https://msdn.microsoft.com/library/windows/apps/br206634.aspx) und ["SetAt"](https://msdn.microsoft.com/library/windows/apps/br206642.aspx) Methoden. Daher verwenden diese Iteratoren die Proxyklassen `Platform::Details::VectorProxy<T>` und `Platform::Details::ArrowProxy<T>` , um Zugriff auf die einzelnen Elemente über die Operatoren `*`, `->`und `[]` zu ermöglichen, wie von STL gefordert. Streng genommen ist bei einer `IVector<Person^> vec`der Typ von `*begin(vec)` `VectorProxy<Person^>`. Allerdings ist das Proxyobjekt fast immer für Ihren Code transparent. Diese Proxyobjekte werden nicht dokumentiert, da sie nur für die interne Verwendung durch Iteratoren bestimmt sind. Es ist jedoch hilfreich zu wissen, wie der Mechanismus funktioniert.

Wenn Sie eine `range for` -Schleife über `IVector` -Container verwenden, verwenden Sie `auto&&` , damit die Iteratorvariable korrekt an die `VectorProxy` -Elemente gebunden werden kann. Wenn Sie `auto` oder `auto&`verwenden, wird die Compilerwarnung C4239 ausgelöst und `VectoryProxy` wird im Text der Warnung erwähnt.

Die folgende Abbildung zeigt ein Beispiel für eine `range for` -Schleife über eine `IVector<Person^>`. Beachten Sie, dass die Ausführung am Haltepunkt in Zeile 64 beendet wird. Im Fenster **Schnellüberwachung** wird angezeigt, dass die Iteratorvariable `p` tatsächlich eine `VectorProxy<Person^>` ist, die die Membervariablen `m_v` und `m_i` aufweist. Wenn Sie jedoch `GetType` für diese Variable aufrufen, gibt sie den identischen Typ zur Instanz `Person` `p2`zurück. Die Schlussfolgerung daraus: Obwohl möglicherweise `VectorProxy` und `ArrowProxy` in der **Schnellüberwachung**, in bestimmten Compilerfehlern des Debuggers oder an anderen Stellen angezeigt werden, müssen Sie sie in der Regel nicht explizit codieren.

![VectorProxy in Bereich&#45;for-Schleife basierend](../cppcx/media/vectorproxy-1.png "VectorProxy_1")

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

In diesem Beispiel wird gezeigt, wie Elemente eingefügt, und suchen sie einem [Platform::Collections::Map](../cppcx/platform-collections-map-class.md), und wieder die `Map` als eine nur-Lese [Windows::Foundation::Collections::IMapView] / Uwp/api / Windows.Foundation.Collections.IMapView_K_V_)-Typ.

[!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]

Im Allgemeinen sollten Sie für die interne Zuordnungsfunktionalität aus Leistungsgründen vorzugsweise den Typ `std::map` verwenden. Wenn Sie den Container über die ABI übergeben müssen, erstellen eine [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) aus der [Std:: Map](../standard-library/map-class.md) und Zurückgeben der `Map` als ein [Windows:: Foundation:: Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_). Wenn Sie versuchen, einen `Map` -Typ in einem öffentlichen Rückgabewert oder Parameter zu verwenden, wird der Compilerfehler C3986 ausgelöst. Sie können das Problem beheben, indem Sie den `Map` in einen `IMap`ändern. In einigen Fällen, beispielsweise wenn Sie nur wenige Suchen oder Einfügungen ausführen und die Auflistung häufig über die ABI übergeben, ist es möglicherweise weniger Aufwand, gleich `Platform::Collections::Map` zu verwenden und die Konvertierung von `std::map`zu vermeiden. Vermeiden Sie in jedem Fall Such- und Einfügevorgänge bei einer `IMap` , da diese der am wenigsten leistungsfähige der drei Typen ist. Konvertieren Sie in `IMap` nur dann, wenn Sie den Container über die ABI übergeben.

## <a name="value-types-in-map"></a>Werttypen in der Zuordnung

Elemente in [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) werden sortiert. Jedes in `Map` zu speichernde Element muss den Kleiner-als-Vergleich in strenger, schwacher Reihenfolg unterstützen, und zwar entweder implizit oder mithilfe eines benutzerdefinierten [stl::less](../standard-library/less-struct.md) -Vergleichsoperators, den Sie bereitstellen. Skalare Typen unterstützen den Vergleich implizit. Für nicht skalare Werttypen wie `Windows::Foundation::DateTime`oder für benutzerdefinierte Vergleiche – z. B. `objA->UniqueID < objB->UniqueID`– müssen Sie einen benutzerdefinierten Vergleichsoperator bereitstellen.

## <a name="collection-types"></a>Auflistungstypen

Auflistungen sind in vier Kategorien unterteilt: änderbare Versionen und schreibgeschützte Versionen von Sequenzauflistungen und assoziativen Auflistungen. Darüber hinaus C++ / CX verbessert die Auflistungen durch Bereitstellung von drei iteratorklassen, die die Zugriff auf Auflistungen vereinfachen.

Elemente einer änderbaren Auflistung können geändert werden, aber Elemente einer schreibgeschützten Auflistung, die als *Ansicht*bekannt ist, können nur gelesen werden. Elemente einer [Vector](../cppcx/platform-collections-vector-class.md) oder[Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) -Auflistung kann zugegriffen werden, mithilfe eines Iterators oder der Auflistung [Vector:: GetAt](../cppcx/platform-collections-vector-class.md#getat) und einem Index. Elemente einer assoziativen Auflistung können zugegriffen werden, indem Sie der Auflistung [Map:: Lookup](../cppcx/platform-collections-map-class.md#lookup) und einen Schlüssel.

[Platform::Collections::Map-Klasse](../cppcx/platform-collections-map-class.md)<br/>
Eine änderbare, assoziative Auflistung. Zuordnungselemente sind Schlüssel-Wert-Paare. Sowohl das Suchen nach einem Schlüssel, um den zugeordneten Wert abzurufen, als auch das Durchlaufen aller Schlüssel-Wert-Paare werden unterstützt.

`Map` und `MapView` sind als Vorlagen für `<K, V, C = std::less<K>>`vorhanden. Daher können Sie den Vergleichsoperator anpassen.  Darüber hinaus sind `Vector` und `VectorView` auf `<T, E = std::equal_to<T>>` vorlagenbasiert, damit Sie das Verhalten von `IndexOf()`anpassen können. Dies ist vor allem für `Vector` und `VectorView` von Wertstrukturen wichtig. Um beispielsweise einen Vektor erstellen\<Windows::Foundation::DateTime >, müssen Sie einen benutzerdefinierten Vergleichsoperator bereitstellen, da es sich bei "DateTime" nicht überlädt den Operator ==-Operator.

[Platform::Collections::MapView-Klasse](../cppcx/platform-collections-mapview-class.md)<br/>
Eine schreibgeschützte Version von `Map`.

[Platform::Collections::Vector Class](../cppcx/platform-collections-vector-class.md)<br/>
Eine änderbare Sequenzauflistung. `Vector<T>` unterstützt stetige und amortisierte stetige [Append](../cppcx/platform-collections-vector-class.md#append) -Direktzugriffsvorgänge.

[Platform::Collections::VectorView-Klasse](../cppcx/platform-collections-vectorview-class.md)<br/>
Eine schreibgeschützte Version von `Vector`.

[Platform::Collections::InputIterator-Klasse](../cppcx/platform-collections-inputiterator-class.md)<br/>
Ein STL-Iterator, der die Anforderungen eines STL-Eingabeiterators erfüllt.

[Platform::Collections::VectorIterator-Klasse](../cppcx/platform-collections-vectoriterator-class.md)<br/>
Ein STL-Iterator, der die Anforderungen eines änderbaren STL-Iterators mit Direktzugriff erfüllt.

[Platform::Collections::VectorViewIterator-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)<br/>
Ein STL-Iterator, der die Anforderungen eines STL-  `const` -Iterators mit Direktzugriff erfüllt.

### <a name="begin-and-end-functions"></a>begin() und end() -Funktionen

Vereinfachen Sie die Verwendung von STLS zu verarbeiten `Vector`, `VectorView`, `Map`, `MapView`, und beliebige `Windows::Foundation::Collections` Objekte, C++ / CX unterstützt die Überladungen von der [begin-Funktion](../cppcx/begin-function.md) und [End Funktion](../cppcx/end-function.md) nicht-Memberfunktionen.

Die folgende Tabelle zeigt die verfügbaren Iteratoren und Funktionen auf.

|Iterators|Funktionen|
|---------------|---------------|
|[Platform::Collections::VectorIterator\<T>](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> (Speichert intern [Collections:: IVector\<T >](https://msdn.microsoft.com/library/windows/apps/br206631.aspx) und int.)|[Begin](../cppcx/begin-function.md)/ [End](../cppcx/end-function.md)([Collections:: IVector\<T >](https://msdn.microsoft.com/library/windows/apps/br206631.aspx))|
|[Platform::Collections::VectorViewIterator\<T>](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> (Speichert intern [IVectorView\<T >](https://msdn.microsoft.com/library/windows/apps/br226058.aspx)^ und int.)|[Begin](../cppcx/begin-function.md)/ [End](../cppcx/end-function.md) ([IVectorView\<T >](https://msdn.microsoft.com/library/windows/apps/br226058.aspx)^)|
|[Platform::Collections::InputIterator\<T>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Speichert intern [IIterator\<T >](https://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ und T.)|[Begin](../cppcx/begin-function.md)/ [End](../cppcx/end-function.md) ([IIterable\<T >](https://msdn.microsoft.com/library/windows/apps/br226024.aspx))|
|[Platform::Collections::InputIterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Speichert intern [IIterator\<T >](https://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ und T.)|[Begin](../cppcx/begin-function.md)/ [End](../cppcx/end-function.md) ([IMap\<K, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).|
|[Platform::Collections::InputIterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Speichert intern [IIterator\<T >](https://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ und T.)|[Begin](../cppcx/begin-function.md)/ [End](../cppcx/end-function.md) ([Windows:: Foundation::Collections::IMapView]/uwp/api/Windows.Foundation.Collections.IMapView_K_V_))|

### <a name="collection-change-events"></a>Änderungsereignisse bei Auflistungen

`Vector` und `Map` unterstützen Datenbindung in XAML-Auflistungen durch Implementieren von Ereignissen, die auftreten, wenn ein Auflistungsobjekt geändert oder zurückgesetzt wird oder wenn ein Element in einer Auflistung eingefügt, aus dieser entfernt oder geändert wird. Sie können zwar eigene Typen schreiben, die Datenbindung unterstützen, können jedoch nicht von `Map` oder von `Vector` erben, da diese Typen versiegelt sind.

Die [Windows::Foundation::Collections::VectorChangedEventHandler](/uwp/api/windows.foundation.collections.vectorchangedeventhandler) und [Windows::Foundation::Collections::MapChangedEventHandler](/uwp/api/windows.foundation.collections.mapchangedeventhandler) Delegaten geben die Signaturen für Ereignishandler für Änderungsereignisse bei Auflistungen. Die [Windows::Foundation::Collections::CollectionChange](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx) öffentlichen Enumerationsklasse und `Platform::Collection::Details::MapChangedEventArgs` und `Platform::Collections::Details::VectorChangedEventArgs` -Verweisklassen speichern die Ereignisargumente, um zu bestimmen, welche das Ereignis verursacht hat. *`EventArgs` -Typen werden im `Details` -Namespace definiert, da Sie sie nicht explizit erstellen oder nutzen müssen, wenn Sie `Map` oder `Vector`verwenden.

## <a name="see-also"></a>Siehe auch

[Typsystem](../cppcx/type-system-c-cx.md)<br/>
[Sprachreferenz zu Visual C++](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)
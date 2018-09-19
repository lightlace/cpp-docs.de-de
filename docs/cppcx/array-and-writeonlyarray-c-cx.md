---
title: Array und WriteOnlyArray (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4423616a9a05268a68e6eff095a2503c3a1d0590
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103670"
---
# <a name="array-and-writeonlyarray-ccx"></a>Array und WriteOnlyArray (C++/CX)

Kostenlos können reguläre Arrays im C-Stil oder [Std:: Array](../standard-library/array-class-stl.md) in einem C++ / CX-Programms (obwohl [Std:: vector](../standard-library/vector-class.md) ist häufig die bessere Wahl), aber in einer beliebigen API, die in Metadaten veröffentlicht wird, müssen Sie ein Array im C-Format konvertieren oder Vektor zu einem [Platform:: Array](../cppcx/platform-array-class.md) oder [Platform:: writeonlyarray](../cppcx/platform-writeonlyarray-class.md) Typ je nachdem, wie sie verwendet wird. Der [Platform::Array](../cppcx/platform-array-class.md) -Typ ist weder so effizient noch so leistungsfähig wie [std::vector](../standard-library/vector-class.md). Als allgemeine Richtlinie sollten Sie daher dessen Verwendung im internen Code vermeiden, da dieser viele Vorgänge mit den Arrayelementen ausführt.

Die folgenden Arraytypen können über die ABI übergeben werden:

1. const Platform::Array^

1. Platform::Array^*

1. Platform::WriteOnlyArray

1. Rückgabewert von Platform::Array^

Diese Arraytypen werden verwendet, um die drei Typen von arraymustern zu implementieren, die von der Windows-Runtime definiert sind.

PassArray wird verwendet, wenn der Aufrufer ein Array an eine Methode übergeben. Die C++-eingabeparametertyp ist `const` [Platform:: Array](../cppcx/platform-array-class.md)\<T >.

FillArray verwendet, wenn der Aufrufer ein Array für die zu füllende Methode übergibt. Die C++-eingabeparametertyp ist [Platform:: writeonlyarray](../cppcx/platform-writeonlyarray-class.md)\<T >.

ReceiveArray wird verwendet, wenn der Aufrufer ein Array empfängt, die die Methode belegt. In C++/CX können Sie das Array im Rückgabewert als Array^ oder in Form eines out-Parameters als Array^*-Typ zurückgeben.

## <a name="passarray-pattern"></a>PassArray-Muster

Wenn vom Clientcode ein Array an eine C++-Methode übergeben und das Array von der Methode nicht geändert wird, dann wird das Array von der Methode als const Array^ akzeptiert. Auf der Ebene der Windows-Runtime-Anwendung-anwendungsbinärschnittstelle (ABI) wird dies als PassArray bezeichnet. Im nächsten Beispiel wird gezeigt, wie ein Array übergeben wird, das in JavaScript zu einer C++-Funktion zugeordnet ist, die aus dem Array liest.

[!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]

Im folgenden Codeausschnitt wird die C++-Methode veranschaulicht:

[!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]

## <a name="receivearray-pattern"></a>ReceiveArray-Muster

Im ReceiveArray-Muster wird ein Array vom Clientcode deklariert und an eine Methode übergeben, mit der Speicher für das Array zugeordnet und es initialisiert wird. Der C++-eingabeparametertyp ist ein Zeiger auf das Caretzeichen: `Array<T>^*`. Im folgenden Beispiel wird gezeigt, wie ein Arrayobjekt in JavaScript deklariert und an eine C++-Funktion übergeben wird, die Speicher zuordnet, Elemente initialisiert und das Arrayobjekt an JavaScript zurückgibt. Von JavaScript wird das zugeordnete Array als Rückgabewert interpretiert, von der C++-Funktion jedoch als out-Parameter.

[!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]

Der folgende Codeausschnitt zeigt zwei Möglichkeiten zur Implementierung der C++-Methode:

[!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]

## <a name="fill-arrays"></a>Füllbereichsarrays

Wenn Sie ein Array im Aufrufer zuordnen und es im Aufgerufenen initialisieren oder ändern möchten, verwenden Sie `WriteOnlyArray`. Im nächsten Beispiel wird gezeigt, wie eine C++-Funktion, die `WriteOnlyArray` verwendet, implementiert und aus JavaScript aufgerufen wird.

[!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]

Der folgende Codeausschnitt zeigt, wie die C++-Methode implementiert wird:

[!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]

## <a name="array-conversions"></a>Arraykonvertierungen

In diesem Beispiel wird gezeigt, wie ein [Platform::Array](../cppcx/platform-array-class.md) verwendet wird, um andere Arten von Auflistungen zu erstellen:

[!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]

Im nächsten Beispiel wird gezeigt, wie ein [Platform::Array](../cppcx/platform-array-class.md) aus einem Array im C-Format erstellt und von einer öffentlichen Methode zurückgegeben wird.

[!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]

## <a name="jagged-arrays"></a>Verzweigte Arrays

Das Windows Runtime-Typsystem unterstützt nicht das Konzept von verzweigten Arrays. Deshalb können Sie ein `IVector<Platform::Array<T>>` nicht als Rückgabewert oder Methodenparameter in einer öffentlichen Methode übergeben. Um ein verzweigtes Array oder eine Sequenz von Sequenzen an die ABI zu übergeben, verwenden Sie `IVector<IVector<T>^>`.

## <a name="use-arrayreference-to-avoid-copying-data"></a>Verwendung von ArrayReference, um das Kopieren von Daten zu vermeiden

In einigen Szenarien, in denen Daten über die ABI an ein [Platform::Array](../cppcx/platform-array-class.md)übergeben werden und diese Daten aus Effizienzgründen letztlich in einem Array im C-Format verarbeitet werden sollen, können Sie [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) verwenden, um den zusätzlichen Kopiervorgang zu vermeiden. Wenn Sie [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) als Argument an einen Parameter übergeben, der ein `Platform::Array`akzeptiert, speichert `ArrayReference` die Daten direkt in ein angegebenes Array im C-Format. Beachten Sie, dass `ArrayReference` nicht über eine Sperre für die Quelldaten verfügt. Wenn diese Daten geändert oder in einem anderen Thread gelöscht werden, bevor der Aufruf abgeschlossen wird, sind die Ergebnisse nicht definiert.

Der folgende Codeausschnitt veranschaulicht, wie die Ergebnisse einer [DataReader](https://msdn.microsoft.com/library/windows/apps/windows.storage.streams.datareader.aspx) Vorgang in einer `Platform::Array` (das übliche Muster), und wie `ArrayReference` zum Kopieren der Daten direkt in ein Array im C-Format:

[!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]

## <a name="avoid-exposing-an-array-as-a-property"></a>Vermeiden, ein Array als Eigenschaft verfügbar zu machen

Im Allgemeinen sollten Sie einen `Platform::Array` -Typ möglichst nicht als Eigenschaft in einer Verweisklasse verfügbar machen, da das gesamte Array zurückgegeben wird, auch wenn der Clientcode nur versucht, auf ein einzelnes Element zuzugreifen. Wenn Sie einen sequenzcontainer als Eigenschaft in einer öffentlichen Verweisklasse verfügbar machen möchten [Windows::Foundation::IVector](https://msdn.microsoft.com/library/windows/apps/br206631.aspx) ist die bessere Wahl. In privaten oder internen APIs (die nicht in Metadaten veröffentlicht werden) sollten Sie die Verwendung eines C++-Standardcontainers wie [std::vector](../standard-library/vector-class.md)erwägen.

## <a name="see-also"></a>Siehe auch

[Typsystem](../cppcx/type-system-c-cx.md)<br/>
[Sprachreferenz zu Visual C++](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)
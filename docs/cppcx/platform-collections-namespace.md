---
title: Platform::Collections-Namespace
ms.date: 01/18/2018
ms.topic: reference
f1_keywords:
- collection/Platform::Collections
helpviewer_keywords:
- Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
ms.openlocfilehash: 025c25d6c01ab9a28c68574cc2a13e09dbf28388
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161744"
---
# <a name="platformcollections-namespace"></a>Platform::Collections-Namespace

Platform:: Collections-Namespace enthält die `Map`, `MapView`, `Vector`, und `VectorView` Klassen. Diese Klassen sind konkrete Implementierungen der entsprechenden Schnittstellen, die im Namespace [Windows::Foundation::Collections](/uwp/api/Windows.Foundation.Collections) definiert sind. Die konkreten Auflistungstypen können nicht über die ABI hinweg portiert werden (z. B. beim Aufruf eines Javascript- oder C#-Programms in eine C++-Komponente). Sie sind allerdings implizit in ihre entsprechenden Schnittstellentypen konvertierbar. Wenn Sie z. B. eine öffentliche Methode implementieren, die eine Auflistung füllt und zurückgibt, verwenden Sie [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) , um die Auflistung intern zu implementieren. Verwenden Sie [Windows::Foundation::Collections::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_) als Rückgabetyp. Weitere Informationen finden Sie unter [Sammlungen](../cppcx/collections-c-cx.md) und [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

Sie können Platform::Collections::Vector aus [std::vector](../standard-library/vector-class.md) und [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) aus [std::map](../standard-library/map-class.md)erstellen.

Darüber hinaus bietet der Platform:: Collections-Namespace Unterstützung für Back INSERT- und Eingabe-Iteratoren und `Vector` und `VectorView` Iteratoren.

Sie müssen einschließen (`#include`) den Header "Collection.h" bereit, die Typen in der Platform:: Collections-Namespace verwenden.

## <a name="syntax"></a>Syntax

```cpp
#include <collection.h>
using namespace Platform::Collections;
```

### <a name="members"></a>Member

Dieser Namespace enthält die folgenden Member.

|Name|Beschreibung|
|----------|-----------------|
|[Platform::Collections::BackInsertIterator-Klasse](../cppcx/platform-collections-backinsertiterator-class.md)|Stellt einen Iterator dar, der ein Element am Ende einer Auflistung einfügt.|
|[Platform::Collections::InputIterator-Klasse](../cppcx/platform-collections-inputiterator-class.md)|Stellt einen Iterator dar, der ein Element am Anfang einer Auflistung einfügt.|
|[Platform::Collections::Map-Klasse](../cppcx/platform-collections-map-class.md)|Stellt eine änderbare Auflistung von Schlüssel-Wert-Paaren dar, auf die über einen Schlüssel zugegriffen wird. Wie bei [std::map](../standard-library/map-class.md).|
|[Platform::Collections::MapView-Klasse](../cppcx/platform-collections-mapview-class.md)|Stellt eine schreibgeschützte Auflistung von Schlüssel-Wert-Paaren dar, auf die über einen Schlüssel zugegriffen wird.|
|[Platform::Collections::Vector Class](../cppcx/platform-collections-vector-class.md)|Stellt eine änderbare Sequenz von Elementen dar. Wie bei [std::vector](../standard-library/vector-class.md).|
|[Platform::Collections::VectorIterator-Klasse](../cppcx/platform-collections-vectoriterator-class.md)|Stellt einen Iterator dar, der eine `Vector` -Auflistung durchläuft.|
|[Platform::Collections::VectorView-Klasse](../cppcx/platform-collections-vectorview-class.md)|Stellt eine schreibgeschützte Sequenz von Elementen dar.|
|[Platform::Collections::VectorViewIterator-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)|Stellt einen Iterator dar, der eine `VectorView` -Auflistung durchläuft.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[Plattformnamespace](../cppcx/platform-namespace-c-cx.md)

### <a name="requirements"></a>Anforderungen

**Metadaten:** platform.winmd

**Namespace:** Platform::Collections

**Compileroption:** /ZW

## <a name="see-also"></a>Siehe auch

[Plattform-Namespace](../cppcx/platform-namespace-c-cx.md)

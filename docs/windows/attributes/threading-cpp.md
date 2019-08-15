---
title: Threading (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: db2940ec3536ae8ea29ba40db84ea869ecb3d0ac
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513930"
---
# <a name="threading-c"></a>threading (C++)

Gibt das Threading Modell für ein COM-Objekt an.

## <a name="syntax"></a>Syntax

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>Parameter

*model*<br/>
Optionale Eines der folgenden Threading Modelle:

- `apartment`(Apartment Threading)

- `neutral`(.NET Framework Komponenten ohne Benutzeroberfläche)

- `single`(einfaches Threading)

- `free`(freies Threading)

- `both`(Apartment und freies Threading)

Der Standardwert ist `apartment`.

## <a name="remarks"></a>Hinweise

Das **Threading** C++ Attribut wird nicht in der generierten IDL-Datei angezeigt, wird jedoch in der Implementierung des COM-Objekts verwendet.

Wenn in ATL-Projekten auch das [Co-Klasse](coclass.md) -Attribut vorhanden ist, wird das von *Model* angegebene Threading Modell als Vorlagen Parameter an die [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) -Klasse übergeben, die durch `coclass` das-Attribut eingefügt wird.

Das **Threading** Attribut schützt auch den Zugriff auf eine [event_source](event-source.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **Threading**finden Sie im [lizenzierten](licensed.md) Beispiel.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**coclass**|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[COM-Attribute](com-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Multithreadingunterstützung für älteren Code (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Neutrale Apartments](/windows/win32/cossdk/neutral-apartments)
---
title: Threading (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: cdebf06a62ebbd1d8648b9777fe200bc7a373261
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038277"
---
# <a name="threading-c"></a>threading (C++)

Gibt das Threadingmodell für eine COM-Objekt.

## <a name="syntax"></a>Syntax

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>Parameter

*model*<br/>
(Optional) Eine der folgenden threading Modelle:

- `apartment` (Apartmentthreading für Anwendungen)

- `neutral` (.NET Framework-Komponenten ohne Benutzeroberfläche)

- `single` (einfaches threading)

- `free` (freies threading)

- `both` ("Apartment" und "Freies threading")

Der Standardwert ist `apartment`.

## <a name="remarks"></a>Hinweise

Die **threading** C++-Attribut nicht in der generierten IDL-Datei angezeigt, aber in der Implementierung des COM-Objekts verwendet werden.

In ATL-Projekte Wenn die [Co-Klasse](coclass.md) Attribut vorhanden ist, wird das Threadingmodell gemäß *Modell* wird als der Vorlagenparameter übergeben, die [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) Klasse , eingefügt, indem die `coclass` Attribut.

Die **threading** Attribut schützt auch den Zugriff auf eine [Event_source](event-source.md).

## <a name="example"></a>Beispiel

Finden Sie unter den [lizenziert](licensed.md) Beispiel für ein Beispiel für die Verwendung von **threading**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**class**, **struct**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**coclass**|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[COM-Attribute](com-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Multithreadingunterstützung für älteren Code (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Neutrale-Apartments](/windows/desktop/cossdk/neutral-apartments)
---
title: Threading (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.threading
dev_langs:
- C++
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6b343ec9342199727122ac89f6df77e532429ad
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792003"
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
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**coclass**|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[COM-Attribute](com-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Multithreadingunterstützung für älteren Code (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Neutrale-Apartments](/windows/desktop/cossdk/neutral-apartments)  
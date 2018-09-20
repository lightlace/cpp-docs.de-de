---
title: Threading (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 8ab2699781526ee12784f7c048cd9a833526fd30
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414996"
---
# <a name="threading-c"></a>threading (C++)

Gibt das Threadingmodell für eine COM-Objekt.

## <a name="syntax"></a>Syntax

```cpp
[ threading(
   model=enumeration
) ]
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

In ATL-Projekte Wenn die [Co-Klasse](../windows/coclass.md) Attribut vorhanden ist, wird das Threadingmodell gemäß *Modell* wird als der Vorlagenparameter übergeben, die [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) Klasse , eingefügt, indem die `coclass` Attribut.

Die **threading** Attribut schützt auch den Zugriff auf eine [Event_source](../windows/event-source.md).

## <a name="example"></a>Beispiel

Finden Sie unter den [lizenziert](../windows/licensed.md) Beispiel für ein Beispiel für die Verwendung von **threading**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**coclass**|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[COM-Attribute](../windows/com-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[Klassenattribute](../windows/class-attributes.md)<br/>
[Multithreadingunterstützung für älteren Code (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Neutrale-Apartments](/windows/desktop/cossdk/neutral-apartments)  
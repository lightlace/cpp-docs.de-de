---
title: Microsoft::WRL::Wrappers-Namespace
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: eac85d10351a141ce561da4272d033644128608f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535485"
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers-Namespace

Definiert die Resource Acquisition ist Initialisierung (RAII) Wrappertypen, die die Verwaltung der Lebensdauer von Objekten, Zeichenfolgen und Handles zu vereinfachen.

## <a name="syntax"></a>Syntax

```cpp
namespace Microsoft::WRL::Wrappers;
```

## <a name="members"></a>Member

### <a name="typedefs"></a>Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|

### <a name="classes"></a>Klassen

|Name|Beschreibung|
|----------|-----------------|
|[CriticalSection-Klasse](../windows/criticalsection-class.md)|Stellt ein kritisches Abschnittsobjekt dar.|
|[Ereignisklasse (WRL)](../windows/event-class-wrl.md)|Stellt ein Ereignis dar.|
|[HandleT-Klasse](../windows/handlet-class.md)|Stellt ein Handle für ein Objekt dar.|
|[HString-Klasse](../windows/hstring-class.md)|Bietet Unterstützung für die Bearbeitung von HSTRING-Handles.|
|[HStringReference-Klasse](../windows/hstringreference-class.md)|Stellt ein HSTRING dar, das aus einer vorhandenen Zeichenfolge erstellt wird.|
|[Mutex-Klasse](../windows/mutex-class.md)|Stellt ein Synchronisierungsobjekt, das ausschließlich auf eine freigegebene Ressource steuert.|
|[RoInitializeWrapper-Klasse](../windows/roinitializewrapper-class.md)|Initialisiert die Windows-Runtime.|
|[Semaphore-Klasse](../windows/semaphore-class.md)|Stellt ein Synchronisierungsobjekt, das eine freigegebene Ressource steuert, die eine begrenzte Anzahl von Benutzern unterstützen können.|
|[SRWLock-Klasse](../windows/srwlock-class.md)|Stellt eine slim Reader-/Writer-Sperre.|

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)
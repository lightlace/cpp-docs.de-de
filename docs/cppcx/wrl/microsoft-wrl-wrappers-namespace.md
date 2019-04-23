---
title: Microsoft::WRL::Wrappers-Namespace
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: 4b88ad0da31321a696c1238f1c9838d3b3a1c927
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030114"
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
|[CriticalSection-Klasse](criticalsection-class.md)|Stellt ein kritisches Abschnittsobjekt dar.|
|[Ereignisklasse (WRL)](event-class-wrl.md)|Stellt ein Ereignis dar.|
|[HandleT-Klasse](handlet-class.md)|Stellt ein Handle für ein Objekt dar.|
|[HString-Klasse](hstring-class.md)|Bietet Unterstützung für die Bearbeitung von HSTRING-Handles.|
|[HStringReference-Klasse](hstringreference-class.md)|Stellt ein HSTRING dar, das aus einer vorhandenen Zeichenfolge erstellt wird.|
|[Mutex-Klasse](mutex-class.md)|Stellt ein Synchronisierungsobjekt, das ausschließlich auf eine freigegebene Ressource steuert.|
|[RoInitializeWrapper-Klasse](roinitializewrapper-class.md)|Initialisiert die Windows-Runtime.|
|[Semaphore-Klasse](semaphore-class.md)|Stellt ein Synchronisierungsobjekt, das eine freigegebene Ressource steuert, die eine begrenzte Anzahl von Benutzern unterstützen können.|
|[SRWLock-Klasse](srwlock-class.md)|Stellt eine slim Reader-/Writer-Sperre.|

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)
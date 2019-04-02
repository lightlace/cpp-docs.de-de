---
title: TerminateMap-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: 17d02ea9cade0301798a5d6625f8eb9a568cb2cc
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784295"
---
# <a name="terminatemap-function"></a>TerminateMap-Funktion

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()
```

### <a name="parameters"></a>Parameter

*module*<br/>
Ein [Modul](module-class.md).

*serverName*<br/>
Der Name einer Teilmenge von Klassenfactorys in das Modul, das vom Parameter angegebene *Modul*.

*forceTerminate*<br/>
**"true"** zum Beenden der Klasse sind Factorys unabhängig von der sie aktiv ist; **"false"** Klassenfactorys nicht beendet, wenn jede Factory aktiv ist.

## <a name="return-value"></a>Rückgabewert

**"true"** wären alle Klassenfactorys beendet ist, andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Klassenfactorys im angegebenen Modul wird heruntergefahren.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](microsoft-wrl-details-namespace.md)
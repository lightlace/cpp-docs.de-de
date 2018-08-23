---
title: TerminateMap-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
dev_langs:
- C++
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e56e3f48a3a58f25d03053867c195d11970893f9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601406"
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

*Modul*  
Ein [Modul](../windows/module-class.md).

*ServerName*  
Der Name einer Teilmenge von Klassenfactorys in das Modul, das vom Parameter angegebene *Modul*.

*forceTerminate*  
**"true"** zum Beenden der Klasse sind Factorys unabhängig von der sie aktiv ist; **"false"** Klassenfactorys nicht beendet, wenn jede Factory aktiv ist.

## <a name="return-value"></a>Rückgabewert

**"true"** wären alle Klassenfactorys beendet ist, andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Klassenfactorys im angegebenen Modul wird heruntergefahren.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)
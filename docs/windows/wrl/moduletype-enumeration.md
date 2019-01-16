---
title: ModuleType-Enumeration
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: 937649eada481f7c45359fa0816266f62dc03875
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335998"
---
# <a name="moduletype-enumeration"></a>ModuleType-Enumeration

Gibt an, ob ein Modul einen In-Process-Server oder einen Out-of-Process-Server unterstützen sollte. 

## <a name="syntax"></a>Syntax

```cpp
enum ModuleType;
```

## <a name="members"></a>Member

### <a name="values"></a>Werte

|Name|Beschreibung|
|----------|-----------------|
|`InProc`|In-Process-Server.|
|`OutOfProc`|Ein Out-of-Process-Server.|
|`DisableCaching`|Deaktivieren Sie Zwischenspeichermechanismus Modul.|
|`InProcDisableCaching`|Kombination von `InProc` und `DisableCaching`.|
|`OutOfProcDisableCaching`|Kombination von `OutOfProc` und `DisableCaching`.|

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)
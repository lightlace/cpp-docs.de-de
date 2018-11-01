---
title: ModuleType-Enumeration
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: d822d214d9bad564286cd2c7494c9f480abdcf00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524747"
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

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)
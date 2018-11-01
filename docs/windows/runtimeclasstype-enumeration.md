---
title: RuntimeClassType-Enumeration
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 62a82d5fab9fd22e23a5244d4fda3b7f5202304c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626810"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType-Enumeration

Gibt den Typ der [RuntimeClass](../windows/runtimeclass-class.md) -Instanz, die unterstützt wird.

## <a name="syntax"></a>Syntax

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>Member

### <a name="values"></a>Werte

|Name|Beschreibung|
|----------|-----------------|
|`ClassicCom`|Eine klassische COM-Runtime-Klasse.|
|`Delegate`|Entspricht `ClassicCom`.|
|`InhibitFtmBase`|Deaktiviert die `FtmBase` -Unterstützung während der `__WRL_CONFIGURATION_LEGACY__` ist nicht definiert.|
|`InhibitWeakReference`|Deaktiviert die Unterstützung von schwachen Verweis.|
|`WinRt`|Eine Windows-Runtime-Klasse.|
|`WinRtClassicComMix`|Die Kombination aus `WinRt` und `ClassicCom`.|

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)
---
title: RuntimeClassType-Enumeration
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 3b869be00cdc405569b82bdf3730f8d4ca4f3aab
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785706"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType-Enumeration

Gibt den Typ der [RuntimeClass](runtimeclass-class.md) -Instanz, die unterstützt wird.

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

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)
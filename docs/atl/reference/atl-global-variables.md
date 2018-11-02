---
title: Globale ATL-Variablen
ms.date: 12/06/2017
f1_keywords:
- ATLBASE/_pAtlModule
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
ms.openlocfilehash: 4f98b31d2454b7c6e903e5b5b87bceb4ddcb6961
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498318"
---
# <a name="atl-global-variables"></a>Globale ATL-Variablen

## <a name="patlmodule"></a>_pAtlModule

Eine globale Variable, die einen Zeiger auf das aktuelle Modul speichern.

```cpp
__declspec(selectany) CAtlModule * _pAtlModule
```

### <a name="remarks"></a>Hinweise

Methoden für diese globale Variable können verwendet werden, um die Funktionalität bereitzustellen, die die (nun veraltete) CComModule-Klasse in Visual C++ 6.0 bereitgestellt.

### <a name="example"></a>Beispiel

```cpp
LONG lLocks = _pAtlModule->GetLockCount();
```

### <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

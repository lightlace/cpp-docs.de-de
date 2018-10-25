---
title: Globale ATL-Variablen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/06/2017
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATLBASE/_pAtlModule
dev_langs:
- C++
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d33c2a3de5b94f522833db67dfb190ede3a8a63
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054956"
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

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
ms.openlocfilehash: 55844390b872cb0d94ff991ab79b8519388d009f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762459"
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


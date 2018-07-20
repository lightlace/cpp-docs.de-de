---
title: TerminateMap-Funktion | Microsoft Docs
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
ms.openlocfilehash: b4787fec0a6b4b9f55c500b66786372945d9a523
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890348"
---
# <a name="terminatemap-function"></a>TerminateMap-Funktion
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
## <a name="parameters"></a>Parameter  
 `module`  
 Ein [Modul](../windows/module-class.md).  
  
 `serverName`  
 Der Name einer Teilmenge von Klassenfactorys in das vom Parameter angegebene Modul `module`.  
  
 `forceTerminate`  
 `true` zum Beenden der Klasse sind Factorys unabhängig von der sie aktiv; `false` Klassenfactorys nicht beendet, wenn alle Factory aktiv ist.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn alle Klassenfactorys beendet wurden. andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Fährt den Klassenfactorys im angegebenen Modul.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)
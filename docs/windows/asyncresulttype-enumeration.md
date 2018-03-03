---
title: AsyncResultType-Enumeration | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
dev_langs:
- C++
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b654a4f27ca78cda680a7ceb69f0c6e2ea0db9a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType-Enumeration
Gibt den Typ des durch die Methode „GetResults()“ zurückgegebenen Ergebnisses zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
enum AsyncResultType;  
```  
  
## <a name="members"></a>Member  
  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`MultipleResults`|Ein Satz von mehreren Ergebnissen, die zwischen Start- und vor dem Aufruf von Close() progressiv dargestellt werden.|  
|`SingleResult`|Ein einzelnes Ergebnis, die angezeigt wird, nachdem das Abschlussereignis tritt auf.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)
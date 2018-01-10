---
title: "Makros für die Ausnahmebehandlung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
dev_langs: C++
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 424a65c44d7bb22d1fef6e21e1892967ecd3e9b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exception-handling-macros"></a>Behandlung von Ausnahmemakros
Diese Makros bieten Unterstützung für die Ausnahmebehandlung.  
  
|||  
|-|-|  
|[_ATLCATCH](#_atlcatch)|Anweisung(en) zur Behandlung von Fehlern, die in der zugeordneten auftreten `_ATLTRY`.|  
|[_ATLCATCHALL](#_atlcatchall)|Anweisung(en) zur Behandlung von Fehlern, die in der zugeordneten auftreten `_ATLTRY`.|  
|[_ATLTRY](#_atltry)|Markiert einen abgesicherte Codeabschnitt, in denen möglicherweise ein Fehler auftreten können.|  
  
## <a name="requirements"></a>Anforderungen:
**Header:** atldef.h

##  <a name="_atlcatch"></a>_ATLCATCH  
 Anweisung(en) zur Behandlung von Fehlern, die in der zugeordneten auftreten `_ATLTRY`.  
  
```
_ATLCATCH(e)
```  
  
### <a name="parameters"></a>Parameter  
 *e*  
 Die Ausnahme abgefangen.  
  
### <a name="remarks"></a>Hinweise  
 Wird in Verbindung mit `_ATLTRY`. Löst in C++ [catch (CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) für eine bestimmte Art von C++-Ausnahmen zu behandeln.  
  
##  <a name="_atlcatchall"></a>_ATLCATCHALL  
 Anweisung(en) zur Behandlung von Fehlern, die in der zugeordneten auftreten `_ATLTRY`.  
  
```
_ATLCATCHALL
```  
  
### <a name="remarks"></a>Hinweise  
 Wird in Verbindung mit `_ATLTRY`. Löst in C++ [catch(...) ](../../cpp/try-throw-and-catch-statements-cpp.md) für alle Typen von C++-Ausnahmen zu behandeln.  
  
##  <a name="_atltry"></a>_ATLTRY  
 Markiert einen abgesicherte Codeabschnitt, in denen möglicherweise ein Fehler auftreten können.  
  
```
_ATLTRY
```  
  
### <a name="remarks"></a>Hinweise  
 Wird in Verbindung mit [_ATLCATCH](#_atlcatch) oder [_ATLCATCHALL](#_atlcatchall). Löst in der C++-Symbol [versuchen](../../cpp/try-throw-and-catch-statements-cpp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)

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
ms.openlocfilehash: 906f6d499da04a6bee9da18dbbb6ad4b463c8fa6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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

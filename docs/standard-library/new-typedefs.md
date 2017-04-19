---
title: '&lt;new&gt; typedefs | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b652d0a1eac1615d1e1b0aed1df05d6a9ee661a3
ms.lasthandoff: 02/24/2017

---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; typedefs
||  
|-|  
|[new_handler](#new_handler)|  
  
##  <a name="new_handler"></a> new_handler  
 Der Typ verweist auf eine Funktion, die als neuer Handler geeignet ist.  
  
```
typedef void (*new_handler)();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Art von Handler-Funktion wird durch **operatornew** oder `operator new[]` aufgerufen, wenn diese eine Anforderung für zusätzlichen Speicher nicht erfüllen können.  
  
### <a name="example"></a>Beispiel  
  Unter [set_new_handler](../standard-library/new-functions.md#set_new_handler) finden Sie ein Beispiel mit `new_handler` als Rückgabewert.  
  
## <a name="see-also"></a>Siehe auch  
 [\<new>](../standard-library/new.md)





---
title: '&lt;new&gt; typedefs | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: e23ea06002dc840997a0e7202f581cd81ef407c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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




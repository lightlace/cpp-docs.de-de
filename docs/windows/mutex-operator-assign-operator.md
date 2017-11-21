---
title: 'Mutex:: Operator = | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
dev_langs: C++
helpviewer_keywords: operator= operator
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7b7a9e35bb356d0f3ebfd870105c0b8217d7f658
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="mutexoperator-operator"></a>Mutex::operator=-Operator
Weist (wechselt) der angegebene Mutex-Objekt in der aktuellen Mutex-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
Mutex& operator=(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `h`  
 Ein Rvalue-Verweis auf ein Mutex-Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das aktuelle Mutex-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der **verschieben Semantik** Abschnitt [Rvalue-Verweisdeklarator: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>Siehe auch
 [Mutex-Klasse](../windows/mutex-class1.md)
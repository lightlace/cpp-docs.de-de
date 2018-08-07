---
title: 'Mutex:: Operator = | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 837c8ed508b713f790d1a6a56310705a00f12b3f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602745"
---
# <a name="mutexoperator-operator"></a>Mutex::operator=-Operator
Zugewiesen (bewegt) der angegebenen **Mutex** -Objekt mit dem aktuellen **Mutex** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
Mutex& operator=(  
   _Inout_ Mutex&& h  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *h*  
 Ein Rvalue-Verweis auf eine **Mutex** Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das aktuelle **Mutex** Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter den **verschieben Semantik** Abschnitt [Rvalue-Verweisdeklarator: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>Siehe auch
 [Mutex-Klasse](../windows/mutex-class1.md)
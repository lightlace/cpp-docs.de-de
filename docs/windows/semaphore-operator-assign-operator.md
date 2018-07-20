---
title: 'Semaphore:: Operator = | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: ea19839f-91f0-4b00-a35b-5728fcba4981
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 25287e642bd368470b207ed237f44ca70773064e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892526"
---
# <a name="semaphoreoperator-operator"></a>Semaphore::operator=-Operator
Verschiebt das angegebene Handle aus einem Semaphorobjekt mit dem aktuellen Semaphore-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
Semaphore& operator=(  
   _Inout_ Semaphore&& h  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `h`  
 Rvalue-Verweis auf eine Semaphorobjekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das aktuelle Semaphore-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>Siehe auch
 [Semaphore-Klasse](../windows/semaphore-class.md)
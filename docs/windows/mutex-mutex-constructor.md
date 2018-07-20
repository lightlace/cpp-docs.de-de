---
title: 'Mutex:: Mutex-Konstruktor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex, constructor
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb7782e44fc8598ca3b806ef922f8d0840765e28
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876455"
---
# <a name="mutexmutex-constructor"></a>Mutex::Mutex-Konstruktor
Initialisiert eine neue Instanz der Mutex-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
explicit Mutex(  
   HANDLE h  
);  
  
Mutex(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `h`  
 Ein Handle oder ein Rvalue-Verweis auf ein Handle, um ein Mutex-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert ein Mutex-Objekt aus dem angegebenen Handle. Der zweite Konstruktor initialisiert ein Mutex-Objekt aus dem angegebenen Handle und klicken Sie dann den Besitz des Mutex mit dem aktuellen Mutex-Objekt verschiebt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>Siehe auch
 [Mutex-Klasse](../windows/mutex-class1.md)
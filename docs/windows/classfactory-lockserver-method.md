---
title: 'ClassFactory:: Lockserver-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- LockServer method
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 654ef60c924a14e861971c651899c8baea0300ef
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462705"
---
# <a name="classfactorylockserver-method"></a>ClassFactory::LockServer-Methode
Erhöht oder verringert die Anzahl der zugrunde liegenden Objekte nachverfolgt werden, von der aktuellen **ClassFactory** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
#### <a name="parameters"></a>Parameter  
 *Bestand*  
 **"true"** erhöht die Anzahl der überwachten Objekte. **"false"** um die Anzahl der überwachten Objekte zu verringern.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls E_FAIL.  
  
## <a name="remarks"></a>Hinweise  
 ClassFactory verfolgt des Objekte in einer zugrunde liegenden Instanz, von der [Modul](../windows/module-class.md) Klasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ClassFactory-Klasse](../windows/classfactory-class.md)
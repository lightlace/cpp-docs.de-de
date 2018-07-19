---
title: 'ClassFactory:: Lockserver-Methode | Microsoft Docs'
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
ms.openlocfilehash: 9e09a795688c7e2b31771126f9e4036ddfbd8e4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860319"
---
# <a name="classfactorylockserver-method"></a>ClassFactory::LockServer-Methode
Erhöht oder verringert die Anzahl der zugrunde liegenden Objekte, die vom aktuellen Objekt ClassFactory nachverfolgt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fLock`  
 `true` die Anzahl der überwachten Objekte zu erhöhen. `false` um die Anzahl der überwachten Objekte zu verringern.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls E_FAIL zurück.  
  
## <a name="remarks"></a>Hinweise  
 ClassFactory der nachverfolgt Objekte in einer zugrunde liegenden Instanz, von der [Modul](../windows/module-class.md) Klasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ClassFactory-Klasse](../windows/classfactory-class.md)
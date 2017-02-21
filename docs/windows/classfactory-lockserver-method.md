---
title: "ClassFactory::LockServer-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ClassFactory::LockServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LockServer-Methode"
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ClassFactory::LockServer-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erhöht oder verringert die Anzahl der zugrunde liegenden Objekte, die vom aktuellen ClassFactory Objekt nachverfolgt werden.  
  
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
 S_OK, wenn erfolgreich; andernfalls E_FAIL.  
  
## <a name="remarks"></a>Hinweise  
 ClassFactory verfolgt des Objekte in einer zugrunde liegenden Instanz, von der [Modul](../windows/module-class.md) Klasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ClassFactory-Klasse](../windows/classfactory-class.md)
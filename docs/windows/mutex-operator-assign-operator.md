---
title: "Mutex::operator=-Operator"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator=-Operator"
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Mutex::operator=-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Weist (bewegt) angegebenen Mutex-Objekt mit dem aktuellen Mutex-Objekt.  
  
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
 Weitere Informationen finden Sie unter den **Verschieben Semantik** Abschnitt [Rvalue-Verweisdeklarator: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>Siehe auch
 [Mutex-Klasse](../windows/mutex-class1.md)
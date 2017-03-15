---
title: "Mutex::Mutex-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Mutex, Konstruktor"
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Mutex::Mutex-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
 Der erste Konstruktor initialisiert ein Mutex-Objekt aus dem angegebenen Handle. Der zweite Konstruktor initialisiert ein Mutex-Objekt aus dem angegebenen Handle und verschiebt anschließend den Besitz des Mutex in das aktuelle Mutex-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>Siehe auch
 [Mutex-Klasse](../windows/mutex-class1.md)
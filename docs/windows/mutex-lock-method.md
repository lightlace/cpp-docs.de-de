---
title: "Mutex::Lock-Methode"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lock-Methode"
ms.assetid: 61d95072-b690-441e-a080-0bf94a733141
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Mutex::Lock-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wartet, bis das aktuelle Objekt oder die Mutex-Objekt, das dem angegebenen Handle zugeordnete Mutex frei, oder das angegebene Timeoutintervall verstrichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `milliseconds`  
 Das Timeoutintervall in Millisekunden. Der Standardwert ist UNENDLICH, der unbegrenzt wartet.  
  
 `h`  
 Das Handle des ein Mutex-Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>Siehe auch
 [Mutex-Klasse](../windows/mutex-class1.md)
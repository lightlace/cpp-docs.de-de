---
title: "Semaphore::Lock-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lock-Methode"
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Semaphore::Lock-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wartet, bis das aktuelle Objekt, oder das Semaphor-Objekt, das das angegebene Handle zugeordnet ist, in den signalisierten Zustand, oder das angegebene Timeoutintervall verstrichen.  
  
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
 Ein Handle für ein Semaphorobjekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Details::SyncLockWithStatusT \< HandleTraits::SemaphoreTraits >  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
[Semaphore-Klasse](../windows/semaphore-class.md)
 
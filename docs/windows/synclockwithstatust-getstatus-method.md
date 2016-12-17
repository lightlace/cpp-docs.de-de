---
title: "SyncLockWithStatusT::GetStatus-Methode"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetStatus-Methode"
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockWithStatusT::GetStatus-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL-Infrastruktur und ist nicht direkt aus dem Code verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Das Ergebnis eines Vorgangs warten auf das Objekt, das die SyncLockWithStatusT-Klasse, wie z. B. basiert eine [Mutex](../windows/mutex-class1.md) oder [Semaphore](../windows/semaphore-class.md). 0 (null) gibt an, dass der Wartevorgang auf den signalisierten Zustand zurückgegeben. Andernfalls ist einen anderen Zustand aufgetreten, z. B. Timeoutwert abgelaufen.  
  
## <a name="remarks"></a>Hinweise  
 Ruft den Wait-Status des aktuellen SyncLockWithStatusT-Objekts ab.  
  
 Die GetStatus()-Funktion ruft den Wert des zugrunde liegenden [Status_](../windows/synclockwithstatust-status-data-member.md) -Datenmember. Wenn ein Objekt basierend auf der SyncLockWithStatusT-Klasse einen Lock-Vorgang ausführt, wartet das Objekt zuerst für das Objekt verfügbar sind. Das Ergebnis dieses Wartevorgangs befindet sich in der `status_` -Datenmember. Die möglichen Werte für die `status_` Datenmember sind die Rückgabewerte des Wartevorgangs. Weitere Informationen finden Sie unter die Rückgabewerte der **WaitForSingleObjectEx()** -Funktion in der MSDN Library.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [SyncLockWithStatusT-Klasse](../windows/synclockwithstatust-class.md)
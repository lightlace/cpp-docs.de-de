---
title: "IThreadPoolConfig Interface"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "IThreadPoolConfig"
  - "ATL::IThreadPoolConfig"
  - "ATL.IThreadPoolConfig"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IThreadPoolConfig interface"
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
caps.latest.revision: 24
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# IThreadPoolConfig Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Schnittstelle stellt Methoden zum Konfigurieren eines Threadpools bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      __interface  
__declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660"))  
IThreadPoolConfig :  
public IUnknown  
```  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[GetSize](../Topic/IThreadPoolConfig::GetSize.md)|Rufen Sie diese Methode auf, um die Anzahl der Threads im Pool abzurufen.|  
|[GetTimeout](../Topic/IThreadPoolConfig::GetTimeout.md)|Rufen Sie diese Methode auf, um die maximale Zeit in Millisekunden abzurufen, dass der Threadpool auf einen Thread wartet, um herunterzufahren.|  
|[SetSize](../Topic/IThreadPoolConfig::SetSize.md)|Rufen Sie diese Methode auf, um die Anzahl der Threads im Pool festzulegen.|  
|[SetTimeout](../Topic/IThreadPoolConfig::SetTimeout.md)|Rufen Sie diese Methode auf, um die maximale Zeit in Millisekunden festzulegen, dass der Threadpool auf einen Thread wartet, um herunterzufahren.|  
  
## Hinweise  
 Diese Schnittstelle wird von [CThreadPool](../../atl/reference/cthreadpool-class.md) implementiert.  
  
## Anforderungen  
 **Header:** atlutil.h  
  
## Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)   
 [CThreadPool Class](../../atl/reference/cthreadpool-class.md)
---
title: "IWorkerThreadClient Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IWorkerThreadClient"
  - "ATL::IWorkerThreadClient"
  - "IWorkerThreadClient"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IWorkerThreadClient interface"
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# IWorkerThreadClient Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`IWorkerThreadClient` ist die Schnittstelle, die von Clients der [CWorkerThread](../../atl/reference/cworkerthread-class.md)\-Klasse implementiert wird.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
__interface IWorkerThreadClient  
  
```  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[CloseHandle](../Topic/IWorkerThreadClient::CloseHandle.md)|Implementieren Sie diese Methode, um das Handle zu schließen, das diesem Objekt zugeordnet ist.|  
|[Ausführen](../Topic/IWorkerThreadClient::Execute.md)|Implementieren Sie diese Methode, um Code auszuführen, wenn das Handle, das diesem Objekt zugeordnet ist, signalisiert wird.|  
  
## Hinweise  
 Implementieren Sie diese Schnittstelle, wenn Sie Code haben, der auf einem Arbeitsthread als Reaktion auf ein Handle ausführen muss, das signalisiert wird.  
  
## Anforderungen  
 **Header:** atlutil.h  
  
## Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)   
 [CWorkerThread Class](../../atl/reference/cworkerthread-class.md)
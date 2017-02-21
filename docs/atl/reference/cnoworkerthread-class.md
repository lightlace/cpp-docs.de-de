---
title: "CNoWorkerThread Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CNoWorkerThread"
  - "ATL.CNoWorkerThread"
  - "CNoWorkerThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoWorkerThread class"
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CNoWorkerThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diese Klasse als Argument, damit der `MonitorClass` Vorlagenparameter Klassen zwischengespeichert werden, wenn Sie dynamische Cacheverwaltung deaktivieren möchten.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CNoWorkerThread  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CNoWorkerThread::AddHandle](../Topic/CNoWorkerThread::AddHandle.md)|Nicht funktionale Entsprechung von [CWorkerThread::AddHandle](../Topic/CWorkerThread::AddHandle.md).|  
|[CNoWorkerThread::AddTimer](../Topic/CNoWorkerThread::AddTimer.md)|Nicht funktionale Entsprechung von [CWorkerThread::AddTimer](../Topic/CWorkerThread::AddTimer.md).|  
|[CNoWorkerThread::GetThreadHandle](../Topic/CNoWorkerThread::GetThreadHandle.md)|Nicht funktionale Entsprechung von [CWorkerThread::GetThreadHandle](../Topic/CWorkerThread::GetThreadHandle.md).|  
|[CNoWorkerThread::GetThreadId](../Topic/CNoWorkerThread::GetThreadId.md)|Nicht funktionale Entsprechung von [CWorkerThread::GetThreadId](../Topic/CWorkerThread::GetThreadId.md).|  
|[CNoWorkerThread::Initialize](../Topic/CNoWorkerThread::Initialize.md)|Nicht funktionale Entsprechung von [CWorkerThread::Initialize](../Topic/CWorkerThread::Initialize.md).|  
|[CNoWorkerThread::RemoveHandle](../Topic/CNoWorkerThread::RemoveHandle.md)|Nicht funktionale Entsprechung von [CWorkerThread::RemoveHandle](../Topic/CWorkerThread::RemoveHandle.md).|  
|[CNoWorkerThread::Shutdown](../Topic/CNoWorkerThread::Shutdown.md)|Nicht funktionale Entsprechung von [CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md).|  
  
## Hinweise  
 Diese Klasse stellt die gleiche öffentliche Schnittstelle wie [CWorkerThread](../../atl/reference/cworkerthread-class.md) bereit.  Diese Schnittstelle wird erwartet, vom `MonitorClass` Vorlagenparameter zu den Cacheklassen bereitgestellt werden.  
  
 Die Methoden in dieser Klasse werden implementiert, um nichts unternehmen.  Die Methoden, die eine Rückgabe S\_OK HRESULT immer zurückgeben und die Methoden, die eine Rückgabe 0 der HANDLE\- oder Thread\-ID immer zurückgeben.  
  
## Anforderungen  
 **Header:** atlutil.h
---
title: IUMSThreadProxy-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
dev_langs: C++
helpviewer_keywords: IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d9d9b200db84ddbf25e514e1432fa0915d5ee383
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy-Struktur
Eine Abstraktion für einen Thread der Ausführung. Wenn dem Planer im Benutzermodus planbare (UMS) Threads gewährt werden sollen, legen Sie den Wert für das Planerrichtlinienelement `SchedulerKind` auf `UmsThreadDefault` fest, und implementieren Sie die `IUMSScheduler`-Schnittstelle. UMS-Threads werden nur unter 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IUMSThreadProxy : public IThreadProxy;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IUMSThreadProxy:: EnterCriticalRegion](#entercriticalregion)|Wird aufgerufen, um eine kritische überzugehen. In einem kritischen Bereich berücksichtigt das Zeitplanungsmodul nicht asynchronen blockierenden Vorgänge, die während der Region durchgeführt. Dies bedeutet, dass der Planer für Seitenfehler, Thread Eingangsseite, Kernel asynchrone Prozeduraufrufe (APCs) usw., für ein UMS-Thread nicht erneut eingegeben werden wird.|  
|[IUMSThreadProxy:: EnterHyperCriticalRegion](#enterhypercriticalregion)|Wird aufgerufen, um eine extrem kritischen überzugehen. In einem hyper-wichtigen Bereich berücksichtigt das Zeitplanungsmodul keine blockierenden Vorgänge, die während der Region durchgeführt. Dies bedeutet, dass das Zeitplanungsmodul nicht erneut geöffnet wird für Funktionsaufrufe, Sperre Übernahme Versuche, welcher Block, Seitenfehler, thread Eingangsseite Kernel asynchrone Prozeduraufrufe (APCs), und usw., für ein UMS-Thread, blockiert.|  
|[IUMSThreadProxy:: ExitCriticalRegion](#exitcriticalregion)|Wird aufgerufen, um einen kritischen Bereich zu verlassen.|  
|[IUMSThreadProxy:: ExitHyperCriticalRegion](#exithypercriticalregion)|Wird aufgerufen, um eine extrem kritischen Bereich zu verlassen.|  
|[IUMSThreadProxy:: GetCriticalRegionType](#getcriticalregiontype)|Gibt zurück, welche Art von kritischen Bereichs, in der Threadproxy befindet. Da hyper wichtige Bereiche eine Obermenge der kritischen Bereiche sind, wenn der Code eingegeben hat, einen wichtigen Bereich, und klicken Sie dann eine extrem kritischen Bereich `InsideHyperCriticalRegion` zurückgegeben werden.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [IThreadProxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="entercriticalregion"></a>IUMSThreadProxy:: EnterCriticalRegion-Methode  
 Wird aufgerufen, um eine kritische überzugehen. In einem kritischen Bereich berücksichtigt das Zeitplanungsmodul nicht asynchronen blockierenden Vorgänge, die während der Region durchgeführt. Dies bedeutet, dass der Planer für Seitenfehler, Thread Eingangsseite, Kernel asynchrone Prozeduraufrufe (APCs) usw., für ein UMS-Thread nicht erneut eingegeben werden wird.  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe eines kritischen Bereichs. Kritische Bereiche sind wiedereintretend.  
  
##  <a name="enterhypercriticalregion"></a>IUMSThreadProxy:: EnterHyperCriticalRegion-Methode  
 Wird aufgerufen, um eine extrem kritischen überzugehen. In einem hyper-wichtigen Bereich berücksichtigt das Zeitplanungsmodul keine blockierenden Vorgänge, die während der Region durchgeführt. Dies bedeutet, dass das Zeitplanungsmodul nicht erneut geöffnet wird für Funktionsaufrufe, Sperre Übernahme Versuche, welcher Block, Seitenfehler, thread Eingangsseite Kernel asynchrone Prozeduraufrufe (APCs), und usw., für ein UMS-Thread, blockiert.  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe eines hyper-kritischen Bereichs. Hyper-kritische Bereiche sind wiedereintretend.  
  
### <a name="remarks"></a>Hinweise  
 Der Planer muss besonders vorsichtig, was in Bereichen aufgerufenen Methoden und Sperren erhält. Wenn Code in solchen Bereichs auf eine Sperre blockiert wird, die etwas anderes, dass der Planer gehalten wird für die Planung zuständig ist, kann der Deadlock folgen.  
  
##  <a name="exitcriticalregion"></a>IUMSThreadProxy:: ExitCriticalRegion-Methode  
 Wird aufgerufen, um einen kritischen Bereich zu verlassen.  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe eines kritischen Bereichs. Kritische Bereiche sind wiedereintretend.  
  
##  <a name="exithypercriticalregion"></a>IUMSThreadProxy:: ExitHyperCriticalRegion-Methode  
 Wird aufgerufen, um eine extrem kritischen Bereich zu verlassen.  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe eines hyper-kritischen Bereichs. Hyper-kritische Bereiche sind wiedereintretend.  
  
##  <a name="getcriticalregiontype"></a>IUMSThreadProxy:: GetCriticalRegionType-Methode  
 Gibt zurück, welche Art von kritischen Bereichs, in der Threadproxy befindet. Da hyper wichtige Bereiche eine Obermenge der kritischen Bereiche sind, wenn der Code eingegeben hat, einen wichtigen Bereich, und klicken Sie dann eine extrem kritischen Bereich `InsideHyperCriticalRegion` zurückgegeben werden.  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Typ eines kritischen Bereichs, der Threadproxy befindet.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IUMSScheduler-Struktur](iumsscheduler-structure.md)

---
title: IUMSThreadProxy-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 46d486ddccce6f3c54627f3ea96f001e8e3bfcf7
ms.lasthandoff: 03/17/2017

---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy-Struktur
Eine Abstraktion für einen Thread der Ausführung. Wenn dem Planer im Benutzermodus planbare (UMS) Threads gewährt werden sollen, legen Sie den Wert für das Planerrichtlinienelement `SchedulerKind` auf `UmsThreadDefault` fest, und implementieren Sie die `IUMSScheduler`-Schnittstelle. UMS-Threads werden nur unter 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IUMSThreadProxy : public IThreadProxy;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IUMSThreadProxy:: EnterCriticalRegion](#entercriticalregion)|Wird aufgerufen, um einen kritischen Bereich einzutreten. In einem kritischen Bereich, wird der Planer keine asynchrone blockierende Operationen berücksichtigt, die während des Bereichs auftreten. Dies bedeutet, dass der Planer für Seitenfehler, Threadunterbrechungen, asynchrone Kernelprozeduraufrufe (APCs) usw., für ein UMS-Thread nicht erneut eingegeben werden kann.|  
|[IUMSThreadProxy:: EnterHyperCriticalRegion](#enterhypercriticalregion)|Wird aufgerufen, um einen äußerst wichtigen Bereich eingeben. In einem äußerst wichtigen Bereich, wird der Planer keine blockierenden Operationen berücksichtigt, die während des Bereichs auftreten. Dies bedeutet, dass der Planer nicht erneut geöffnet wird für Funktionsaufrufe, Sperre Übernahme Versuche, welcher Block, Seitenfehler, thread-Unterbrechungen, Kernel asynchrone Prozeduraufrufe (APCs), und usw., für die ein UMS-Thread, blockiert.|  
|[IUMSThreadProxy:: ExitCriticalRegion](#exitcriticalregion)|Wird aufgerufen, um einen kritischen Bereich zu verlassen.|  
|[IUMSThreadProxy:: ExitHyperCriticalRegion](#exithypercriticalregion)|Wird aufgerufen, um einen extrem kritischen Bereich zu verlassen.|  
|[IUMSThreadProxy:: GetCriticalRegionType](#getcriticalregiontype)|Gibt die Art des kritischen Bereichs, in der Threadproxy befindet. Da besonders wichtige Bereiche eine Obermenge wichtiger Bereiche sind, wenn der Code eingegeben hat einen kritischen Bereich und dann einem äußerst wichtigen Bereich `InsideHyperCriticalRegion` zurückgegeben werden.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [IThreadProxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="entercriticalregion"></a>IUMSThreadProxy:: EnterCriticalRegion-Methode  
 Wird aufgerufen, um einen kritischen Bereich einzutreten. In einem kritischen Bereich, wird der Planer keine asynchrone blockierende Operationen berücksichtigt, die während des Bereichs auftreten. Dies bedeutet, dass der Planer für Seitenfehler, Threadunterbrechungen, asynchrone Kernelprozeduraufrufe (APCs) usw., für ein UMS-Thread nicht erneut eingegeben werden kann.  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe eines kritischen Bereichs. Kritische Bereiche sind wiedereintretend.  
  
##  <a name="enterhypercriticalregion"></a>IUMSThreadProxy:: EnterHyperCriticalRegion-Methode  
 Wird aufgerufen, um einen äußerst wichtigen Bereich eingeben. In einem äußerst wichtigen Bereich, wird der Planer keine blockierenden Operationen berücksichtigt, die während des Bereichs auftreten. Dies bedeutet, dass der Planer nicht erneut geöffnet wird für Funktionsaufrufe, Sperre Übernahme Versuche, welcher Block, Seitenfehler, thread-Unterbrechungen, Kernel asynchrone Prozeduraufrufe (APCs), und usw., für die ein UMS-Thread, blockiert.  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe des äußerst wichtigen Bereichs. Extrem kritische Bereiche sind wiedereintretend.  
  
### <a name="remarks"></a>Hinweise  
 Der Planer muss besonders vorsichtig, welche Methoden und Sperren in solchen Bereichen abgerufenen sein. Wenn Code in so einem Bereich eine Sperre, die von einem Element gehalten wird, dass der Planer zum Planen von verantwortlich ist blockiert, möglicherweise Deadlock folgen.  
  
##  <a name="exitcriticalregion"></a>IUMSThreadProxy:: ExitCriticalRegion-Methode  
 Wird aufgerufen, um einen kritischen Bereich zu verlassen.  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe eines kritischen Bereichs. Kritische Bereiche sind wiedereintretend.  
  
##  <a name="exithypercriticalregion"></a>IUMSThreadProxy:: ExitHyperCriticalRegion-Methode  
 Wird aufgerufen, um einen extrem kritischen Bereich zu verlassen.  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe des äußerst wichtigen Bereichs. Extrem kritische Bereiche sind wiedereintretend.  
  
##  <a name="getcriticalregiontype"></a>IUMSThreadProxy:: GetCriticalRegionType-Methode  
 Gibt die Art des kritischen Bereichs, in der Threadproxy befindet. Da besonders wichtige Bereiche eine Obermenge wichtiger Bereiche sind, wenn der Code eingegeben hat einen kritischen Bereich und dann einem äußerst wichtigen Bereich `InsideHyperCriticalRegion` zurückgegeben werden.  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Typ eines kritischen Bereichs, der Threadproxy befindet.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IUMSScheduler-Struktur](iumsscheduler-structure.md)


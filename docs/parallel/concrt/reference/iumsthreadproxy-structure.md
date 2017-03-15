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
- concrtrm/concurrency::IUMSThreadProxy
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 55ed05f137775e819c81ce231cf8c8ad3a9974f3
ms.lasthandoff: 02/24/2017

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
|[IUMSThreadProxy:: EnterCriticalRegion-Methode](#entercriticalregion)|Wird aufgerufen, um einen kritischen Bereich einzutreten. In einem kritischen Bereich, wird der Planer keine asynchrone blockierende Operationen berücksichtigt, die während des Bereichs auftreten. Dies bedeutet, dass der Planer für Seitenfehler, Threadunterbrechungen, asynchrone Kernelprozeduraufrufe (APCs) usw., für ein UMS-Thread nicht erneut eingegeben werden kann.|  
|[IUMSThreadProxy:: EnterHyperCriticalRegion-Methode](#enterhypercriticalregion)|Wird aufgerufen, um einen äußerst wichtigen Bereich eingeben. In einem äußerst wichtigen Bereich, wird der Planer keine blockierenden Operationen berücksichtigt, die während des Bereichs auftreten. Dies bedeutet, dass der Planer nicht erneut geöffnet wird für Funktionsaufrufe, Sperre Übernahme Versuche, welcher Block, Seitenfehler, thread-Unterbrechungen, Kernel asynchrone Prozeduraufrufe (APCs), und usw., für die ein UMS-Thread, blockiert.|  
|[IUMSThreadProxy:: ExitCriticalRegion-Methode](#exitcriticalregion)|Wird aufgerufen, um einen kritischen Bereich zu verlassen.|  
|[IUMSThreadProxy:: ExitHyperCriticalRegion-Methode](#exithypercriticalregion)|Wird aufgerufen, um einen extrem kritischen Bereich zu verlassen.|  
|[IUMSThreadProxy:: GetCriticalRegionType-Methode](#getcriticalregiontype)|Gibt die Art des kritischen Bereichs, in der Threadproxy befindet. Da besonders wichtige Bereiche eine Obermenge wichtiger Bereiche sind, wenn der Code eingegeben hat einen kritischen Bereich und dann einem äußerst wichtigen Bereich `InsideHyperCriticalRegion` zurückgegeben werden.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [IThreadProxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameentercriticalregiona--iumsthreadproxyentercriticalregion-method"></a><a name="entercriticalregion"></a>IUMSThreadProxy:: EnterCriticalRegion-Methode  
 Wird aufgerufen, um einen kritischen Bereich einzutreten. In einem kritischen Bereich, wird der Planer keine asynchrone blockierende Operationen berücksichtigt, die während des Bereichs auftreten. Dies bedeutet, dass der Planer für Seitenfehler, Threadunterbrechungen, asynchrone Kernelprozeduraufrufe (APCs) usw., für ein UMS-Thread nicht erneut eingegeben werden kann.  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe eines kritischen Bereichs. Kritische Bereiche sind wiedereintretend.  
  
##  <a name="a-nameenterhypercriticalregiona--iumsthreadproxyenterhypercriticalregion-method"></a><a name="enterhypercriticalregion"></a>IUMSThreadProxy:: EnterHyperCriticalRegion-Methode  
 Wird aufgerufen, um einen äußerst wichtigen Bereich eingeben. In einem äußerst wichtigen Bereich, wird der Planer keine blockierenden Operationen berücksichtigt, die während des Bereichs auftreten. Dies bedeutet, dass der Planer nicht erneut geöffnet wird für Funktionsaufrufe, Sperre Übernahme Versuche, welcher Block, Seitenfehler, thread-Unterbrechungen, Kernel asynchrone Prozeduraufrufe (APCs), und usw., für die ein UMS-Thread, blockiert.  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe des äußerst wichtigen Bereichs. Extrem kritische Bereiche sind wiedereintretend.  
  
### <a name="remarks"></a>Hinweise  
 Der Planer muss besonders vorsichtig, welche Methoden und Sperren in solchen Bereichen abgerufenen sein. Wenn Code in so einem Bereich eine Sperre, die von einem Element gehalten wird, dass der Planer zum Planen von verantwortlich ist blockiert, möglicherweise Deadlock folgen.  
  
##  <a name="a-nameexitcriticalregiona--iumsthreadproxyexitcriticalregion-method"></a><a name="exitcriticalregion"></a>IUMSThreadProxy:: ExitCriticalRegion-Methode  
 Wird aufgerufen, um einen kritischen Bereich zu verlassen.  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe eines kritischen Bereichs. Kritische Bereiche sind wiedereintretend.  
  
##  <a name="a-nameexithypercriticalregiona--iumsthreadproxyexithypercriticalregion-method"></a><a name="exithypercriticalregion"></a>IUMSThreadProxy:: ExitHyperCriticalRegion-Methode  
 Wird aufgerufen, um einen extrem kritischen Bereich zu verlassen.  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Tiefe des äußerst wichtigen Bereichs. Extrem kritische Bereiche sind wiedereintretend.  
  
##  <a name="a-namegetcriticalregiontypea--iumsthreadproxygetcriticalregiontype-method"></a><a name="getcriticalregiontype"></a>IUMSThreadProxy:: GetCriticalRegionType-Methode  
 Gibt die Art des kritischen Bereichs, in der Threadproxy befindet. Da besonders wichtige Bereiche eine Obermenge wichtiger Bereiche sind, wenn der Code eingegeben hat einen kritischen Bereich und dann einem äußerst wichtigen Bereich `InsideHyperCriticalRegion` zurückgegeben werden.  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Typ eines kritischen Bereichs, der Threadproxy befindet.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IUMSScheduler-Struktur](iumsscheduler-structure.md)


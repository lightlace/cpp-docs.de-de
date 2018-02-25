---
title: Threadprivate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- threadprivate
dev_langs:
- C++
helpviewer_keywords:
- threadprivate OpenMP directive
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 55a50d2387662fe42c04d61a8e98153aad95c835
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="threadprivate"></a>threadprivate
Gibt an, dass eine Variable einem Thread zugehörig ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma omp threadprivate(var)  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `var`  
 Eine durch Trennzeichen getrennte Liste von Variablen, die an einen Thread privat machen möchten. `var` entweder eine globale - oder Namespace-bewertete Variable oder eine statische lokale Variable muss sein.  
  
## <a name="remarks"></a>Hinweise  
 Die `threadprivate` Richtlinie unterstützt kein OpenMP-Klauseln.  
  
 Weitere Informationen finden Sie unter [2.7.1 Threadprivate-Direktive](../../../parallel/openmp/2-7-1-threadprivate-directive.md).  
  
 Die `threadprivate` Richtlinie basiert auf der [Thread](../../../cpp/thread.md) `__declspec` -Attribut; die Beschränkungen **__declspec(thread)** gelten für `threadprivate`.  
  
 Sie können keine `threadprivate` in DLLs, die geladen wird, über [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175).  Dies schließt die DLLs, die geladen werden, mit [/DELAYLOAD (Laden von Import verzögern)](../../../build/reference/delayload-delay-load-import.md), die auch verwendet **LoadLibrary**.  
  
 Sie können `threadprivate` in eine DLL, die beim Prozessstart statisch geladen wird.  
  
 Da `threadprivate` basiert auf **__declspec(thread)**ein `threadprivate` Variable wird in einen beliebigen Thread, die Schritte im Prozess, nicht nur auf diese Threads, die Teil eines Thread-Teams, die vom eines parallelen Bereichs erzeugte sind vorhanden.  Dies ist ein Implementierungsdetail, die Sie kennen sollten, sein, da Sie, z. B. Konstruktoren für möglicherweise bemerken sollten eine `threadprivate` einen benutzerdefinierten Typ aufgerufen häufig wird erwartet.  
  
 Ein `threadprivate` Variablen eines destructable nicht notwendigerweise sein Destruktor aufgerufen haben.  Zum Beispiel:  
  
```  
struct MyType   
{  
    ~MyType();  
};  
  
MyType threaded_var;  
#pragma omp threadprivate(threaded_var)  
int main()   
{  
    #pragma omp parallel  
    {}  
}  
```  
  
 Benutzer haben keinen Einfluss auf, wenn die Threads enthalten sind, die den parallelen Bereich beendet wird.  Wenn diese Threads vorhanden sind, wenn der Prozess beendet wird, die Threads über das Beenden des Prozesses nicht benachrichtigt und der Destruktor nicht aufgerufen werden, für die wird `threaded_var` auf einen beliebigen Thread mit Ausnahme des beendet wird (Hier wird der primäre Thread).  Damit der Code nicht auf ordnungsgemäße Zerstörung von zählen sollten `threadprivate` Variablen.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel der Verwendung von `threadprivate`, finden Sie unter [private](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../../../parallel/openmp/reference/openmp-directives.md)
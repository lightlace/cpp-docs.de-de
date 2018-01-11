---
title: Threadsicherheit in der C++-Standardbibliothek | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- thread safety
- C++ Standard Library, thread safety
- thread safety, C++ Standard Library
ms.assetid: 9351c8fb-4539-4728-b0e9-226e2ac4284b
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fa4c69e79a918d7b8cf77e03f76c81e846d5a5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="thread-safety-in-the-c-standard-library"></a>Threadsicherheit in der C++-Standardbibliothek
Die folgenden Threadsicherheitsregeln gelten für alle Klassen in der C++-Standardbibliothek – dazu gehört wie unten beschrieben auch `shared_ptr`.  In manchen Fällen stehen noch stärkere Garantien zur Verfügung – z.B. die unten beschriebenen iostream-Standardobjekte und Typen, die speziell für das Multithreading entwickelt wurden wie diejenigen in [\<atomic>](../standard-library/atomic.md).  
  
 Ein Objekt ist zum Lesen aus mehreren Threads threadsicher. Ein bestimmtes Objekt A kann z. B. sicher gleichzeitig aus Thread 1 und Thread 2 ausgelesen werden.  
  
 Wenn durch einen Thread in ein Objekt geschrieben wird, müssen alle Lese- und Schreibvorgänge im Zusammenhang mit diesem Objekt in diesem oder anderen Threads geschützt werden. Wenn z. B. Thread 1 in Objekt A schreibt, muss verhindert werden, dass Thread 2 Objekt A ausliest oder in Objekt A schreibt.  
  
 Es ist sicher, aus einer Instanz eines Typs zu lesen oder in diese zu schreiben, wenn ein anderer Thread aus einer anderen Instanz desselben Typs liest oder in diese schreibt. Im Fall zweier Objekte desselben Typs namens Objekt A und Objekt B ist es sicher, wenn Thread 1 in Objekt A schreibt und in Thread 2 aus Objekt B gelesen wird.  
  
## <a name="sharedptr"></a>shared_ptr  
 Mehrere Threads können gleichzeitig verschiedene [shared_ptr](../standard-library/shared-ptr-class.md)-Objekte auslesen und in diese schreiben, auch wenn die Objekte Kopien sind, die denselben Besitzer haben.  
  
## <a name="iostream"></a>iostream  
 Die iostream-Standardobjekte `cin`, `cout`, `cerr`, `clog`, `wcin`, `wcout`, `wcerr` und `wclog` folgen denselben Regeln wie die anderen Klassen, mit der Ausnahme, dass es sicher ist, wenn in mehreren Threads in ein Objekt geschrieben wird. Zum Beispiel kann Thread 1 zur selben Zeit in [cout](../standard-library/iostream.md#cout) schreiben wie Thread 2. Dies kann allerdings zu einer Vermischung der Ausgaben zweier Threads führen.  
  
> [!NOTE]
>  Das Lesen aus einem Streampuffer wird nicht als Lesevorgang betrachtet. Stattdessen wird es als Schreibvorgang angesehen, da der Zustand der Klasse geändert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)




---
title: "QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Schnittstellen, Verfügbarkeit"
  - "Schnittstellen, Zeiger"
  - "QueryInterface-Methode"
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obwohl es Mechanismen, durch die ein Objekt die Funktionalität ausgedrückt werden, sie bereitstellt statisch gibt \(bevor instanziiert wird\), ist der einfache COM\-Mechanismus, die **IUnknown** \-Methode zu verwenden, die [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) aufgerufen wird.  
  
 Jede Schnittstelle wird von **IUnknown** abgeleitet, enthält jede Schnittstelle eine Implementierung von `QueryInterface`.  Unabhängig von der Implementierung fragt diese Methode ein Objekt mit dem IID der Schnittstelle ab, mit der der Aufrufer einen Zeiger wünscht.  Wenn das Objekt, die die herstellen, `QueryInterface` einen Zeiger auf die Schnittstelle abgerufen werden, während `AddRef` auch aufrufen.  Andernfalls gibt es den **E\_NOINTERFACE** Fehlercode zurück.  
  
 Beachten Sie, dass Sie [Verweiszählung](../atl/reference-counting.md) Regeln jederzeit befolgen müssen.  Wenn Sie **Release** auf einem Schnittstellenzeiger aufrufen, um den Verweiszähler auf null zu verringern, sollten Sie diesen Zeiger nicht erneut verwenden.  Gelegentlich müssen Sie sich ein schwacher Verweis auf ein Objekt \(das heißt, möchten Sie ein Zeiger auf eine der Schnittstellen abrufen, ohne den Verweiszähler erhöht wird\), aber es ist nicht zulässig, hierzu, indem Sie `QueryInterface` gefolgt von **Release** aufrufen.  Der Zeiger abgerufenen auf diese Weise ist ungültig und sollte nicht verwendet werden.  Dies wird schneller deutlich, wenn [\_ATL\_DEBUG\_INTERFACES](../Topic/_ATL_DEBUG_INTERFACES.md) definiert wird, sodass, dieses Makro ist zu definieren eine einfache Methode zum Suchen nach \- Verweiszählungsfehlern.  
  
## Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [QueryInterface: Navigating in an Object](http://msdn.microsoft.com/library/windows/desktop/ms687230)
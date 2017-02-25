---
title: "Reference Counting | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef method [C++]"
  - "AddRef method [C++], reference counting"
  - "reference counting"
  - "reference counts"
  - "Referenzen, Zählen"
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Reference Counting
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM selbst nicht automatisch versucht, ein Objekt aus dem Arbeitsspeicher zu entfernen, wenn es erstellen möchten, dass das Objekt nicht mehr verwendet wird.  Stattdessen muss der Objektprogrammierer das nicht verwendete Objekt entfernen.  Der Programmierer bestimmt, ob ein Objekt auf Grundlage eines Verweiszähler entfernt werden kann.  
  
 COM verwendet die **IUnknown**\-Methoden, [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Version](http://msdn.microsoft.com/library/windows/desktop/ms682317), um den Verweiszähler von Schnittstellen in einem Objekt zu verwalten.  Die allgemeinen Regeln zum Aufrufen dieser Methoden sind:  
  
-   Wenn ein Client einen Schnittstellenzeiger empfängt, muss `AddRef` aufgerufen werden mit der Schnittstelle.  
  
-   Sobald der Client mithilfe des Schnittstellenzeigers beendet, muss er **Release** aufrufen.  
  
 In einer einfachen Implementierung dekrementiert Inkremente jedes `AddRef` Aufrufs und jeder **Release** Aufruf eine Zählervariable innerhalb des Objekts.  Wenn die Anzahlrückgaben auf null, die Schnittstelle nicht mehr alle Benutzer hat und entscheiden, sich vom Arbeitsspeicher zu entfernen.  
  
 Verweiszählung kann auch implementiert werden, damit jeder Verweis auf das Objekt \(nicht zu einer einzelnen Schnittstelle\) gezählt werden.  In diesem Fall gibt jedes `AddRef` und **Release** Aufrufsdelegaten auf eine zentrale Implementierung für das Objekt und **Release** das gesamte Objekt wenn seine Verweiszählerreichweiten null frei.  
  
> [!NOTE]
>  Wenn `CComObject` von abgeleitetes Objekt wird mithilfe des **new**\-Operator, der Verweiszähler ist 0.  Daher muss ein Aufruf `AddRef` gemacht werden, nachdem erfolgreich `CComObject` von abgeleitetes Objekt erstellt hat.  
  
## Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [Managing Object Lifetimes through Reference Counting](http://msdn.microsoft.com/library/windows/desktop/ms687260)
---
title: "Verweiszählung (ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9bef78ba6047305ccb20e5740ae03535ca2c366b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="reference-counting"></a>Verweiszählung
COM selbst versucht automatisch nicht, ein Objekt aus dem Arbeitsspeicher entfernen, wenn er davon ausgeht, dass das Objekt nicht mehr verwendet wird. Stattdessen muss der Programmierer nicht verwendete Objekt entfernen. Der Programmierer bestimmt, ob ein Objekt basierend auf einer Verweisanzahl entfernt werden kann.  
  
 COM verwendet die **IUnknown** Methoden [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Version](http://msdn.microsoft.com/library/windows/desktop/ms682317), um den Verweiszähler der Schnittstellen für ein Objekt zu verwalten. Die allgemeinen Regeln für das Aufrufen dieser Methoden sind:  
  
-   Wenn ein Client einen Schnittstellenzeiger empfängt `AddRef` muss auf der Schnittstelle aufgerufen werden.  
  
-   Wenn der Client mit den Schnittstellenzeiger abgeschlossen ist, muss er ihn aufzurufen **Version**.  
  
 In eine einfache Implementierung jedes `AddRef` aufrufen Inkremente und jede **Version** aufrufen dekrementiert eine Zählervariable innerhalb des Objekts. Wenn die Anzahl 0 (null) zurückgibt, wird die Schnittstelle nicht mehr hat jeder Benutzer und kann nach Belieben selbst aus dem Arbeitsspeicher entfernt wird.  
  
 Verweiszählung kann ebenfalls implementiert werden, damit, dass jeder Verweis auf das Objekt (nicht auf eine einzelne Schnittstelle) gezählt wird. In diesem Fall jedes `AddRef` und **Release** Delegaten an eine zentrale Implementierung für das Objekt aufrufen und **Version** des gesamten Objekts freigegeben, wenn der entsprechende Verweiszähler 0 (null) erreicht.  
  
> [!NOTE]
>  Wenn eine `CComObject`-abgeleitete Objekt wird erstellt, mit der **neue** -Operator, der den Verweiszähler dieser Planergruppe ist 0. Deshalb wird ein Aufruf zum `AddRef` muss erfolgen, nachdem Sie erfolgreich erstellt die `CComObject`-abgeleitetes Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [Verwaltung der Objektlebensdauer durch Verweiszählung](http://msdn.microsoft.com/library/windows/desktop/ms687260)


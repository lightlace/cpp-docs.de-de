---
title: Welche Vorteile hat Remoteautomatisierung? | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Remote Automation, DCOM
ms.assetid: 269ad218-e164-40ef-9b87-25fcc8ba21de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4a82b26a1e6c208a584dfd19ebfd4530b4bdf76
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="what-does-remote-automation-provide"></a>Welche Vorteile hat Remoteautomatisierung?
Remoteautomatisierung kann Programme aufzurufenden `IDispatch` auf einem Computer aus einer anderen Implementierungen. Sie unterstützt auch andere Schnittstellen von Automation, insbesondere **IEnumVARIANT** für die Unterstützung der Datensammlung. Er bietet die Möglichkeit, einer beliebigen anderen COM-Schnittstelle zu verteilen (mit Ausnahme von **IUnknown**, natürlich) und wie reguläre Automation enthält Marshalling Unterstützung nur für diese Datentypen, die von der Automatisierung unterstützt.  
  
 Dieser Satz von ganzen Einrichtungen kann ein Programm zum Zugriff auf die Methoden und Eigenschaften, einschließlich derer, die Auflistungen oder weiteren Automatisierungsobjekte eines Objekts, die auf einem zugänglichen Netzwerkknoten zurückgeben. Wenn der Clientcomputer auch die entsprechende Software ausgeführt wird, ist es möglich, dass der Server einen Rückruf an den Client erneut mit Automatisierungsfunktionen (dies funktioniert bei 32-Bit und 64-Bit-Clients und gleicht konzeptionell Ereignisse wird jedoch nicht verwendet Derselbe Mechanismus).  
  
 Für eine Anwendung als Remoteautomatisierung Server funktionsfähig sein, muss es als ausführbare Datei implementiert werden (d. h. als "Lokaler Server" und nicht als "Inproc-Server").  
  
## <a name="see-also"></a>Siehe auch  
 [Wann ist Remoteautomatisierung angebracht](where-does-remote-automation-fit-in-q.md)   
 [DCOM-Geschichte](../mfc/history-of-dcom.md)

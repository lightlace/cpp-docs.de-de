---
title: "Welche Vorteile hat Remoteautomatisierung?"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Remoteautomatisierung, DCOM"
ms.assetid: 269ad218-e164-40ef-9b87-25fcc8ba21de
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Welche Vorteile hat Remoteautomatisierung?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Remote\- Automatisierung können Programme, um `IDispatch` Implementierungen auf einem anderen Computer aus aufzurufen.  Es unterstützt auch andere Schnittstellen, die durch Automatisierung, speziell **IEnumVARIANT** für Auflistungsunterstützung benötigt werden.  Es bietet die Möglichkeit, keine anderen COM\-Schnittstelle \(außer **IUnknown** zu verteilen, benötigen\), und wie reguläre Automatisierung, enthält es Marshallingsunterstützung nur für diese Datentypen, die durch Automatisierung unterstützt werden.  
  
 Dieser Satz von Funktionen kann ein Programm, um auf die Methoden und Eigenschaften, einschließlich Zugriff, die Auflistungen zurückgeben oder Automatisierungsobjekte, eines Objekts fördern, das auf einen zugreifbaren Netzknoten ausgeführt wird.  Wenn die Clientcomputer auch die entsprechende Software ausgeführt wird, ist es möglich, den Server zurück an den Client, danach mithilfe der Automatisierungsfeatures aufzurufen \(dies funktioniert nur für 32\-Bit\- und 64\-Bit\-Clients, und ist mit den Ereignissen vergleichbar, obwohl nicht denselben Mechanismus verwendet\).  
  
 Damit eine Anwendung sind funktional als Remote\-Agent\-Dienst Automatisierungsserver, muss sie als ausführbare Datei implementiert werden \(das heißt, als "lokaler Server" anstatt als "inproc Server"\).  
  
## Siehe auch  
 [Wann ist Remoteautomatisierung angebracht?](../mfc/where-does-remote-automation-fit-in-q.md)   
 [DCOM\-Geschichte](../mfc/history-of-dcom.md)
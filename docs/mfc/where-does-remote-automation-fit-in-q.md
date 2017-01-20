---
title: "Wann ist Remoteautomatisierung angebracht?"
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
ms.assetid: 4c4c8176-cfc0-44f7-bc87-b690f069ad2f
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Wann ist Remoteautomatisierung angebracht?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DCOM wurde im Jahre 1996 freigegeben und ist nur mit den 32\-Bit\- und 64\-Bit\-Plattformen verfügbar.  Das Visual Basic\-Team bei Microsoft hat immer Visual Basic wie mithilfe der Automatisierung gesehen, z seiner Komponenten zu ermöglichen, die kommuniziert.  Das Fehlen einer verteilten Version schränkte streng die Verwendung dieser Funktionen in Unternehmensumgebungen ein, sodass das Team hat beschlossen, das Visual Basic 4.0 Enterprise Edition, entwickelt, um die Erstellung des eigenen Satz Remotingkomponenten für die Automatisierungsteile von OLE und COM zu untersuchen.  Natürlich müssen war ein Hauptziel, sicherzustellen, dass das Ergebnis mit diesem kompatibel sein würde und von DCOM ersetzt werden kann, wenn es verfügbar wurde.  Sie anschließend mit der Projektarbeit fortfahren können, um von Automatisierung \(RA\) für 16\-Bit\- und 32\-Bit\-Windows\-Plattformen zu implementieren.  
  
 Remote\- Automatisierung ist nicht mit einer bestimmten Sprache verknüpft, sondern wenn die Version der Visual C\+\+ 4.2 Enterprise\-Edition, wurde sie nur mit Visual Basic 4.0 enthalten.  Beachten Sie, dass die Automatisierung insgesamt von DCOM zusammengefasst wird.  Wenn Sie die Möglichkeit haben DCOM, anstelle den Automatisierung in Anwendungen zu verwenden, sollten Sie so tun.  Trotzdem gibt es Szenarien, in denen eine Automatisierung mehr entspricht:  
  
-   Wenn Sie 16\-Bit\-Clients haben.  
  
-   Wenn Ihre Organisation keine DCOM\-aktivierte Version von Windows NT oder Windows 95 weiterhin bereitgestellt hat.  
  
-   Wenn Sie eine vorhandene Anwendungssuite aktualisieren, die Remoterollen Automatisierung verwendet, um C\+\+\-Komponenten anstelle einer oder mehreren Visual Basic\-Komponenten zu verwenden.  
  
 Dort müssen Sie kein Unterschied zwischen Programmen, die erstellt werden, um von Automatisierung verwenden und dass sein, die erstellt werden, um zu DCOM Automatisierung zu verwenden, und die Konfigurationshilfsprogramme machen es sehr einfach, Vorgang zwischen Remoteautomatisierung und DCOM zu wechseln.  Daher ist es nicht schwierig, eine Anwendung von den Automatisierung zu DCOM zu aktualisieren, sobald die Infrastruktur vorhanden ist.  
  
## Siehe auch  
 [Welche Vorteile hat Remoteautomatisierung?](../mfc/what-does-remote-automation-provide-q.md)   
 [DCOM\-Geschichte](../mfc/history-of-dcom.md)
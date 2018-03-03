---
title: OLE-Hintergrund | Microsoft Docs
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
- OLE, about OLE
ms.assetid: 5f654eb5-66b1-40c9-9215-bb85356a67f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e40fb7d2e58fa672196853e1edb9d5577c2cb14a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background"></a>OLE-Hintergrund
OLE wird ein Mechanismus, der ermöglicht Benutzern das Erstellen und Bearbeiten der Dokumente, die Elemente oder "Objekte" von mehreren Anwendungen erstellt.  
  
> [!NOTE]
>  OLE war ursprünglich ein Akronym für Object Linking and Embedding. Allerdings ist es nun als OLE bezeichnet. Teile von OLE, die nicht im Zusammenhang mit verlinken und Einbetten sind jetzt Bestandteil von Active-Technologie.  
  
 OLE-Dokumente, die in der Vergangenheit Verbunddokumente, aufgerufen werden verschiedene Arten von Daten oder Komponenten nahtlos integrieren. Audioclips, Kalkulationstabellen und Bitmaps sind typische Beispiele für Komponenten im OLE-Dokumente. Unterstützung von OLE in der Anwendung ermöglicht Benutzern die OLE-Dokumente zu verwenden, ohne befürchten, wechseln zwischen den verschiedenen Anwendungen; OLE wird der Wechsel für Sie.  
  
 Verwenden Sie eine Steuerelementcontainer-Anwendung zum Erstellen von zusammengesetzter Dokumenten und einer Serveranwendung oder Component-Anwendung, um die Elemente innerhalb des Containerdokuments zu erstellen. Jede Anwendung, die Sie schreiben kann es sich um einen Container, einem Server oder beides sein.  
  
 OLE umfasst viele verschiedene Konzepte, dass alle auf dem Ziel eine nahtlose Interaktion zwischen Anwendungen arbeiten. Zu diesen Bereichen zählen folgende:  
  
 Verlinken und einbetten  
 Verlinken und Einbetten sind die beiden Methoden zum Speichern von Elementen innerhalb eines OLE-Dokuments erstellt, die in einer anderen Anwendung erstellt wurden. Allgemeine Informationen zu den Unterschieden zwischen den beiden finden Sie im Artikel [OLE-Hintergrund: verlinken und einbetten](../mfc/ole-background-linking-and-embedding.md). Ausführlichere Informationen finden Sie in den Artikeln [Container](../mfc/containers.md) und [Server](../mfc/servers.md).  
  
 Direkte Aktivierung (visuelle Bearbeitung)  
 Aktivieren ein eingebettetes Element im Kontext des Containerdokuments wird die direkte Aktivierung oder die visuelle Bearbeitung aufgerufen werden. Die containeranwendung Schnittstelle ändert, um die Funktionen von der Component-Anwendung zu integrieren, die das eingebettete Element erstellt. Verknüpfte Elemente werden nie vorhanden aktiviert, da die tatsächlichen Daten für das Element in einer separaten Datei, aus Kontext der Anwendung, die der Link enthalten ist. Weitere Informationen zum direkten Aktivierung, finden Sie im Artikel [Aktivierung](../mfc/activation-cpp.md).  
  
> [!NOTE]
>  Verlinken und einbetten und direkte Aktivierung geben Sie die wichtigsten Funktionen von OLE visuelle Bearbeitung.  
  
 Automatisierung  
 Automatisierung ermöglicht einer Anwendung in einer anderen Anwendung steuern. Die steuernde Anwendung wird als Automatisierungsclient bezeichnet, und die Anwendung gesteuert wird, wird als eine Automation-Server oder der Automatisierungskomponente bezeichnet. Weitere Informationen zur Automatisierung finden Sie in den Artikeln [Automatisierungsclients](../mfc/automation-clients.md) und [Automatisierungsserver](../mfc/automation-servers.md).  
  
> [!NOTE]
>  Automation funktioniert in OLE und Active Technology Kontexten. Sie können ein Objekt basierend auf COM automatisieren.  
  
 Verbunddateien  
 Verbunddateien bieten eine standard-Dateiformat, das den strukturierten Speicherung von Verbunddokumente für OLE-Anwendungen vereinfacht. In einer Verbunddatei Speicher wurden zahlreiche Funktionen von Verzeichnissen und Streams viele Funktionen der Dateien. Diese Technologie wird auch als strukturierten Speicher bezeichnet. Weitere Informationen zu Verbunddateien, finden Sie im Artikel [Container: Verbunddateien](../mfc/containers-compound-files.md).  
  
 Uniform Data Transfer  
 Uniform Data Transfer (UDT) ist ein Satz von Schnittstellen, mit die Daten an Sie gesendete und empfangene üblich Art und Weise, unabhängig von der tatsächlichen Methode zur Datenübertragung ausgewählt werden können. UDT-Formulare, denen die Grundlage für Daten vom überträgt ziehen und ablegen. UDTS werden jetzt als Grundlage für die vorhandene Windows-Datenübertragung, z. B. die Zwischenablage und dynamischer Datenaustausch (DDE) dient. Weitere Informationen über UDT finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md).  
  
 Drag & Drop  
 Drag & Drop ist eine einfach zu bedienenden, direkte Bearbeitung Technik zum Übertragen von Daten zwischen Anwendungen, die unter Windows innerhalb einer Anwendung oder sogar in ein einzelnes Fenster in einer Anwendung. Die übertragenen Daten ist ausgewählt und an das gewünschte Ziel gezogen wird. Drag & Drop basiert auf einheitliche Datenübertragung. Weitere Informationen zu Drag & Drop, finden Sie im Artikel [Drag & Drop](../mfc/drag-and-drop-ole.md).  
  
 Component Object Model  
 Das Component Object Model (COM) bietet die Infrastruktur verwendet, wenn OLE-Objekte miteinander kommunizieren. Die MFC-OLE-Klassen vereinfachen COM-Programmierer. COM ist Teil des Active-Technologie, da COM-Objekte OLE und Active-Technologie zugrunde liegen. Weitere Informationen zu COM finden Sie unter der [Active Template Library (ATL)](../atl/active-template-library-atl-concepts.md) Themen.  
  
 Einige der wichtigeren OLE-Themen finden Sie in den folgenden Artikeln:  
  
-   [OLE-Hintergrund: Verlinken und Einbetten](../mfc/ole-background-linking-and-embedding.md)  
  
-   [OLE-Hintergrund: Container und Server](../mfc/ole-background-containers-and-servers.md)  
  
-   [OLE-Hintergrund: Implementierungsstrategien](../mfc/ole-background-implementation-strategies.md)  
  
-   [OLE-Hintergrund: MFC-Implementierung](../mfc/ole-background-mfc-implementation.md)  
  
 Allgemeine OLE-Informationen nicht in den oben aufgeführten Artikeln finden suchen Sie nach OLE in MSDN.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)


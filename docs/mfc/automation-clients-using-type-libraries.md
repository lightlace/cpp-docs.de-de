---
title: "Automatisierungsclients: Verwenden von Typbibliotheken"
ms.custom: na
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MkTypLib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODL-Dateien"
  - "Automatisierungsclients, Typbibliotheken"
  - "Klassen [C++], Dispatch"
  - "Clients, Automatisierung"
  - "dispatch-Klasse"
  - "MkTypLib-Tool"
  - "ODL (Object Description Language)"
  - "ODL-Dateien"
  - "Typbibliotheken, Automatisierungsclients"
ms.assetid: d405bc47-118d-4786-b371-920d035b2047
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Automatisierungsclients: Verwenden von Typbibliotheken
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Automatisierungsclients müssen Informationen über die Eigenschaften und Methoden Serverobjekten haben, wenn die Clients die Server bearbeiten sollen.  Eigenschaften verfügen; Datentypen der Methoden Rückgabewerte häufig und akzeptieren Parameter.  Der Client fordert Informationen über Datentypen aus allen diesen, um zum Serverobjekttyp statisch zu binden.  
  
 Diese Typinformationen können auf verschiedene Weise wird angegeben werden.  Es wird empfohlen, um eine Typbibliothek zu erstellen.  
  
 Informationen zur [MkTypLib](http://msdn.microsoft.com/library/windows/desktop/aa366797), finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Visual C\+\+ kann eine Typbibliotheksdatei lesen und eine Dispatchklasse erstellen, die von [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md) abgeleitet wird.  Ein Objekt dieser Klasse sind Eigenschaften und Vorgänge, die die dem Serverobjekts duplizieren.  Die Anwendung ruft dieses die Eigenschaften und die Vorgänge des Objekts auf, und die Funktionen, die von `COleDispatchDriver` geerbt wurde, leitet diese Aufrufe OLE\-System weiter, die diese wiederum an das Serverobjekt weiterleitet.  
  
 Visual C\+\+ wird automatisch diese Typbibliotheksdatei für Sie verwaltet, wenn Sie festgelegt haben, dass die Automatisierung einzubeziehen, als das Projekt erstellt wurde.  Als Teil jedes Builds wird der TLB\-Datei mit MkTypLib erstellt.  
  
### Um eine Dispatchklasse aus einer Datei der Typbibliothek \(.tlb\) erstellen  
  
1.  Klicken Sie in der Klassenansicht in Projektmappen\-Explorer oder klicken Sie mit der rechten Maustaste auf das Projekt und klicken Sie auf **Hinzufügen** und dann im Kontextmenü auf **Klasse hinzufügen**.  
  
2.  **Klasse hinzufügen** Im Dialogfeld wählen Sie den Ordner **Visual C\+\+\/MFC** im linken Bereich aus.  Wählen Sie das Symbol **MFC\-Klasse aus der Typbibliothek \(typelib\)** im rechten Bereich aus und klicken Sie auf **Öffnen**.  
  
3.  Im Dialogfeld **Assistent zum Hinzufügen von Klassen aus der Typbibliothek** eine Typbibliothek der Dropdownliste **Verfügbare Typbibliotheken** aus.  Das **Schnittstellen** Feld sind die Schnittstellen an, die für die ausgewählte Typbibliothek verfügbar sind.  
  
    > [!NOTE]
    >  Sie können Schnittstellen von mehr als einer Typbibliothek aus.  
  
     Um Schnittstellen auswählen, auf diese doppelklicken oder auf die Schaltfläche **Hinzufügen** klicken.  Wenn Sie dies durchführen, werden die Namen für Dispatchklassen im Feld **Generierte Klassen**.  Sie können die Klassennamen im `Class` Feld bearbeiten.  
  
     Das Feld **Datei** wird die Datei angezeigt, in der Klasse deklariert ist. \(Sie können diesen Dateinamen auch bearbeiten\).  Sie können die Schaltfläche Durchsuchen auch verwenden, um andere Dateien auszuwählen, wenn Sie lieber, Kopf\- und der Implementierungsinformationen zu haben, die in vorhandene Dateien oder in ein Verzeichnis als dem Projektverzeichnis geschrieben werden.  
  
    > [!NOTE]
    >  Alle Dispatchklassen für die ausgewählten Schnittstellen werden in die Datei eingefügt, die hier angegeben wird.  Wenn Sie die Schnittstellen in separaten Header deklariert werden soll, müssen Sie diesen Assistenten für eine Headerdatei ausführen, die Sie erstellen möchten.  
  
    > [!NOTE]
    >  Einige Typbibliotheksinformationen werden in Dateien mit .DLL\-, .OCX\- oder .OLB\-Dateierweiterungen gespeichert.  
  
4.  Klicken Sie auf **Fertig stellen**.  
  
     Der Assistent schreibt den Code für die Dispatchklassen mithilfe der angegebenen Klasse und der Dateinamen.  
  
## Siehe auch  
 [Automatisierungsclients](../mfc/automation-clients.md)
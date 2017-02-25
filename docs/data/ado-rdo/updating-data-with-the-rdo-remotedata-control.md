---
title: "Aktualisieren von Daten mit dem RDO-Remote-Datensteuerelement | Microsoft Docs"
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
  - "RDO-Remote-Datensteuerelement"
  - "RDO-Remote-Datensteuerelement, Aktualisieren von Daten"
  - "RemoteData-Steuerelement"
  - "RemoteData-Steuerelement, Aktualisieren von Daten"
ms.assetid: abb4175f-612e-4645-905e-c0fa918b0fd7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Aktualisieren von Daten mit dem RDO-Remote-Datensteuerelement
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Daten des RDO\-Remote\-Datensteuerelements können entweder schreibgeschützt oder veränderbar sein.  
  
### So erstellen Sie eine Anwendung, in der Daten mithilfe eines RDO\-Remote\-Datensteuerelements geändert werden  
  
1.  Legen Sie die **CursorDriver**\-Eigenschaft des RDO\-Remote\-Datensteuerelements fest.  
  
    -   Zurückgegebene Daten werden von serverseitigen Cursorn auf dem Server gespeichert.  
  
    -   Daten im lokalen Clientspeicher werden von clientseitigen ODBC\-Cursorn gespeichert.  
  
    -   Client Batch\-Cursor verwenden eine Cursorbibliothek, die auf Parallelitätsaspekte zugeschnitten ist.  
  
    -   Bei Ausführung einer Aktionsabfrage wird eine "No Cursor"\-Option verwendet, sodass kein Cursor erforderlich ist.  
  
2.  Legen Sie die **LockType**\-Eigenschaft des RDO\-Remote\-Datensteuerelements fest.  Es wird vollständige Parallelität auf der Grundlage einer Resultsetoption empfohlen.  
  
    -   Die schreibgeschützte Parallelität sollte nicht verwendet werden, wenn die Daten veränderbar sein sollen.  
  
    -   Bei der eingeschränkten Parallelität werden Daten während der Aktualisierung gesperrt, damit andere Benutzer nicht Gefahr laufen, inkompatible Änderungen an den Daten vorzunehmen.  
  
    -   Bei der vollständigen Parallelität werden die Daten nicht gesperrt. Wird während eines Commits jedoch erkannt, dass ein anderer Client einen inkompatiblen Zustand bereitgestellt hat, gibt das RDO\-Remote\-Datensteuerelement eine Fehlermeldung aus.  
  
3.  Legen Sie die **ResultsetType**\-Eigenschaft des RDO\-Remote\-Datensteuerelements fest.  Stellen Sie sicher, dass die ausgewählten Optionen vom ODBC\-Treiber unterstützt werden:  
  
    -   Wenn Sie einen statischen Cursor erstellen, werden Änderungen so lange nicht erkannt, bis der Cursor geschlossen und erneut geöffnet wird.  
  
    -   Wenn Sie einen Keysetcursor erstellen, lässt der Cursor beliebige Einfügungen, Aktualisierungen und Löschvorgänge innerhalb des Keysetcursors zu.  
  
4.  Legen Sie Eigenschaften des datengebundenen Steuerelements fest, um Aktualisierbarkeit zu gewährleisten.  Beachten Sie, dass einige Steuerelemente keine Aktualisierung zulassen.  
  
 Informationen über die Verwendung dieser Objekte finden Sie in der Dokumentation zum RDO\-Remote\-Datensteuerelement.  
  
## Siehe auch  
 [RDO\-Datenbindung](../../data/ado-rdo/rdo-databinding.md)   
 [Verwenden der RDO\-Datenbindung in Visual C\+\+](../../data/ado-rdo/using-rdo-databinding-in-visual-cpp.md)
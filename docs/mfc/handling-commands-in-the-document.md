---
title: "Behandeln von Kommentaren in einem Dokument"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "WM_COMMAND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlsbehandlung"
  - "Befehlsbehandlung, Befehle in Dokumenten"
  - "Dokumente, Behandeln von Meldungen in"
  - "Dokumente, Meldungszuordnungen"
  - "Meldungsbehandlung, WM_COMMAND-Meldungen"
  - "Meldungszuordnungen, in Dokumentklassen"
  - "WM_COMMAND"
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Behandeln von Kommentaren in einem Dokument
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

die Dokumentklasse behandelt auch bestimmte Befehle, die von Menüelementen, Symbolleisten\-Schaltflächen oder Tastenkombinationen generiert werden.  Standardmäßig behandelt **CDocument** den Speicherungs\- und speichern als Befehle im Menü Datei, mithilfe der Serialisierung.  Andere Befehle, die die Daten auswirken, werden auch von Memberfunktionen des Dokuments behandelt werden.  Im Scribbleprogramm, Klasse stellt einen Handler `CScribDoc` für den Bearbeitungs\-freienRaum aller Befehl bereitgestellt, der alle Daten löscht, die momentan im Dokument gespeichert sind.  Dokumente können Meldungszuordnungen haben, aber als Ansichten, Dokumente können Standardwindows\-meldungen nicht bearbeiten nur **WM\_COMMAND** \- Meldungen oder Befehle "."  
  
## Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)
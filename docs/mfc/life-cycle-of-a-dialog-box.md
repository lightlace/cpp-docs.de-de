---
title: "Lebenszyklus eines Dialogfelds | Microsoft Docs"
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
  - "Dialogfelder, Lebenszyklus"
  - "Lebenszyklus von Dialogfeldern"
  - "MFC-Dialogfelder, Lebenszyklus"
  - "Modale Dialogfelder, Lebenszyklus"
  - "Nicht modale Dialogfelder, Lebenszyklus"
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Lebenszyklus eines Dialogfelds
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Während des Lebenszyklus eines Dialogfelds, ruft der Benutzer das Dialogfeld, normalerweise innerhalb eines Befehlshandlers, das gleichzeitig erstellt und initialisiert, der Benutzer interagiert auf das Dialogfeld auf, und das Dialogfeld schließt.  
  
 Für modalen Dialogfelder erfasst Ihr Handler alle Daten der eingegebene Benutzer, sobald das Dialogfeld geschlossen wird.  Da das gleichzeitig vorhanden ist, wenn sein Dialogfeld geschlossen hat, können Sie die Membervariablen der Dialogfeldklasse einfach verwenden, um die Daten zu extrahieren.  
  
 Nicht modale Dialogfelder extrahieren Sie möglicherweise häufig Daten im Dialogfeldobjekt, während das Dialogfeld noch angezeigt ist.  Daraufhin wird das gleichzeitig gelöscht; Wenn dies geschieht, hängt von dem Code ab.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Erstellen und Anzeigen von Dialogfeldern](../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [Erstellen für modale Dialogfelder](../mfc/creating-modal-dialog-boxes.md)  
  
-   [Erstellen von nicht modalen Dialogfeldern](../mfc/creating-modeless-dialog-boxes.md)  
  
-   [Verwenden einer Dialogfeldvorlage im Arbeitsspeicher](../mfc/using-a-dialog-template-in-memory.md)  
  
-   [Festlegen der Hintergrundfarbe des Dialogfelds](../mfc/setting-the-dialog-box’s-background-color.md)  
  
-   [Initialisieren des Dialogfelds](../mfc/initializing-the-dialog-box.md)  
  
-   [Behandlungs\-Windows\-Meldungen im Dialogfeld](../mfc/handling-windows-messages-in-your-dialog-box.md)  
  
-   [Abrufen von Daten im Dialogfeldobjekt](../mfc/retrieving-data-from-the-dialog-object.md)  
  
-   [Schließen des Dialogfelds](../mfc/closing-the-dialog-box.md)  
  
-   [Zerstören des Dialogfelds](../mfc/destroying-the-dialog-box.md)  
  
-   [Dialogdatenaustausch \(DDX\) und Validierung \(DDV\)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Eigenschaftenblattdialogfelder](../mfc/property-sheets-and-property-pages-mfc.md)  
  
## Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)
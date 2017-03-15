---
title: "Initialisieren des Dialogfelds | Microsoft Docs"
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
  - "Initialisieren von Dialogfeldern"
  - "MFC-Dialogfelder, Initialisieren"
  - "Modale Dialogfelder, Initialisieren"
  - "Nicht modale Dialogfelder, Initialisieren"
  - "OnInitDialog-Methode"
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Initialisieren des Dialogfelds
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem das Dialogfeld und sämtliche Steuerelemente erstellt sind, jedoch bevor das Dialogfeld \(jedes Typs\) auf dem Bildschirm angezeigt wird, wird die [OnInitDialog](../Topic/CDialog::OnInitDialog.md)\-Memberfunktion des Dialogfeldobjekts aufgerufen.  Ein modales Dialogfeld tritt dies während des Aufrufs auf `DoModal`.  Ein nicht modales Dialogfeld wird `OnInitDialog` aufgerufen, wenn **Erstellen** aufgerufen wird.  Sie überschreiben normalerweise `OnInitDialog`, um die Steuerelemente im Dialogfeld, z Festlegen des ursprünglichen Texts eines Eingabefelds zu initialisieren.  Sie müssen die `OnInitDialog`\-Memberfunktion der Basisklasse, `CDialog` aufrufen, von der `OnInitDialog` \- Überschreibung.  
  
 Wenn Sie die Hintergrundfarbe des Dialogfelds \(und die aller anderen Dialogfelder\) in der Anwendung festlegen möchten, finden Sie unter [Festlegen der Hintergrundfarbe des Dialogfelds](../mfc/setting-the-dialog-box’s-background-color.md).  
  
## Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)
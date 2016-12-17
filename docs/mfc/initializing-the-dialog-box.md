---
title: "Initialisieren des Dialogfelds"
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
  - "Initialisieren von Dialogfeldern"
  - "MFC-Dialogfelder, Initialisieren"
  - "Modale Dialogfelder, Initialisieren"
  - "Nicht modale Dialogfelder, Initialisieren"
  - "OnInitDialog-Methode"
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Initialisieren des Dialogfelds
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem das Dialogfeld und sämtliche Steuerelemente erstellt sind, jedoch bevor das Dialogfeld \(jedes Typs\) auf dem Bildschirm angezeigt wird, wird die [OnInitDialog](../Topic/CDialog::OnInitDialog.md)\-Memberfunktion des Dialogfeldobjekts aufgerufen.  Ein modales Dialogfeld tritt dies während des Aufrufs auf `DoModal`.  Ein nicht modales Dialogfeld wird `OnInitDialog` aufgerufen, wenn **Erstellen** aufgerufen wird.  Sie überschreiben normalerweise `OnInitDialog`, um die Steuerelemente im Dialogfeld, z Festlegen des ursprünglichen Texts eines Eingabefelds zu initialisieren.  Sie müssen die `OnInitDialog`\-Memberfunktion der Basisklasse, `CDialog` aufrufen, von der `OnInitDialog` \- Überschreibung.  
  
 Wenn Sie die Hintergrundfarbe des Dialogfelds \(und die aller anderen Dialogfelder\) in der Anwendung festlegen möchten, finden Sie unter [Festlegen der Hintergrundfarbe des Dialogfelds](../mfc/setting-the-dialog-box’s-background-color.md).  
  
## Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)
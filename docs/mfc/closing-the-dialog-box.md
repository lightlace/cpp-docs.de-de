---
title: "Schlie&#223;en des Dialogfelds | Microsoft Docs"
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
  - "Dialogfelder, Schließen"
  - "MFC-Dialogfelder, Schließen"
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Schlie&#223;en des Dialogfelds
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein modales Dialogfeld schließt, wenn eine der Schaltflächen, normalerweise die Schaltfläche OK oder die Abbruchschaltfläche auswählt.  Die Auswahl " oder Abbrechen geklickt wird Windows, das gleichzeitig zu übermitteln eine **BN\_CLICKED**\-Steuerelement\-Benachrichtigung mit ID der Schaltfläche, entweder **IDOK** oder **IDCANCEL**.  `CDialog` stellt Standardhandlerfunktionen für diese Meldungen bereit: `OnOK` und `OnCancel`.  Die Standardhandler rufen die `EndDialog`\-Memberfunktion auf, um das Dialogfeld zu schließen.  Sie können `EndDialog` aus Ihrem eigenen Code aufrufen.  Weitere Informationen finden Sie in [EndDialog](../Topic/CDialog::EndDialog.md)\-Memberfunktion der `CDialog`\-Klasse in der *MFC\-Referenz*.  
  
 Um zum Schließen und Löschen eines nicht modalen Dialogfelds, der `PostNcDestroy` überschreiben anordnen und den Operator **löschen** im **this** Zeiger aufrufen.  [Zerstören des Dialogfelds](../mfc/destroying-the-dialog-box.md) erläutert, was als Nächstes geschieht.  
  
## Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)
---
title: Lebenszyklus eines Dialogfelds | Microsoft Docs
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
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 743aed312008d1908701933ec642dd52b0ac3ec8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="life-cycle-of-a-dialog-box"></a>Lebenszyklus eines Dialogfelds
Während des Lebenszyklus eines Dialogfelds der Benutzer das Dialogfeld aufgerufen, in der Regel in einem Befehlshandler, der erstellt und initialisiert das Dialogfeldobjekt, Benutzerinteraktion mit dem Dialogfeld und das Dialogfeld wird geschlossen.  
  
 Für modale Dialogfelder sammelt der Handler keine Daten vom Benutzer eingegeben wird, sobald das Dialogfeld geschlossen wird. Da das Dialogfeldobjekt vorhanden ist, nachdem das Dialogfeld Fenster geschlossen wurde, können Sie einfach die Membervariablen der Dialogfeldklasse verwenden, um die Daten zu extrahieren.  
  
 Für nicht modale Dialogfelder können Sie Daten aus dem Dialogfeldobjekt auf häufig extrahieren, während das Dialogfeld immer noch sichtbar ist. Zu einem späteren Zeitpunkt wird das Dialogfeldobjekt zerstört. Wenn dies geschieht, hängt von Ihren Code ab.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Erstellen und Anzeigen von Dialogfeldern](../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [Erstellen von modalen Dialogfeldern](../mfc/creating-modal-dialog-boxes.md)  
  
-   [Erstellen von nicht modalen Dialogfeldern](../mfc/creating-modeless-dialog-boxes.md)  
  
-   [Verwenden einer Dialogvorlage im Speicher](../mfc/using-a-dialog-template-in-memory.md)  
  
-   [Das Dialogfeld Hintergrundfarbe festlegen](../mfc/setting-the-dialog-boxs-background-color.md)  
  
-   [Initialisieren des Dialogfelds](../mfc/initializing-the-dialog-box.md)  
  
-   [Behandlung von Windows-Meldungen in einem Dialogfeld](../mfc/handling-windows-messages-in-your-dialog-box.md)  
  
-   [Abrufen von Daten aus dem Dialogfeldobjekt](../mfc/retrieving-data-from-the-dialog-object.md)  
  
-   [Schließen des Dialogfelds](../mfc/closing-the-dialog-box.md)  
  
-   [Zerstören des Dialogfelds](../mfc/destroying-the-dialog-box.md)  
  
-   [Dialogdatenaustausch (DDX) und Überprüfung (DDV)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Eigenschaftenblatt-Dialogfelder](../mfc/property-sheets-and-property-pages-mfc.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)


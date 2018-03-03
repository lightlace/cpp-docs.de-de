---
title: Zuordnen von Windows-Meldungen zu einer Klasse | Microsoft Docs
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
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4701b0ae9f71099febb1a239cea6285fb0a7b229
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mapping-windows-messages-to-your-class"></a>Zuordnen von Windows-Meldungen zu einer Klasse
Wenn Sie das Dialogfeld Windows-Nachrichten zu verarbeiten möchten, überschreiben Sie die entsprechenden Handler-Funktionen. Verwenden Sie hierzu im Eigenschaftenfenster [ordnen Sie die Nachrichten](../mfc/reference/mapping-messages-to-functions.md) der Dialogfeld-Klasse. Schreibt einen Eintrag für die Nachricht-Zuordnung für jede Nachricht, und fügt die Meldungshandler Memberfunktionen der Klasse. Verwenden Sie die Visual C++ Quellcode-Editors zum Schreiben von Code in die Meldungshandler.  
  
 Sie können auch festlegen, überschreiben Memberfunktionen der [CDialog](../mfc/reference/cdialog-class.md) und deren Basisklassen besonders [CWnd](../mfc/reference/cwnd-class.md).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)  
  
-   [Überschreibbare Memberfunktionen](../mfc/commonly-overridden-member-functions.md)  
  
-   [Häufig hinzugefügte Memberfunktionen](../mfc/commonly-added-member-functions.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)


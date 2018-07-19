---
title: Zuordnen von Windows-Meldungen zu einer Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 398888a858165197c6e35be791169a9311f3014b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346268"
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


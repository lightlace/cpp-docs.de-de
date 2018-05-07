---
title: Validieren von Dialogfelddaten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 229b4a5ffb32f4a167dcc8393a269bbb2e35b500
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dialog-data-validation"></a>Validieren von Dialogfelddaten
Sie können Überprüfung zusätzlich zu den Datenaustausch durch Aufrufen von DDV-Funktionen angeben, wie im Beispiel gezeigt [Dialogdatenaustausch](../mfc/dialog-data-exchange.md). Die `DDV_MaxChars` Aufruf im Beispiel wird überprüft, dass die in das Textfeld Steuerelement eingegebene Zeichenfolge nicht mehr als 20 Zeichen ist. DDV-Funktion Warnungen in der Regel den Benutzer ein Meldungsfeld an, wenn die Überprüfung schlägt fehl, und legt den Fokus auf dem betreffenden-Steuerelement, damit der Benutzer die Daten erneut eingeben kann. Eine DDV-Funktion für ein bestimmtes Steuerelement muss unmittelbar nach der DDX-Funktion für dasselbe Steuerelement aufgerufen werden.  
  
 Sie können auch eigene benutzerdefinierte DDX- und DDV-Routinen definieren. Einzelheiten dazu und andere Aspekte der DDX- und DDV finden Sie unter [MFC technischer Hinweis 26](../mfc/tn026-ddx-and-ddv-routines.md).  
  
 Die [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) Schreiben aller der DDX und DDV-Aufrufe in der datenzuordnung für Sie.  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelddaten Dialogdatenaustausch und-Validierung](../mfc/dialog-data-exchange-and-validation.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [Dialogdatenaustausch](../mfc/dialog-data-exchange.md)


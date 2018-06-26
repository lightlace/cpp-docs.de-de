---
title: Abrufen von Daten aus dem Dialogfeldobjekt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], retrieving user data
- dialog box data [MFC]
- data [MFC], retrieving
- GetDlgItemText method [MFC]
- SetDlgItemText method [MFC]
- SetWindowText method [MFC]
- dialog box data [MFC], retrieving
- retrieving data [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- dialog box controls [MFC], initializing values
- DDX (dialog data exchange) [MFC]
- MFC dialog boxes [MFC], retrieving user input
- data retrieval [MFC], dialog boxes
- data [MFC], dialog boxes
- DDX (dialog data exchange) [MFC], about DDX
- DDX (dialog data exchange) [MFC], retrieving data from Dialog object
- GetWindowText method [MFC]
ms.assetid: bdca2b61-6b53-4c2e-b426-8712c7a38ec0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b221bd97d9ee943e19b043bcc9be6aba0fa1672
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929594"
---
# <a name="retrieving-data-from-the-dialog-object"></a>Abrufen von Daten aus dem Dialogfeldobjekt
Das Framework bietet eine einfache Möglichkeit, um die Werte von Steuerelementen in einem Dialogfeld zu initialisieren und zum Abrufen der Werte aus den Steuerelementen. Der mehr arbeitsaufwendig manuelle Ansatz ist die Funktionen aufrufen, wie die `SetDlgItemText` und `GetDlgItemText` Memberfunktionen der Klasse `CWnd`, das Steuerelement Windows gelten. Mit diesen Funktionen Sie Zugriff auf jedes Steuerelement einzeln zu festlegen oder Abrufen des Objektwerts, Aufrufen von Funktionen wie z. B. `SetWindowText` und `GetWindowText`. Das Framework Ansatz automatisiert Initialisierung und abrufen.  
  
 Dialogdatenaustausch (DDX) können Sie die Daten zwischen den Steuerelementen in das Dialogfeld und den Membervariablen in dem Dialogfeldobjekt leichter austauschen. Dieser Austausch funktioniert beide Richtungen. Um die Steuerelemente im Dialogfeld zu initialisieren, Sie können die Werte der Datenelemente im Dialogfeld festlegen, und das Framework übertragen die Werte für die Steuerelemente ab, bevor Sie das Dialogfeld angezeigt wird. Anschließend können Sie jederzeit die Dialogfeld-Datenmember mit vom Benutzer eingegebenen Daten aktualisieren. An diesem Punkt können Sie die Daten durch einen Verweis auf die Daten Membervariablen.  
  
 Sie können auch für die Werte der Dialogfeld-Steuerelemente, die automatisch mit Validieren von Dialogfelddaten (DDV) überprüft werden anordnen.  
  
 DDX- und DDV werden ausführlicher in [Dialogdatenaustausch und-Validierung](../mfc/dialog-data-exchange-and-validation.md).  
  
 Für ein modales Dialogfeld rufen Sie alle Daten, die vom Benutzer wenn eingegebenen `DoModal` IDOK zurückgegeben, aber bevor das Dialogfeld Objekt zerstört wird. Für ein nicht modales Dialogfeld kann Abrufen von Daten aus dem Dialogfeldobjekt jederzeit aufrufen `UpdateData` mit dem Argument **"true"** und klicken Sie dann den Zugriff auf Membervariablen für Dialogfeld-Klasse. Dieses Thema wird ausführlicher im [Dialogdatenaustausch und-Validierung](../mfc/dialog-data-exchange-and-validation.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)


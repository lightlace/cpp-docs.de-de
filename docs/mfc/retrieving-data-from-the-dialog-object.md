---
title: Abrufen von Daten aus dem Dialogfeldobjekt | Microsoft-Dokumentation
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
ms.openlocfilehash: 3055468c04bba7c9cb999d0a642c0819524ff7e7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391409"
---
# <a name="retrieving-data-from-the-dialog-object"></a>Abrufen von Daten aus dem Dialogfeldobjekt

Das Framework bietet eine einfache Möglichkeit zum Initialisieren der Werte von Steuerelementen in einem Dialogfeld und Werte aus den Steuerelementen abzurufen. Beim manuellen vorgehen werden mehr arbeitsaufwendig ist zum Aufrufen von Funktionen wie z. B. die `SetDlgItemText` und `GetDlgItemText` Memberfunktionen der Klasse `CWnd`, die für das Steuerelement von Windows gelten. Mit dieser Funktionen die, Sie Zugriff auf jedes Steuerelement einzeln durch, um festlegen oder Abrufen von seinem Wert Aufrufen von Funktionen wie z. B. `SetWindowText` und `GetWindowText`. Die Framework Ansatz automatisiert sowohl Initialisierung und abrufen.

Dialogdatenaustausch (DDX) können Sie Daten zwischen den Steuerelementen im Dialogfeld und Membervariablen Variablen im Dialogfeld noch einfacher. Dieser Austausch funktioniert in beide Richtungen. Um die Steuerelemente in das Dialogfeld zu initialisieren, können Sie die Werte der Datenelemente im Dialogfeld festlegen, und das Framework werden die Werte für die Steuerelemente übertragen, bevor Sie das Dialogfeld angezeigt wird. Anschließend können Sie jederzeit die Dialogfeld-Datenmember mit vom Benutzer eingegebenen Daten aktualisieren. An diesem Punkt können Sie die Daten durch einen Verweis auf die Daten Membervariablen.

Sie können auch für die Werte der Dialogfeld-Steuerelemente, die automatisch mit von Dialogfelddaten (DDV) überprüft werden anordnen.

DDX- und DDV werden ausführlicher in [Dialogdatenaustausch und Validierung](../mfc/dialog-data-exchange-and-validation.md).

Für ein modales Dialogfeld, rufen Sie können alle Daten, die der Benutzer eingegeben wird, wenn `DoModal` IDOK zurückgegeben, aber bevor das Dialogfeld Objekt zerstört wird. Für ein nicht modales Dialogfeld, Sie können Daten abrufen aus dem Dialogfeldobjekt zu einem beliebigen Zeitpunkt durch Aufrufen von `UpdateData` mit dem Argument **"true"** und anschließendes zugreifen auf Membervariablen für Dialogfeld-Klasse. Dieses Thema wird ausführlicher erläutert [Dialogdatenaustausch und Validierung](../mfc/dialog-data-exchange-and-validation.md).

## <a name="see-also"></a>Siehe auch

[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)


---
title: Abrufen von Daten aus dem Dialogfeldobjekt
ms.date: 11/04/2016
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
ms.openlocfilehash: 903d76a1e672d05a3c093e528f7153562df8e3e5
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685569"
---
# <a name="retrieving-data-from-the-dialog-object"></a>Abrufen von Daten aus dem Dialogfeldobjekt

Das Framework bietet eine einfache Möglichkeit, die Werte von Steuerelementen in einem Dialogfeld zu initialisieren und Werte aus den Steuerelementen abzurufen. Die aufwändiger manuelle Vorgehensweise besteht darin, Funktionen wie die `SetDlgItemText`-und `GetDlgItemText`-Element Funktionen der Klasse `CWnd` aufzurufen, die auf Steuerelemente angewendet werden. Mit diesen Funktionen können Sie auf jedes Steuerelement einzeln zugreifen, um seinen Wert festzulegen oder abzurufen, indem Sie Funktionen wie `SetWindowText` und `GetWindowText` aufrufen. Der Ansatz des Frameworks automatisiert die Initialisierung und den Abruf.

Mit dem Dialogfeld Datenaustausch (DDX) können Sie die Daten zwischen den Steuerelementen im Dialogfeld und den Element Variablen im Dialog Objekt leichter austauschen. Dieser Austausch funktioniert auf beide Arten. Wenn Sie die Steuerelemente im Dialogfeld initialisieren möchten, können Sie die Werte von Datenmembern im Dialogfeld Objekt festlegen, und das Framework überträgt die Werte auf die Steuerelemente, bevor das Dialogfeld angezeigt wird. Anschließend können Sie die Dialog Datenelemente jederzeit mit den vom Benutzer eingegebenen Daten aktualisieren. An diesem Punkt können Sie die Daten verwenden, indem Sie auf die Datenmember-Variablen verweisen.

Sie können auch festlegen, dass die Werte der Dialogfeld Steuerelemente automatisch mit der Dialog Datenüberprüfung (Dialog Data Validation, DDV) überprüft werden.

DDX und DDV werden im [Dialog Datenaustausch und](../mfc/dialog-data-exchange-and-validation.md)in der Validierung ausführlicher erläutert.

Bei einem modalen Dialogfeld können Sie alle Daten abrufen, die der Benutzer eingegeben hat, wenn `DoModal` IDOK zurückgibt, aber bevor das Dialogfeld Objekt zerstört wird. Für ein nicht modalem Dialogfeld können Sie jederzeit Daten aus dem Dialog Objekt abrufen, indem Sie `UpdateData` mit dem Argument **true** aufrufen und dann auf Dialogfeld-Member-Variablen zugreifen. Dieses Thema wird im [Dialog Datenaustausch und](../mfc/dialog-data-exchange-and-validation.md)in der Validierung ausführlicher erläutert.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)

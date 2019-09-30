---
title: Initialisieren des Dialogfelds
ms.date: 11/04/2016
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
ms.openlocfilehash: 14cdf94bef79f254b4aaa2c1c0dfba6c88b7498b
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685627"
---
# <a name="initializing-the-dialog-box"></a>Initialisieren des Dialogfelds

Nachdem das Dialogfeld und alle zugehörigen Steuerelemente erstellt wurden, aber kurz bevor das Dialogfeld (eines der beiden Typen) auf dem Bildschirm angezeigt wird, wird die [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) -Member-Funktion des Dialog Objekts aufgerufen. Bei einem modalen Dialogfeld erfolgt dies während des `DoModal`-Aufrufes. Bei einem nicht modalem Dialogfeld wird `OnInitDialog` aufgerufen, wenn `Create` aufgerufen wird. In der Regel überschreiben Sie `OnInitDialog`, um die Steuerelemente des Dialog Felds zu initialisieren, z. b. das Festlegen des Anfangs Texts eines Bearbeitungs Felds. Sie müssen die `OnInitDialog`-Member-Funktion der Basisklasse, `CDialog`, von der `OnInitDialog`-außer Kraft Setzung aus abrufen.

Wenn Sie die Hintergrundfarbe des Dialog Felds (und die aller anderen Dialogfelder in der Anwendung) festlegen möchten, finden Sie weitere Informationen unter [Festlegen der Hintergrundfarbe für das Dialogfeld](../mfc/setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)

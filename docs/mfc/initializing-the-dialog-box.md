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
ms.openlocfilehash: 87b3405f1441e730cf5c9ce7fc03d2c7372e55db
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289532"
---
# <a name="initializing-the-dialog-box"></a>Initialisieren des Dialogfelds

Nachdem das Dialogfeld Feld und alle Steuerelemente werden erstellt, aber noch bevor das Dialogfeld wird das (unabhängig vom Typ) des Screens, dem Dialogfeldobjekt [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Memberfunktion aufgerufen wird. Für ein modales Dialogfeld, dies geschieht bei der `DoModal` aufrufen. Für ein nicht modales Dialogfeld `OnInitDialog` wird aufgerufen, wenn `Create` aufgerufen wird. Überschreiben Sie i. d. r. `OnInitDialog` um das Dialogfeld-Steuerelemente, z. B. das Festlegen von des ursprünglichen Texts des ein Bearbeitungsfeld zu initialisieren. Rufen Sie die `OnInitDialog` Member-Funktion der Basisklasse, `CDialog`, aus Ihrem `OnInitDialog` außer Kraft setzen.

Wenn Sie die Hintergrundfarbe des Dialogfelds (und mit der alle anderen Dialogfelder in Ihrer Anwendung) festlegen möchten, finden Sie unter [Festlegen der Hintergrundfarbe des Dialogfelds](../mfc/setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>Siehe auch

[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

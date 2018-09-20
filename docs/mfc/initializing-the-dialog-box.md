---
title: Initialisieren des Dialogfelds | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42526eea184cb4f28d5214fe0c56281ac6da9d6c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426106"
---
# <a name="initializing-the-dialog-box"></a>Initialisieren des Dialogfelds

Nachdem das Dialogfeld Feld und alle Steuerelemente werden erstellt, aber noch bevor das Dialogfeld wird das (unabhängig vom Typ) des Screens, dem Dialogfeldobjekt [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Memberfunktion aufgerufen wird. Für ein modales Dialogfeld, dies geschieht bei der `DoModal` aufrufen. Für ein nicht modales Dialogfeld `OnInitDialog` wird aufgerufen, wenn `Create` aufgerufen wird. Überschreiben Sie i. d. r. `OnInitDialog` um das Dialogfeld-Steuerelemente, z. B. das Festlegen von des ursprünglichen Texts des ein Bearbeitungsfeld zu initialisieren. Rufen Sie die `OnInitDialog` Member-Funktion der Basisklasse, `CDialog`, aus Ihrem `OnInitDialog` außer Kraft setzen.

Wenn Sie die Hintergrundfarbe des Dialogfelds (und mit der alle anderen Dialogfelder in Ihrer Anwendung) festlegen möchten, finden Sie unter [Festlegen der Hintergrundfarbe des Dialogfelds](../mfc/setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>Siehe auch

[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)


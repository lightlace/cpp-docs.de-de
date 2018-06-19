---
title: Initialisieren des Dialogfelds | Microsoft Docs
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
ms.openlocfilehash: 7918180a437687eded090b3d014e4affe38fe8f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344710"
---
# <a name="initializing-the-dialog-box"></a>Initialisieren des Dialogfelds
Nachdem das Dialogfeld Feld und alle Steuerelemente werden erstellt, aber noch bevor das Dialogfeld im Feld (Typ) auf dem Bildschirm angezeigt, dem Dialogfeldobjekt des [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Memberfunktion aufgerufen wird. Für ein modales Dialogfeld, dies geschieht bei der `DoModal` aufrufen. Für ein nicht modales Dialogfeld `OnInitDialog` wird aufgerufen, wenn **erstellen** aufgerufen wird. Überschreiben Sie i. d. r. `OnInitDialog` um das Dialogfeld-Steuerelemente, z. B. das Festlegen des ersten Texts, der ein Bearbeitungsfeld zu initialisieren. Rufen Sie die `OnInitDialog` Member-Funktion der Basisklasse, `CDialog`, aus der `OnInitDialog` außer Kraft setzen.  
  
 Wenn Sie die Hintergrundfarbe des Dialogfelds (und von anderen Dialogfeldern in Ihrer Anwendung) festlegen möchten, finden Sie unter [Festlegen der Hintergrundfarbe des Dialogfelds](../mfc/setting-the-dialog-boxs-background-color.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)


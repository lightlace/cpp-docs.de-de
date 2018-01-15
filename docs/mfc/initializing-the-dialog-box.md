---
title: Initialisieren des Dialogfelds | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2af05011e8f2af2993edf3ea2f82716137b17857
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-the-dialog-box"></a>Initialisieren des Dialogfelds
Nachdem das Dialogfeld Feld und alle Steuerelemente werden erstellt, aber noch bevor das Dialogfeld im Feld (Typ) auf dem Bildschirm angezeigt, dem Dialogfeldobjekt des [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Memberfunktion aufgerufen wird. Für ein modales Dialogfeld, dies geschieht bei der `DoModal` aufrufen. Für ein nicht modales Dialogfeld `OnInitDialog` wird aufgerufen, wenn **erstellen** aufgerufen wird. Überschreiben Sie i. d. r. `OnInitDialog` um das Dialogfeld-Steuerelemente, z. B. das Festlegen des ersten Texts, der ein Bearbeitungsfeld zu initialisieren. Rufen Sie die `OnInitDialog` Member-Funktion der Basisklasse, `CDialog`, aus der `OnInitDialog` außer Kraft setzen.  
  
 Wenn Sie die Hintergrundfarbe des Dialogfelds (und von anderen Dialogfeldern in Ihrer Anwendung) festlegen möchten, finden Sie unter [Festlegen der Hintergrundfarbe des Dialogfelds](../mfc/setting-the-dialog-boxs-background-color.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)


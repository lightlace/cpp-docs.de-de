---
title: Typsicherer Zugriff auf Steuerelemente in einem Dialogfeld | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- Windows common controls [MFC], in dialog boxes
- safe access to dialog box controls
- dialog boxes [MFC], type-safe access to controls
- controls [MFC], accessing in dialog boxes
- type-safe access to dialog box controls
- MFC dialog boxes [MFC], type-safe access to controls
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a876be701b680de0559f123aaaaa68d4c006e41a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>Typsicherer Zugriff auf die Steuerelemente in einem Dialogfeld
Die Steuerelemente in einem Dialogfeld können die Schnittstellen von MFC-Steuerelementklassen wie `CListBox` und `CEdit` nutzen. Sie können ein Steuerelementobjekt erstellen und es an ein Dialogsteuerelement anhängen. Dann können Sie auf das Steuerelement über seine Klassenschnittstelle zugreifen und Memberfunktionen aufrufen, die für das Steuerelement ausgeführt werden sollen. Die hier beschriebenen Methoden bieten einen typsicheren Zugriff auf ein Steuerelement. Dies ist speziell für Steuerelemente wie Bearbeitungsfelder und Listenfelder nützlich.  
  
 Es gibt zwei Methoden, um eine Verbindung zwischen einem Steuerelement in einem Dialogfeld und einer C++-Steuerelement-Membervariable in einer von `CDialog` abgeleiteten Klasse herzustellen:  
  
-   [Ohne Code-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md)  
  
-   [Mit Code-Assistenten](../mfc/type-safe-access-to-controls-with-code-wizards.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)


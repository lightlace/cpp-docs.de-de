---
title: Typsicherer Zugriff auf Steuerelemente in einem Dialogfeld | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- Windows common controls [MFC], in dialog boxes
- safe access to dialog box controls
- dialog boxes [MFC], type-safe access to controls
- controls [MFC], accessing in dialog boxes
- type-safe access to dialog box controls
- MFC dialog boxes [MFC], type-safe access to controls
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b6005f34b28a634b36aad93186a34a8806b8033d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>Typsicherer Zugriff auf die Steuerelemente in einem Dialogfeld
Die Steuerelemente in einem Dialogfeld können die Schnittstellen von MFC-Steuerelementklassen wie `CListBox` und `CEdit` nutzen. Sie können ein Steuerelementobjekt erstellen und es an ein Dialogsteuerelement anhängen. Dann können Sie auf das Steuerelement über seine Klassenschnittstelle zugreifen und Memberfunktionen aufrufen, die für das Steuerelement ausgeführt werden sollen. Die hier beschriebenen Methoden bieten einen typsicheren Zugriff auf ein Steuerelement. Dies ist speziell für Steuerelemente wie Bearbeitungsfelder und Listenfelder nützlich.  
  
 Es gibt zwei Methoden, um eine Verbindung zwischen einem Steuerelement in einem Dialogfeld und einer C++-Steuerelement-Membervariable in einer von `CDialog` abgeleiteten Klasse herzustellen:  
  
-   [Ohne Code-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md)  
  
-   [Mit Code-Assistenten](../mfc/type-safe-access-to-controls-with-code-wizards.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)


---
title: Typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb861995c16411bb58e3051c5ffc78f75931ae8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>Typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten
Der erste Ansatz zum Erstellen Typsicherer Zugriff auf Steuerelemente verwendet eine Inline-Memberfunktion um den Rückgabetyp der Klasse umgewandelt `CWnd`des `GetDlgItem` Memberfunktion versucht, den entsprechenden C++-Steuerelementtyp, wie in diesem Beispiel:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]  
  
 Sie können diese Memberfunktion klicken Sie dann auf das Steuerelement in einer typsicheren Weise mit Code ähnlich dem folgenden verwenden:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Typsicherer Zugriff auf Steuerelemente in einem Dialogfeld](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [Typsicherer Zugriff auf Steuerelemente mit Code-Assistenten](../mfc/type-safe-access-to-controls-with-code-wizards.md)


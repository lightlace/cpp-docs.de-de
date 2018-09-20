---
title: Typsicherer Zugriff auf Steuerelemente in einem Dialogfeld | Microsoft-Dokumentation
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
ms.openlocfilehash: 3ed8a374c34eacc48e1d877e704fdc60a20f33d9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422713"
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>Typsicherer Zugriff auf die Steuerelemente in einem Dialogfeld

Die Steuerelemente in einem Dialogfeld können die Schnittstellen von MFC-Steuerelementklassen wie `CListBox` und `CEdit` nutzen. Sie können ein Steuerelementobjekt erstellen und es an ein Dialogsteuerelement anhängen. Dann können Sie auf das Steuerelement über seine Klassenschnittstelle zugreifen und Memberfunktionen aufrufen, die für das Steuerelement ausgeführt werden sollen. Die hier beschriebenen Methoden bieten einen typsicheren Zugriff auf ein Steuerelement. Dies ist speziell für Steuerelemente wie Bearbeitungsfelder und Listenfelder nützlich.

Es gibt zwei Methoden, um eine Verbindung zwischen einem Steuerelement in einem Dialogfeld und einer C++-Steuerelement-Membervariable in einer von `CDialog` abgeleiteten Klasse herzustellen:

- [Ohne Code-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md)

- [Mit Code-Assistenten](../mfc/type-safe-access-to-controls-with-code-wizards.md)

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)


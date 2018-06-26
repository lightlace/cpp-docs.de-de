---
title: 'MFC-ActiveX-Steuerelemente: Zurückgeben von Fehlercodes aus einer Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdcd18a80b430a0a8576effaaa46215dd5eb9600
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36927918"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC-ActiveX-Steuerelemente: Zurückgeben von Fehlercodes aus einer Methode
Dieser Artikel beschreibt, wie zum Zurückgeben von Fehlercodes aus einem ActiveX-Steuerelement-Methode.  
  
 Um anzugeben, dass innerhalb einer Methode ein Fehler aufgetreten ist, verwenden Sie die [ThrowError](../mfc/reference/colecontrol-class.md#throwerror) Memberfunktion, die einen SCODE (Statuscode) als Parameter annimmt. Sie können einen vordefinierten SCODE oder definieren ein eigenes.  
  
> [!NOTE]
>  `ThrowError` sollen nur als Mittel zum Zurückgeben von kein Fehlers aus einer Eigenschaft abzurufen oder festzulegen, verwendet werden-Funktion oder ein Automation-Methode. Dies sind die einzigen Fälle, in denen die passenden Ausnahmehandler werden auf dem Stapel vorhanden.  
  
 Hilfsfunktionen vorhanden, für die am häufigsten verwendeten SCODEs, z. B. vordefinierte [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), und [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
 Eine Liste der vordefinierten SCODEs und Anweisungen zum Definieren von benutzerdefinierten SCODEs, finden Sie im Abschnitt [Behandeln von Fehlern in ActiveX-Steuerelementen](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX-Steuerelemente: Weiterführende Themen.  
  
 Weitere Informationen zur Meldung von Ausnahmen in anderen Bereichen des Codes finden Sie unter [COleControl:: FireError](../mfc/reference/colecontrol-class.md#fireerror) und im Abschnitt [Behandeln von Fehlern in ActiveX-Steuerelementen](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX-Steuerelemente: Weiterführende Themen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)


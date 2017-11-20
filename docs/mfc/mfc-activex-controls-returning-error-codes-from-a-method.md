---
title: "MFC-ActiveX-Steuerelemente: Zurückgeben von Fehlercodes aus einer Methode | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 878d31d779d6722f25e9a3b53847cea25daac6e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC-ActiveX-Steuerelemente: Zurückgeben von Fehlercodes aus einer Methode
Dieser Artikel beschreibt, wie zum Zurückgeben von Fehlercodes aus einem ActiveX-Steuerelement-Methode.  
  
 Um anzugeben, dass innerhalb einer Methode ein Fehler aufgetreten ist, verwenden Sie die [ThrowError](../mfc/reference/colecontrol-class.md#throwerror) Member-Funktion akzeptiert eine `SCODE` (Statuscode) als Parameter. Sie können eine vordefinierte `SCODE` oder ein eigenes definieren.  
  
> [!NOTE]
>  `ThrowError`sollen nur als Mittel zum Zurückgeben von kein Fehlers aus einer Eigenschaft abzurufen oder festzulegen, verwendet werden-Funktion oder ein Automation-Methode. Dies sind die einzigen Fälle, in denen die passenden Ausnahmehandler werden auf dem Stapel vorhanden.  
  
 Hilfsfunktionen für die am häufigsten verwendeten vordefinierten vorhanden `SCODE`s, z. B. [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), und [COleControl:: SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
 Eine Liste der vordefinierten `SCODE`s und Anweisungen zum Definieren von benutzerdefinierten `SCODE`s, finden Sie im Abschnitt [Behandeln von Fehlern in ActiveX-Steuerelementen](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX-Steuerelemente: Weiterführende Themen.  
  
 Weitere Informationen zur Meldung von Ausnahmen in anderen Bereichen des Codes finden Sie unter [COleControl:: FireError](../mfc/reference/colecontrol-class.md#fireerror) und im Abschnitt [Behandeln von Fehlern in ActiveX-Steuerelementen](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX-Steuerelemente: Weiterführende Themen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)


---
title: Behandeln der TTN_NEEDTEXT-Benachrichtigung für QuickInfos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TTN_NEEDTEXT
dev_langs:
- C++
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5879082ddc23630e5ee497d8abf6b65873a2b6d4
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931963"
---
# <a name="handling-ttnneedtext-notification-for-tool-tips"></a>Behandeln der TTN_NEEDTEXT-Benachrichtigung für QuickInfos
Im Rahmen des [von QuickInfos](../mfc/enabling-tool-tips.md), behandeln Sie das **TTN_NEEDTEXT** Nachricht, indem Sie den folgenden Eintrag meldungszuordnung Ihres Besitzerfensters hinzufügen:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]  
  
 `memberFxn`  
 Die Memberfunktion aufgerufen werden, wenn diese Schaltfläche Text erforderlich ist.  
  
 Beachten Sie, dass die ID einer QuickInfo immer 0.  
  
 Deklarieren Sie die Handlerfunktion wird in der Klassendefinition wie folgt:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]  
  
 wobei kursiv Parameter sind:  
  
 `id`  
 Der Bezeichner des Steuerelements, das die Benachrichtigung gesendet. Nicht verwendet. Die Steuerelement-Id stammt aus dem **NMHDR** Struktur.  
  
 `pNMHDR`  
 Ein Zeiger auf die [NMTTDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760258) Struktur. Diese Struktur wird ebenfalls erläutert in weiteren [der TOOLTIPTEXT-Struktur](../mfc/tooltiptext-structure.md).  
  
 `pResult`  
 Ein Zeiger auf den Ergebniscode können Sie festlegen, bevor Sie zurückkehren. **TTN_NEEDTEXT** Handler können ignorieren die *pResult* Parameter.  
  
 Als Beispiel für eine Formularansicht Benachrichtigungshandler:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]  
  
 Rufen Sie `EnableToolTips` (dieses Fragment entnommen `OnInitDialog`):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)


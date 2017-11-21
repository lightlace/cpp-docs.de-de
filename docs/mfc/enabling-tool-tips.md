---
title: QuickInfos | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7c7e35dab6a94a01851b667ce4ab3dd58aa4bd8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="enabling-tool-tips"></a>Erstellen von QuickInfos
Sie können die Tool-Tipp-Unterstützung für die untergeordneten Steuerelemente von einem Fenster (z. B. die Steuerelemente auf einem Formular Ansichts- oder Dialogfeldobjekt) aktivieren.  
  
### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>So aktivieren Sie QuickInfos für die untergeordneten Steuerelemente eines Fensters  
  
1.  Rufen Sie `EnableToolTips` für das Fenster für die Sie QuickInfos bereitstellen möchten.  
  
2.  Geben Sie eine Zeichenfolge für jedes Steuerelement in Ihrer [TTN_NEEDTEXT-Benachrichtigung](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) Handler. Der Handler befindet sich in der meldungszuordnung des Fensters, das die untergeordneten Steuerelemente (z. B. die Form-Klasse) enthält. Dieser Handler sollten Aufrufen eine Funktion, die das Steuerelement identifiziert, und legt sie fest **PszText** , geben Sie den Text von der QuickInfo-Steuerelement verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)


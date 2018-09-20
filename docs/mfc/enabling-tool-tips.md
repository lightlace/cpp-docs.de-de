---
title: QuickInfos | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 968d31b49c6d2b2fe5a5f69e04f58f17de8df5a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440484"
---
# <a name="enabling-tool-tips"></a>Erstellen von QuickInfos

Sie können die QuickInfo-Unterstützung für Tools für die untergeordneten Steuerelemente eines Fensters (z. B. die Steuerelemente in einem Formular Ansichts- oder Dialogfeldobjekt) aktivieren.

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>QuickInfos für die untergeordneten Steuerelemente eines Fensters aktivieren

1. Rufen Sie `EnableToolTips` für das Fenster für die Sie QuickInfos bereitstellen möchten.

1. Geben Sie eine Zeichenfolge für jedes Steuerelement in Ihrer [TTN_NEEDTEXT-Benachrichtigung](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) Handler. Der Handler ist in der meldungszuordnung des Fensters, das die untergeordneten Steuerelemente (z. B. Ihrem Formular-Klasse) enthält. Dieser Handler sollten Aufrufen eine Funktion, die das Steuerelement identifiziert, und legt **PszText** zum Angeben des Texts, die von der QuickInfo-Steuerelement verwendet.

## <a name="see-also"></a>Siehe auch

[QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)


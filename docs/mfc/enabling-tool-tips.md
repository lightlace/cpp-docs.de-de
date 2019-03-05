---
title: Erstellen von QuickInfos
ms.date: 11/04/2016
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
ms.openlocfilehash: 892ed76ef7e021544505600110cd2569d6078312
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285944"
---
# <a name="enabling-tool-tips"></a>Erstellen von QuickInfos

Sie können die QuickInfo-Unterstützung für Tools für die untergeordneten Steuerelemente eines Fensters (z. B. die Steuerelemente in einem Formular Ansichts- oder Dialogfeldobjekt) aktivieren.

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>QuickInfos für die untergeordneten Steuerelemente eines Fensters aktivieren

1. Rufen Sie `EnableToolTips` für das Fenster für die Sie QuickInfos bereitstellen möchten.

1. Geben Sie eine Zeichenfolge für jedes Steuerelement in Ihrer [TTN_NEEDTEXT-Benachrichtigung](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) Handler. Der Handler ist in der meldungszuordnung des Fensters, das die untergeordneten Steuerelemente (z. B. Ihrem Formular-Klasse) enthält. Dieser Handler sollten Aufrufen eine Funktion, die das Steuerelement identifiziert, und legt **PszText** zum Angeben des Texts, die von der QuickInfo-Steuerelement verwendet.

## <a name="see-also"></a>Siehe auch

[QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

---
title: 'MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten'
ms.date: 09/12/2018
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
helpviewer_keywords:
- picture stock property pages [MFC]
- CLSID_CFontPropPage [MFC]
- color stock property pages [MFC]
- CLSID_CColorPropPage [MFC]
- fonts [MFC], ActiveX controls
- stock properties [MFC], stock property pages
- CLSID_CPicturePropPage [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
ms.openlocfilehash: b73a027422cfe9cbf03afece400c1b513cace151
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62239334"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten

Dieser Artikel beschreibt die vordefinierten Eigenschaftenseiten, die für ActiveX-Steuerelemente und deren Verwendung zur Verfügung.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Weitere Informationen zur Verwendung von Eigenschaftenseiten in einem ActiveX-Steuerelement finden Sie unter den folgenden Artikeln:

- [MFC-ActiveX-Steuerelemente: Eigenschaftenseiten](../mfc/mfc-activex-controls-property-pages.md)

- [MFC-ActiveX-Steuerelemente: Hinzufügen einer weiteren benutzerdefinierten Eigenschaftenseite](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

MFC bietet drei vordefinierten Eigenschaftenseiten für die Verwendung von ActiveX-Steuerelementen: `CLSID_CColorPropPage`, `CLSID_CFontPropPage`, und `CLSID_CPicturePropPage`. Diese Seiten wird eine Benutzeroberfläche für die vordefinierten Farbe, Schriftart und Bildeigenschaften, bzw. angezeigt.

Um diese Eigenschaftenseiten in einem Steuerelement zu integrieren, wird der Code, der des Steuerelements-Array von Eigenschaftenseiten-IDs initialisiert, deren IDs hinzugefügt. Im folgenden Beispiel befindet sich dieser Code, in der Implementierungsdatei des Steuerelements (. CPP), das Array für alle drei vordefinierten Eigenschaftenseiten und die Standardseite für die Eigenschaft initialisiert (mit dem Namen `CMyPropPage` in diesem Beispiel):

[!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

Beachten Sie, dass die Anzahl der Eigenschaftenseiten, in dem BEGIN_PROPPAGEIDS-Makro 4 ist. Dies stellt die Anzahl der Eigenschaftenseiten von ActiveX-Steuerelement unterstützt werden.

Nachdem diese Änderungen vorgenommen wurden, erstellen Sie Ihr Projekt neu. Das Steuerelement verfügt jetzt über die Eigenschaftenseiten für die Schriftart, Bild und Farbeigenschaften.

> [!NOTE]
>  Wenn die vordefinierten Eigenschaftenseiten Steuerelement können nicht zugegriffen werden, möglicherweise darauf zurückzuführen, bis die MFC-DLL (MFCxx.DLL) mit dem aktuellen Betriebssystem nicht ordnungsgemäß registriert wurde. Dies führt in der Regel installieren Sie Visual C++ unter einem Betriebssystem, die sich von dem derzeit ausgeführt.

> [!TIP]
>  Wenn die vordefinierten Eigenschaftenseiten nicht sichtbar sind (siehe vorherigen Hinweis), die DLL mit RegSvr32.exe über die Befehlszeile mit dem Namen der vollständige Pfad zur DLL registrieren.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Eigenschaften](../mfc/mfc-activex-controls-adding-stock-properties.md)

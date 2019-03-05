---
title: Verwenden von Bildlisten in einem Symbolleisten-Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: d027f7834c67ad0ed51d1b7fda5b2704972efe38
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57300790"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>Verwenden von Bildlisten in einem Symbolleisten-Steuerelement

Standardmäßig werden die von den Schaltflächen in einem Symbolleisten-Steuerelement verwendet Bilder als eine einzelne Bitmap gespeichert. Allerdings können Sie Bilder in einem Satz von Bildlisten speichern. Das Steuerelementobjekt Symbolleiste kann bis zu drei separate Bildlisten verwenden:

- Aktiviert die Bildliste enthält Bilder für Symbolleisten-Schaltflächen, die derzeit aktiviert sind.

- Deaktiviert die Bildliste enthält Bilder für Symbolleisten-Schaltflächen, die zurzeit deaktiviert sind.

- Markiert die Bildliste enthält Bilder für Symbolleisten-Schaltflächen, die derzeit ausgewählt sind. Diese Bildliste wird verwendet, nur dann, wenn die Symbolleiste die Formatvorlage TBSTYLE_FLAT verwendet.

Diese Bildlisten werden von dem Symbolleisten-Steuerelement verwendet, wenn Sie sie durch Zuordnen der `CToolBarCtrl` Objekt. Diese Zuordnung wird erreicht, indem Sie Aufrufe an [CToolBarCtrl:: SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist), [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist), und [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist).

MFC verwendet standardmäßig die `CToolBar` Klasse zum Implementieren von MFC-Anwendungssymbolleisten. Allerdings die `GetToolBarCtrl` Memberfunktion kann verwendet werden, die eingebettete abzurufenden `CToolBarCtrl` Objekt. Sie können dann Aufrufe an `CToolBarCtrl` Memberfunktionen, die das zurückgegebene Objekt verwenden.

Im folgende Beispiel wird diese Technik veranschaulicht, indem Sie einen aktivierten zuweisen (`m_ToolBarImages`) als auch deaktivierte (`m_ToolBarDisabledImages`) Bildliste an, eine `CToolBarCtrl` Objekt (`m_ToolBarCtrl`).

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
>  Der Bildliste ein, die die Toolbar-Objekt müssen es sich um dauerhafte Objekte sein. Aus diesem Grund sind sie häufig Datenmember einer MFC-Klasse. In diesem Beispiel ist die Hauptframe-Fensterklasse.

Sobald der Bildliste zugeordnet sind die `CToolBarCtrl` Objekt, das Framework automatisch die richtigen Schaltflächenbild angezeigt.

## <a name="see-also"></a>Siehe auch

[Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

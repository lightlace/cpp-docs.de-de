---
title: Verwenden von Bildlisten in einem Symbolleistensteuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3604de0b3b24b638e549c6823ea6c95036543c1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401770"
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


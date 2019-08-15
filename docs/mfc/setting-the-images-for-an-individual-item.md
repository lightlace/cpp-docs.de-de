---
title: Festlegen der Bilder für ein bestimmtes Element
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
ms.openlocfilehash: 177c06acfe665a43921b19407d9d357d4545e748
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511276"
---
# <a name="setting-the-images-for-an-individual-item"></a>Festlegen der Bilder für ein bestimmtes Element

Die unterschiedlichen Typen von Bildern, die vom erweiterten Kombinations Feld Element verwendet werden, werden durch die Werte in den Elementen *iImage*, *iSelectedImage*und *IOverlay* der [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) -Struktur bestimmt. Jeder Wert ist der Index eines Bilds in der zugeordneten Bildliste des Steuer Elements. Diese Member werden standardmäßig auf 0 festgelegt, sodass das Steuerelement kein Bild für das Element anzeigt. Wenn Sie Bilder für ein bestimmtes Element verwenden möchten, können Sie die Struktur entsprechend ändern, entweder beim Einfügen des Kombinations Feld Elements oder durch Ändern eines vorhandenen Kombinations Feld Elements.

## <a name="setting-the-image-for-a-new-item"></a>Festlegen des Bilds für ein neues Element

Wenn Sie ein neues Element einfügen, initialisieren Sie die Member *iImage*, *iSelectedImage*und *IOverlay* -Struktur mit den richtigen Werten, und fügen Sie das Element dann mit einem [CComboBoxEx:: InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem)-Befehl ein.

Im folgenden Beispiel wird ein neues erweitertes Kombinations Feld Element (`cbi`) in das erweiterte Kombinations Feld-Steuer`m_comboEx`Element () eingefügt, um Indizes für alle drei Bild Zustände bereitzustellen:

[!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]

## <a name="setting-the-image-for-an-existing-item"></a>Festlegen des Bilds für ein vorhandenes Element

Wenn Sie ein vorhandenes Element ändern, müssen Sie mit dem *Mask* -Member einer **COMBOBOXEXITEM** -Struktur arbeiten.

#### <a name="to-modify-an-existing-item-to-use-images"></a>So ändern Sie ein vorhandenes Element für die Verwendung von Images

1. Deklarieren Sie eine **COMBOBOXEXITEM** -Struktur, und legen Sie den *Mask* -Datenmember auf die Werte fest, die Sie ändern möchten.

1. Rufen Sie mithilfe dieser Struktur einen [CComboBoxEx:: GetItem](../mfc/reference/ccomboboxex-class.md#getitem)-Befehl auf.

1. Ändern Sie die Member *Mask*, *iImage*und *iSelectedImage* der neu zurückgegebenen Struktur unter Verwendung der entsprechenden Werte.

1. Rufen Sie [CComboBoxEx:: abtitem](../mfc/reference/ccomboboxex-class.md#setitem)auf, und übergeben Sie die geänderte Struktur.

Im folgenden Beispiel wird dieses Verfahren veranschaulicht, indem die ausgewählten und nicht ausgewählten Bilder des dritten erweiterten Kombinations Feld Elements ausgetauscht werden:

[!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]

## <a name="see-also"></a>Siehe auch

[Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

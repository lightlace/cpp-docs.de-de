---
title: Festlegen der Bilder für ein bestimmtes Element
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
ms.openlocfilehash: 61e152534dbea09fbca0af819b0847e82a1c4146
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512072"
---
# <a name="setting-the-images-for-an-individual-item"></a>Festlegen der Bilder für ein bestimmtes Element

Die verschiedenen Typen von Bildern, die von der erweiterten Kombinationsfeldelement werden nach den Werten in bestimmt die *iImage*, *iSelectedImage*, und *iOverlay* Mitglied der [ COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) Struktur. Jeder Wert ist der Index eines Bildes in der Liste zugeordnete Bild des Steuerelements. Standardmäßig werden diese Elemente auf 0 (null) festgelegt, verursacht das Steuerelement kein Bild für das Element an. Wenn Sie Images für ein bestimmtes Element verwenden möchten, können Sie die Struktur entsprechend entweder beim Einfügen des Kombinationsfelds oder durch Ändern einer vorhandenen ComboBoxItem-Steuerelement ändern.

## <a name="setting-the-image-for-a-new-item"></a>Festlegen des Bildformats für ein neues Element

Wenn Sie ein neues Element einfügen, initialisieren Sie die *iImage*, *iSelectedImage*, und *iOverlay* Strukturmember durch die entsprechenden Werte ein, und fügen Sie dann das Element mit einem Aufruf von [CComboBoxEx:: InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem).

Das folgende Beispiel fügt ein neue erweiterte Kombinationsfeldelement (`cbi`) in der erweiterten Kombinationsfeld-Steuerelement (`m_comboEx`), stellt Indizes für alle drei Zustände image:

[!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]

## <a name="setting-the-image-for-an-existing-item"></a>Festlegen des Bildformats für ein vorhandenes Element

Wenn Sie ein vorhandenes Element ändern, müssen Sie arbeiten mit der *Maske* Mitglied einer **COMBOBOXEXITEM** Struktur.

#### <a name="to-modify-an-existing-item-to-use-images"></a>So ändern Sie ein vorhandenes Element zum Verwenden von images

1. Deklarieren Sie eine **COMBOBOXEXITEM** Struktur, und legen Sie die *Maske* Datenmembers, der die Werte werden Sie ändern möchten.

1. Mit dieser Struktur stellen einen Aufruf von [:: GetItem](../mfc/reference/ccomboboxex-class.md#getitem).

1. Ändern der *Maske*, *iImage*, und *iSelectedImage* Member das neu zurückgegebene Struktur, die entsprechenden Werte verwendet.

1. Rufen Sie [CComboBoxEx::SetItem](../mfc/reference/ccomboboxex-class.md#setitem), und übergeben Sie die geänderten Struktur.

Das folgende Beispiel zeigt dieses Verfahren durch die ausgewählte und nicht ausgewählte Bilder der dritte erweiterte Kombinationsfeldelements austauschen:

[!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]

## <a name="see-also"></a>Siehe auch

[Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)


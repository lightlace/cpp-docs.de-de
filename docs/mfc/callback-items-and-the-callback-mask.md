---
title: Rückrufelemente und die Rückrufmaske
ms.date: 11/04/2016
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
ms.openlocfilehash: 5c326d8498ea297936254a8650f666103ea3c772
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509135"
---
# <a name="callback-items-and-the-callback-mask"></a>Rückrufelemente und die Rückrufmaske

Für alle Elemente speichert ein Listenansicht-Steuerelement in der Regel den Beschriftungs Text, den Bildlisten Index der Element Symbole und einen Satz von Bitflags für den Zustand des Elements. Sie können einzelne Elemente als Rückruf Elemente definieren, was nützlich ist, wenn Ihre Anwendung bereits einige der Informationen für ein Element speichert.

Ein Element wird als Rückruf Element definiert, indem geeignete Werte für die `pszText` -und-Member der `LVITEM` - `iImage` Struktur angegeben werden (siehe [CListCtrl:: GetItem](../mfc/reference/clistctrl-class.md#getitem)). Wenn die Anwendung den Text des Elements oder des unter Elements verwaltet, geben Sie den **LPSTR_TEXTCALLBACK** -Wert für `pszText` den Member an. Wenn die Anwendung das Symbol für das Element nachverfolgt, geben Sie den **I_IMAGECALLBACK** -Wert für `iImage` das Element an.

Zusätzlich zum Definieren von Rückruf Elementen können Sie auch die Rückruf Maske des Steuer Elements ändern. Bei dieser Maske handelt es sich um einen Satz von Bitflags, die die Element Zustände angeben, für die die Anwendung und nicht das Steuerelement die aktuellen Daten speichert. Die Rückruf Maske gilt für alle Elemente des Steuer Elements, im Gegensatz zur Rückruf Element Bezeichnung, die für ein bestimmtes Element gilt. Die Rückruf Maske ist standardmäßig 0 (null), was bedeutet, dass das Steuerelement alle Element Zustände nachverfolgt. Um dieses Standardverhalten zu ändern, initialisieren Sie die Maske mit einer beliebigen Kombination der folgenden Werte:

- **LVIS_CUT** Das Element ist für einen Ausschneide-und Einfügevorgang gekennzeichnet.

- **LVIS_DROPHILITED** Das Element wird als Drag & Drop-Ziel hervorgehoben.

- **LVIS_FOCUSED** Das Element hat den Fokus.

- **LVIS_SELECTED** Das Element ist ausgewählt.

- **LVIS_OVERLAYMASK** Die Anwendung speichert den Abbild Listen Index des aktuellen Überlagerungs Bilds für jedes Element.

- **LVIS_STATEIMAGEMASK** Die Anwendung speichert den Abbild Listen Index des aktuellen Status Bilds für jedes Element.

Weitere Informationen zum Abrufen und Festlegen dieser Maske finden Sie unter [CListCtrl:: GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask) und [CListCtrl:: SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask).

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

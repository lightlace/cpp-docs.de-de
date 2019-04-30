---
title: Rückrufelemente und die Rückrufmaske
ms.date: 11/04/2016
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
ms.openlocfilehash: 35967f128c6cc59bc9cea90da559b32c51fb38d1
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344284"
---
# <a name="callback-items-and-the-callback-mask"></a>Rückrufelemente und die Rückrufmaske

Für die einzelnen Elemente einem Listenansicht-Steuerelement in der Regel den Bezeichnungstext, der den Index des Bildes Liste von Symbolen für das Element, speichert, und ein Satz von Bit flags für den Zustand des Elements. Sie können einzelne Elemente als Rückrufelemente, definieren, die dies hilfreich ist, wenn die Anwendung bereits einige der Informationen für ein Element gespeichert werden.

Definieren Sie ein Element als ein Rückrufelement durch Angabe der entsprechenden Werte für die `pszText` und `iImage` Mitglied der **LV_ITEM** Struktur (finden Sie unter [CListCtrl:: GetItem](../mfc/reference/clistctrl-class.md#getitem)). Wenn die Anwendung die des Elements oder Unterelements Text verwaltet, geben Sie die **LPSTR_TEXTCALLBACK** Wert für die `pszText` Member. Wenn die Anwendung verfolgt das Symbol für das Element des, geben Sie die **I_IMAGECALLBACK** Wert für die `iImage` Member.

Zusätzlich zum Definieren von Rückrufelemente, können Sie auch die Rückrufmaske des Steuerelements ändern. Diese Maske ist ein Satz von Bitflags, die die Element-Zustände angeben, für die das Steuerelement, anstatt die Anwendung die aktuellen Daten speichert. Die Rückrufmaske gilt für alle Elemente des Steuerelements, im Gegensatz zu den Rückrufelement, die für ein bestimmtes Element gilt. Die Rückrufmaske ist 0 (null), wird standardmäßig, was bedeutet, dass das Steuerelement alle Element-Zustände verfolgt. Um dieses Standardverhalten ändern möchten, initialisieren Sie die Maske für eine beliebige Kombination der folgenden Werte ein:

- **LVIS_CUT** das Element ist für einen Ausschneiden und Einfügen-Vorgang markiert.

- **LVIS_DROPHILITED** das Element als Drag-Drop-Ziel hervorgehoben wird.

- **LVIS_FOCUSED** das Element den Fokus besitzt.

- **LVIS_SELECTED** das Element ist ausgewählt.

- **LVIS_OVERLAYMASK** die Anwendung speichert den Index des Bildes-Liste des aktuellen Bilds Overlay für jedes Element.

- **LVIS_STATEIMAGEMASK** die Anwendung speichert den Index des Bildes-Liste des aktuellen statusbilds für jedes Element.

Weitere Informationen zum Abrufen und Festlegen dieser Maske finden Sie unter [CListCtrl:: GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask) und [CListCtrl::SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask).

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

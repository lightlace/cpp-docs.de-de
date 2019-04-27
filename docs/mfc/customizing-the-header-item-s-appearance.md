---
title: Das Headerelement anpassen&#39;Darstellung
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
ms.openlocfilehash: 081260bd5c1cf6335d398a4fd773c9590dbc8030
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241580"
---
# <a name="customizing-the-header-item39s-appearance"></a>Das Headerelement anpassen&#39;Darstellung

Durch Festlegen der *DwStyle* Parameter bei der Erstellung von einem Kopfzeilen-Steuerelement ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md#create)), können Sie definieren, die Darstellung und Verhalten des Headers Elemente oder des Headersteuerelements selbst.

Hier ist eine Stichprobe der samt deren Zweck die Stile, die Sie festlegen können:

- Um ein Headerelement, das Aussehen einer Schaltfläche zu machen, verwenden die **HDS_BUTTONS** Stil.

   Verwenden Sie dieses Format, wenn Sie Aktionen als Reaktion auf Mausklicks auf ein Headerelement, wie z. B. das Sortieren von Daten nach einer bestimmten Spalte, wie in Microsoft Outlook ausführen möchten.

- Um die Headerelemente die Darstellung eines "hot Track" gewähren, wenn der Mauszeiger darüber bewegt, verwenden Sie die **HDS_HOTTRACK** Stil.

   Hot Track zeigt eine Gliederung 3D, übergibt der Zeiger auf ein Element in einer ansonsten flachen Leiste.

- Um anzugeben, dass das Kopfzeilen-Steuerelement ausgeblendet werden soll, verwenden Sie die **HDS_HIDDEN** Stil.

   Die **HDS_HIDDEN** Stil gibt an, dass das Kopfzeilen-Steuerelement als Datencontainer und nicht auf ein visuelles Steuerelement verwendet werden soll. Diese Art des Steuerelements wird nicht automatisch ausgeblendet, aber stattdessen beeinflusst das Verhalten von `CHeaderCtrl::Layout`. Der zurückgegebene Wert in der *cy* Mitglied der `WINDOWPOS` Struktur werden auf 0 (null) gibt an, dass das Steuerelement nicht für den Benutzer sichtbar sein soll.

Weitere Informationen zu diesen Eigenschaften finden Sie unter [Elemente](/windows/desktop/Controls/header-controls) im Windows SDK. Informationen zum Hinzufügen von Elementen zu einem Kopfzeilen-Steuerelement, finden Sie unter [Hinzufügen von Elementen zum Headersteuerelement](../mfc/adding-items-to-the-header-control.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

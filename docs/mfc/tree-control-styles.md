---
title: Struktursteuerelementstile
ms.date: 11/04/2016
f1_keywords:
- TVS_SINGLEEXPAND
- TVS_LINESATROOT
- TVS_HASBUTTONS
- TVS_NOTOOLTIPS
- TVS_HASLINES
helpviewer_keywords:
- TVS_LINESATROOT [MFC]
- styles [MFC], CTreeCtrl
- styles [MFC], tree control
- TVS_HASLINES
- TVS_SINGLEEXPAND
- CTreeCtrl class [MFC], styles
- TVS_EDITLABELS [MFC]
- TVS_NOTOOLTIPS [MFC]
- TVS_HASBUTTONS [MFC]
- tree controls [MFC], styles
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
ms.openlocfilehash: d03961c1c905689af5894897a59262c8f00e73fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181522"
---
# <a name="tree-control-styles"></a>Struktursteuerelementstile

Strukturansicht-Steuerelementen ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) Stile bestimmen Aspekte der Darstellung einer Struktur des Steuerelements. Die anfänglichen Formate wird festgelegt, wenn Sie die Strukturansicht-Steuerelement erstellen. Können Sie abrufen und ändern Sie die Stile, nach dem Erstellen der Strukturansicht mit der [GetWindowLong](/windows/desktop/api/winuser/nf-winuser-getwindowlonga) und [SetWindowLong](/windows/desktop/api/winuser/nf-winuser-setwindowlonga) Windows-Funktionen, die Angabe **GWL_STYLE** für die *nIndex* Parameter. Eine vollständige Liste der Formate, finden Sie unter [Ansicht Fenster Struktursteuerelementstile](/windows/desktop/Controls/tree-view-control-window-styles) im Windows SDK.

Die **Formate TVS_HASLINES** Stil verbessert die grafische Darstellung der Hierarchie für ein Strukturansicht-Steuerelement durch Zeichnen von Linien, die untergeordneten Elemente mit ihren entsprechenden übergeordneten Element verknüpft. Dieses Format wird nicht auf Elemente am Stamm der Hierarchie verknüpft. Zu diesem Zweck müssen Sie zum Kombinieren der **Formate TVS_HASLINES** und **TVS_LINESATROOT** Stile.

Der Benutzer kann erweitert oder durch Doppelklicken auf das übergeordnete Element eines übergeordneten Elements der Liste der untergeordneten Elemente zu reduzieren. Ein Strukturansicht-Steuerelement, die die **TVS_SINGLEEXPAND** Format bewirkt, dass die zum Erweitern ausgewählt wird und das Element wird deaktiviert, um Sie zu reduzieren. Wenn der Mauszeiger verwendet wird, um das ausgewählte Element Klick, und dieses Element wird geschlossen, wird dieses erweitert. Wenn das ausgewählte Element Single-geklickt wird, wenn er geöffnet ist, wird er reduziert werden.

Ein Strukturansicht-Steuerelement, die die **TVS_HASBUTTONS** Stil wird eine Schaltfläche auf der linken Seite jedes übergeordneten Elements hinzugefügt. Der Benutzer kann die Schaltfläche zum Erweitern oder reduzieren die untergeordneten Elemente als Alternative zur durch Doppelklicken auf das übergeordnete Element klicken. **TVS_HASBUTTONS** Elemente am Stamm der Hierarchie nicht Schaltflächen hinzu. Zu diesem Zweck müssen Sie kombinieren **Formate TVS_HASLINES**, **TVS_LINESATROOT**, und **TVS_HASBUTTONS**.

Die **TVS_EDITLABELS** Stil ermöglicht es dem Benutzer, die Bezeichnungen von Elementen der Strukturansicht-Steuerelement zu bearbeiten. Weitere Informationen zum Bearbeiten von Bezeichnungen finden Sie unter [Strukturansicht-Steuerelement Bezeichnungsbearbeitung](../mfc/tree-control-label-editing.md) weiter unten in diesem Thema.

Die **TVS_NOTOOLTIPS** -Stil deaktiviert die automatische QuickInfo-Funktion des Strukturansicht-Steuerelemente. Diese Funktion zeigt automatisch eine QuickInfo, die mit den Titel des Elements unter dem Cursor, wenn es sich bei der gesamte Titel derzeit nicht angezeigt wird.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

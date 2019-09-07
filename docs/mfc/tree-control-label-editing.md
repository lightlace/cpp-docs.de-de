---
title: Bearbeiten der Struktursteuerelement-Bezeichnung
ms.date: 11/04/2016
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
ms.openlocfilehash: 4b53d2c8e5a26a4dc37dfd7ae0710748bcd27bf6
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741230"
---
# <a name="tree-control-label-editing"></a>Bearbeiten der Struktursteuerelement-Bezeichnung

Der Benutzer kann die Bezeichnungen von Elementen in einem Struktur Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)), das den **TVS_EDITLABELS** -Stil hat, direkt bearbeiten. Der Benutzer beginnt mit der Bearbeitung, indem er auf die Bezeichnung des Elements klickt, das den Fokus besitzt. Eine Anwendung beginnt mit der Bearbeitung mithilfe der [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) -Member-Funktion. Das Struktur Steuerelement sendet die Benachrichtigung, wenn die Bearbeitung beginnt und abgebrochen oder abgeschlossen wird. Wenn die Bearbeitung abgeschlossen ist, müssen Sie ggf. die Bezeichnung des Elements aktualisieren.

Wenn die Bezeichnungs Bearbeitung beginnt, sendet ein Struktur Steuerelement eine [TVN_BEGINLABELEDIT](/windows/win32/Controls/tvn-beginlabeledit) -Benachrichtigungs Meldung. Wenn Sie diese Benachrichtigung verarbeiten, können Sie die Bearbeitung einiger Bezeichnungen zulassen und die Bearbeitung anderer Bezeichnungen verhindern. Wenn 0 zurückgegeben wird, wird die Bearbeitung ermöglicht, und das Zurückgeben von Null verhindert

Wenn die Bezeichnungs Bearbeitung abgebrochen oder abgeschlossen wird, sendet ein Struktur Steuerelement eine [TVN_ENDLABELEDIT](/windows/win32/Controls/tvn-endlabeledit) -Benachrichtigungs Meldung. Der *LPARAM* -Parameter ist die Adresse einer [NMTVDISPINFO](/windows/win32/api/commctrl/ns-commctrl-nmtvdispinfow) -Struktur. Das **Element Element** ist eine [tvitem](/windows/win32/api/commctrl/ns-commctrl-tvitemw) -Struktur, die das Element identifiziert und den bearbeiteten Text enthält. Sie sind dafür verantwortlich, die Bezeichnung des Elements ggf. nach der Validierung der bearbeiteten Zeichenfolge zu aktualisieren. Der *pszText* -Member `TV_ITEM` von ist 0, wenn die Bearbeitung abgebrochen wird.

Während der Bezeichnungs Bearbeitung können Sie in der Regel als Reaktion auf die [TVN_BEGINLABELEDIT](/windows/win32/Controls/tvn-beginlabeledit) -Benachrichtigungs Meldung einen Zeiger auf das Bearbeitungs Steuerelement erhalten, das für die Bezeichnungs Bearbeitung mithilfe der [geteditcontrol](../mfc/reference/ctreectrl-class.md#geteditcontrol) -Member-Funktion verwendet wird. Sie können die [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) -Member-Funktion des Edit-Steuer Elements aufrufen, um die Menge an Text einzuschränken, die ein Benutzer in das Bearbeitungs Steuerelement eingeben oder eine Unterklasse zum Abfangen und Verwerfen von ungültigen Zeichen Beachten Sie jedoch, dass das Bearbeitungs Steuerelement nur angezeigt wird, *nachdem* **TVN_BEGINLABELEDIT** gesendet wurde.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

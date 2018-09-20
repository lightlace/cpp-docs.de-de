---
title: Struktursteuerelement-Bezeichnung bearbeiten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99b3490e98ba9cf9640c4903d88064a7808c6494
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376576"
---
# <a name="tree-control-label-editing"></a>Bearbeiten der Struktursteuerelement-Bezeichnung

Der Benutzer die Bezeichnungen von Elementen in einem Strukturansicht-Steuerelement direkt bearbeiten kann ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)), bei dem die **TVS_EDITLABELS** Stil. Der Benutzer beginnt, bearbeiten, indem Sie auf die Bezeichnung des Elements, das den Fokus besitzt. Eine Anwendung beginnt mit der Bearbeitung mit der [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) Member-Funktion. Das Struktursteuerelement sendet die Benachrichtigung, wenn Bearbeitung beginnt, und wenn sie abgebrochen oder abgeschlossen ist. Wenn die Bearbeitung abgeschlossen ist, können Sie für die Aktualisierung der elementbezeichnung verantwortlich, bei Bedarf.

Wenn bezeichnungsbearbeitung beginnt, ein Strukturansicht-Steuerelement sendet eine [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit) Benachrichtigung. Verarbeiten diese Benachrichtigung, Sie können einige Bezeichnungen bearbeitet und anderer Bearbeitung verhindern. Zurückgeben von 0 ermöglicht das Bearbeiten und ungleich NULL zurückgegeben wird verhindert, dass es.

Bei der bezeichnungsbearbeitung abgebrochen oder abgeschlossen ist, sendet ein Strukturansicht-Steuerelement eine [TVN_ENDLABELEDIT](/windows/desktop/Controls/tvn-endlabeledit) Benachrichtigung. Die *lParam* Parameter ist die Adresse von einem [NMTVDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa) Struktur. Die **Element** Member ist ein [TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema) -Struktur, identifiziert das Element und den bearbeiteten Text enthält. Sie sind verantwortlich für die Aktualisierung der elementbezeichnung ggf. vielleicht nach der Überprüfung der bearbeiteten Zeichenfolge. Die *PszText* Mitglied `TV_ITEM` ist 0, wenn die Bearbeitung abgebrochen wird.

Beim Bearbeiten der Beschriftung in der Regel als Reaktion auf die [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit) -benachrichtigungsmeldung und erhalten Sie einen Zeiger auf das Bearbeitungssteuerelement zum Bearbeiten von Bezeichnungen mithilfe der [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) Member -Funktion. Sie können des Steuerelements zum Bearbeiten des Aufrufen [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) Memberfunktion versucht, der ein Benutzer eingeben kann Text oder Unterklasse Bearbeitungssteuerelement abfangen und verwerfen ungültige Zeichen begrenzt. Beachten Sie jedoch, dass das Bearbeitungssteuerelement nur angezeigt wird, *nach* **TVN_BEGINLABELEDIT** gesendet wird.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)


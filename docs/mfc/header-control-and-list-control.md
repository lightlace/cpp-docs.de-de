---
title: Headersteuerelement und Listensteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
ms.openlocfilehash: 934b54de3266138225087d5519af2be51972cf9d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240074"
---
# <a name="header-control-and-list-control"></a>Headersteuerelement und Listensteuerelement

In den meisten Fällen verwenden Sie das Kopfzeilen-Steuerelement, das in eingebettet ist eine [CListCtrl](../mfc/reference/clistctrl-class.md) oder [CListView](../mfc/reference/clistview-class.md) Objekt. Es gibt jedoch Situationen, in denen ein separates Headerobjekt Steuerelement wünschenswert sein, z. B. zum Bearbeiten von Daten, die in Spalten oder Zeilen angeordnet werden, einem [CView](../mfc/reference/cview-class.md)-abgeleitetes Objekt. In diesen Fällen benötigen Sie größere Kontrolle über die Darstellung und das Standardverhalten von einem eingebetteten Kopfzeilen-Steuerelement.

In den meisten Fällen, dass Sie einem Kopfzeilen-Steuerelement Standard bereitstellen möchten, ein Standardverhalten, das Sie verwenden möchten [CListCtrl](../mfc/reference/clistctrl-class.md) oder [CListView](../mfc/reference/clistview-class.md) stattdessen. Verwendung `CListCtrl` Wenn die Funktionalität von einem standardmäßigen Kopfzeilen-Steuerelement in einem Listenansicht-Steuerelement allgemeine eingebettet werden sollen. Verwendung [CListView](../mfc/reference/clistview-class.md) Wenn die Funktionalität von einem standardmäßigen Kopfzeilen-Steuerelement in ein Objekt eingebettet werden sollen.

> [!NOTE]
>  Diese Steuerelemente umfassen nur eine integrierte Kopfzeilen-Steuerelement, wenn das Listenansicht-Steuerelement erstellt wird, mit der **LVS_REPORT** Stil.

In den meisten Fällen kann die Darstellung von eingebetteten Headersteuerelements geändert werden, durch Ändern der Stile eines mit Listenansicht-Steuerelement. Darüber hinaus kann Informationen zu dem Kopfzeilen-Steuerelement über Memberfunktionen der übergeordneten Listenansicht-Steuerelement abgerufen werden. Allerdings wird für vollständige Kontrolle und -Zugriff, um die Attribute und-Stile eines eingebetteten Headersteuerelement, empfohlen, dass ein Zeiger auf das Headersteuerelement-Objekt abgerufen werden.

Das eingebettete Headersteuerelement-Objekt kann zugegriffen werden, entweder `CListCtrl` oder `CListView` mit einem Aufruf von der jeweiligen Klasse `GetHeaderCtrl` Member-Funktion. Der folgende Code veranschaulicht dies:

[!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Verwenden von Bildlisten in Headersteuerelementen](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

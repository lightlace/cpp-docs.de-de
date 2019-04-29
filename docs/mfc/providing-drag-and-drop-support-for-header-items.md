---
title: Bereitstellen von Drag &amp; Drop-Unterstützung für Headerelemente
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: f30ad029742a01280abda85cbd1a81104d01d8cd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297033"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Bereitstellen von Drag &amp; Drop-Unterstützung für Headerelemente

Drag & Drop-Unterstützung für Headerelemente geben an, um die HDS_DRAGDROP-Stil. Drag & Drop-Unterstützung für Headerelemente bietet dem Benutzer die Möglichkeit, die Headerelemente, die von einem Kopfzeilen-Steuerelement neu anzuordnen. Das Standardverhalten bietet eine halb transparente bilddarstellung des Headerelements, das gezogen wird, und einen visuellen Indikator, der die neue Position, wenn das Headerelement gelöscht wird.

Wie können gemeinsame Drag & Drop-Funktionalität, Sie das Standardverhalten für Drag & Drop erweitern, indem die HDN_BEGINDRAG und HDN_ENDDRAG handlingbenachrichtigungen. Sie können die Darstellung des Bilds ziehen Sie auch anpassen, durch Überschreiben der [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) Member-Funktion.

> [!NOTE]
>  Wenn Sie Drag & Drop-Unterstützung für eine eingebettete Kopfzeilen-Steuerelement in einem Listensteuerelement bereitstellen, finden Sie im Abschnitt "Extended Style" in der [Ändern der Stile von Listensteuerelementen](../mfc/changing-list-control-styles.md) Thema.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)

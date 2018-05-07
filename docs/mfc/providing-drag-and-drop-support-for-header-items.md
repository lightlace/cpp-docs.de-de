---
title: Bereitstellen von Drag-and-Drop-Unterstützung für Headerelemente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50cd19d4828269d0591afd0b46768e9917b96906
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Bereitstellen von Drag & Drop-Unterstützung für Headerelemente
Drag & Drop-Unterstützung für Headerelemente geben an, um die `HDS_DRAGDROP` Stil. Drag & Drop-Unterstützung für Headerelemente gewährt dem Benutzer die Möglichkeit, den Header-Elemente von einem Headersteuerelement neu anordnen. Standardmäßig enthält ein Bild halbtransparente ziehen Sie das Headerelement, das gezogen werden und ein visueller Indikator, der die neue Position, wenn das Headerelement gelöscht wird.  
  
 Mit allgemeinen Drag-and-Drop-Funktionen, die Drag-and-Drop-Standardverhalten durch Behandeln erweitern können die **HDN_BEGINDRAG** und **HDN_ENDDRAG** Benachrichtigungen. Sie können die Darstellung des Bilds ziehen Sie auch anpassen, durch Überschreiben der [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) Memberfunktion.  
  
> [!NOTE]
>  Wenn Sie Drag & Drop-Unterstützung für ein eingebettetes Headersteuerelement in einem Listensteuerelement bereitstellen, finden Sie im Abschnitt "Erweiterte Formate" in der [Ändern der Stile von Listensteuerelementen](../mfc/changing-list-control-styles.md) Thema.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)


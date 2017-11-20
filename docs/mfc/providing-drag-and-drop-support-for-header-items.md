---
title: "Bereitstellen von Drag-and-Drop-Unterstützung für Headerelemente | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a6f9d305786fa54231deae3dcd65624ba39875e0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Bereitstellen von Drag & Drop-Unterstützung für Headerelemente
Drag & Drop-Unterstützung für Headerelemente geben an, um die `HDS_DRAGDROP` Stil. Drag & Drop-Unterstützung für Headerelemente gewährt dem Benutzer die Möglichkeit, den Header-Elemente von einem Headersteuerelement neu anordnen. Standardmäßig enthält ein Bild halbtransparente ziehen Sie das Headerelement, das gezogen werden und ein visueller Indikator, der die neue Position, wenn das Headerelement gelöscht wird.  
  
 Mit allgemeinen Drag-and-Drop-Funktionen, die Drag-and-Drop-Standardverhalten durch Behandeln erweitern können die **HDN_BEGINDRAG** und **HDN_ENDDRAG** Benachrichtigungen. Sie können die Darstellung des Bilds ziehen Sie auch anpassen, durch Überschreiben der [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) Memberfunktion.  
  
> [!NOTE]
>  Wenn Sie Drag & Drop-Unterstützung für ein eingebettetes Headersteuerelement in einem Listensteuerelement bereitstellen, finden Sie im Abschnitt "Erweiterte Formate" in der [Ändern der Stile von Listensteuerelementen](../mfc/changing-list-control-styles.md) Thema.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)


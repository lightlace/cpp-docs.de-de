---
title: Übersicht über die Elementzustände des struktursteuerung-Steuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bc62308642492aa00a139fb15cc9e6cdcfc3247
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-item-states-overview"></a>Übersicht über Elementzustände des Struktursteuerung-Steuerelements
Jedes Element in einem Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) dem aktuellen Status. Beispielsweise kann ein Element, deaktiviert, erweiterten usw. ausgewählt werden. Meistens, legt das Strukturansicht-Steuerelement automatisch ein Elementstatus entsprechend Benutzeraktionen, wie z. B. die Auswahl eines Elements fest. Sie können auch den Zustand eines Elements festlegen, mit der [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) Memberfunktion und rufen Sie den aktuellen Status eines Elements mit dem [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) Memberfunktion. Eine vollständige Liste der Element-Zustände, finden Sie unter [Strukturansicht Steuerelement Konstanten](http://msdn.microsoft.com/library/windows/desktop/bb759985) im Windows SDK.  
  
 Aktuellen Status des Elements wird angegeben, indem die `nState` Parameter. Ein Strukturansicht-Steuerelement kann den Zustand eines Elements eine Benutzeraktion, wie Sie das Element auswählen oder Festlegen des Fokus auf das Element entsprechend ändern. Darüber hinaus kann eine Anwendung den Zustand eines Elements zu deaktivieren oder Ausblenden des Elements oder die Angabe von Overlay Bild- oder statusbilds ändern.  
  
 Wenn Sie angeben, oder ändern den Zustand eines Elements, das `nStateMask` Parameter gibt an, welchen Status bits festgelegt wird, und die `nState` Parameter enthält die neuen Werte für jene Bits. Im folgende Beispiel ändert z. B. den aktuellen Status eines übergeordneten Elements (gemäß `hParentItem`) in eine `CTreeCtrl` Objekt (`m_treeCtrl`) zu **TVIS_EXPANDPARTIAL geändert**:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]  
  
 Ein weiteres Beispiel für Änderung des Zustands wäre ein Elementbild Overlay festgelegt. Um dies zu erreichen `nStateMask` umfasst die `TVIS_OVERLAYMASK` Wert und `nState` muss den einsbasierten Index verschoben wird, wie das Overlay-Bild acht Bits mit Links enthalten die [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) Makro. Der Index kann 0 kein Overlaybild an. Das Overlay-Image muss wurde zur Liste hinzugefügt haben des Strukturansicht-Steuerelements von Overlaybildern durch einen vorherigen Aufruf der [CImageList:: SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) Funktion. Die Funktion gibt den einsbasierten Index des Bilds hinzufügen. Dies ist der Index verwendet, mit der **INDEXTOOVERLAYMASK** Makro. Ein Strukturansicht-Steuerelement kann bis zu vier Overlay-Images sind.  
  
 Festzulegende statusbilds für ein Element, `nStateMask` umfasst die `TVIS_STATEIMAGEMASK` Wert und `nState` muss den einsbasierten Index des statusbilds verschoben wird, wie 12 Bits mit Links enthalten die [INDEXTOSTATEIMAGEMASK](http://msdn.microsoft.com/library/windows/desktop/bb775597) Makro. Der Index kann 0 keine statusbilds an. Weitere Informationen zu Overlay gespeichert und Status Bildern finden Sie unter [Struktur Control Lists, Image](../mfc/tree-control-image-lists.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)


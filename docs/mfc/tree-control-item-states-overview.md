---
title: "&#220;bersicht &#252;ber Elementzust&#228;nde des Struktursteuerung-Steuerelements"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl-Klasse, Elementzustände"
  - "Zustände, CTreeCtrl-Elemente"
  - "Struktursteuerelemente, Übersicht über Elementzustände"
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
caps.latest.revision: 14
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;bersicht &#252;ber Elementzust&#228;nde des Struktursteuerung-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jedes Element in einem der Strukturansicht \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) verfügt über einen aktuellen Zustand.  Beispielsweise kann ein Element ausgewählt werden, deaktiviert wurde, erweitert, u. a.  In den meisten Fällen legt das Struktursteuerelement automatisch den Zustand eines Elements fest, um Benutzeraktionen, wie Auswahl eines Elements darzustellen.  Sie können jedoch den Zustand eines Elements, indem Sie die Memberfunktion [SetItemState](../Topic/CTreeCtrl::SetItemState.md) festlegen, auch verwenden und den aktuellen Zustand eines Elements abrufen, indem Sie die Memberfunktion [GetItemState](../Topic/CTreeCtrl::GetItemState.md) verwenden.  Eine vollständige Liste von Elementzuständen, finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Strukturansicht\-Steuerelement\-Konstanten](http://msdn.microsoft.com/library/windows/desktop/bb759985).  
  
 Der aktuelle Zustand eines Elements durch den Parameter `nState` angegeben.  Eine Strukturansicht könnte den Zustand eines Elements, um Benutzeraktionen, z Auswahl des Elements oder Festlegen des Fokus auf das Element an.  Außerdem könnte eine Anwendung den Zustand eines Elements, um das Element zu deaktivieren oder auszublenden oder einem Overlaybild oder Zustandsbild anzugeben.  
  
 Wenn Sie den Zustand eines Elements angeben oder ändern, gibt der Parameter `nStateMask` an, die Bits anfordern, um festzulegen, und der `nState`\-Parameter enthält die neuen Werte für diese Bits.  Beispielsweise wird im folgenden Beispiel den aktuellen Zustand eines übergeordneten Elements \(angegeben durch `hParentItem`\) in einem `CTreeCtrl`\-Objekt \(`m_treeCtrl`\) zu **TVIS\_EXPANDPARTIAL**:  
  
 [!CODE [NVC_MFCControlLadenDialog#71](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#71)]  
  
 Ein weiteres Beispiel für das Ändern des Zustands würde, Overlaybild eines Elements festzulegen sein.  Um dies zu erreichen, muss `nStateMask` den Wert `TVIS_OVERLAYMASK` enthalten, und `nState` muss den mit Eins beginnenden Index des Overlaybilds einschließen, das verschoben wird ließ acht Bits mit dem Makro [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) verwendet.  Der Index darf 0, um keinen Overlaybilds anzugeben.  Das Overlaybild muss der Liste des Strukturansicht\-Steuerelements von Overlaybildern bei einem vorherigen Aufruf der [CImageList::SetOverlayImage](../Topic/CImageList::SetOverlayImage.md)\-Funktion hinzugefügt worden sein.  Die Funktion gibt den mit Eins beginnenden Index des Bildes, der hinzugefügt; Dies ist der Index, der mit dem Makro **INDEXTOOVERLAYMASK** verwendet wird.  Eine Strukturansicht kann bis vier bedeckte Bilder enthalten.  
  
 Um Zustandsbild eines Elements festzulegen, muss `nStateMask` den Wert `TVIS_STATEIMAGEMASK` enthalten, und `nState` muss den mit Eins beginnenden Index des Zustands einschließen, der das Bild, das verschoben wurde 12 Bits können mit dem [INDEXTOSTATEIMAGEMASK](http://msdn.microsoft.com/library/windows/desktop/bb775597)\-Makro.  Der Index darf 0, um keinen Zustandsbilds anzugeben.  Weitere Informationen über Overlay\- und Zustandsbilder, finden Sie unter [Strukturansicht\-Steuerelement\-Bildlisten](../mfc/tree-control-image-lists.md).  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
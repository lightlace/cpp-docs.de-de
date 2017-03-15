---
title: "Verwenden von Bildlisten in einem erweiterten Kombinationsfeld-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Erweiterte Kombinationsfelder, Bilder"
  - "Bilderlisten [C++], Kombinationsfelder"
  - "Bilder [C++], Kombinationsfeldelemente"
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verwenden von Bildlisten in einem erweiterten Kombinationsfeld-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Hauptfeature von erweiterten Kombinationsfeld\-Steuerelementen ist die Fähigkeit, Bilder der einer Bildliste mit einzelnen Elementen in einem Kombinationsfeld\-Steuerelement zuzuordnen.  Jedes Element ist in der Lage, drei verschiedenen Bilder anzuzeigen: ein für den Auswahlzustand, eines für seinen nicht ausgewählten Zustand und eine dritte für ein Overlaybild.  
  
 In der folgenden Prozedur ordnet einer Bildliste einem erweiterten Kombinationsfeld\-Steuerelement zu:  
  
### So einer Bildliste einem erweiterten Kombinationsfeld\-Steuerelement zuordnen  
  
1.  Erstellen Sie eine neue Bildliste \(oder verwenden Sie ein vorhandenes Bildlistenobjekt\), mithilfe des [CImageList](../mfc/reference/cimagelist-class.md)\-Konstruktors und Speichern des resultierenden Zeigers.  
  
2.  Initialisieren Sie das neue Bildlistenobjekt, indem Sie [CImageList::Create](../Topic/CImageList::Create.md) aufrufen.  Der folgende Code ist ein Beispiel dieses Aufrufs.  
  
     [!CODE [NVC_MFCControlLadenDialog#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#10)]  
  
3.  Fügen Sie optionale Bilder für jeden Zustand hinzu: aktiviert oder deaktiviert und ein Overlay.  Der folgende Code fügt drei vordefinierte Bilder hinzu.  
  
     [!CODE [NVC_MFCControlLadenDialog#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#11)]  
  
4.  Ordnen Sie der Bildliste mit dem Steuerelement mit einem Aufruf von [CComboBoxEx::SetImageList](../Topic/CComboBoxEx::SetImageList.md).  
  
 Sobald die Bildliste dem Steuerelement zugeordnet wurde, können Sie den Bildern einzeln angeben, die jedes Element für die drei möglichen Zustände verwendet.  Weitere Informationen finden Sie unter [Festlegen der Bilder für ein einzelnes Element](../mfc/setting-the-images-for-an-individual-item.md).  
  
## Siehe auch  
 [Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
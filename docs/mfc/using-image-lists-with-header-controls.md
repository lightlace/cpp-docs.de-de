---
title: "Verwenden von Bildlisten in Headersteuerelementen"
ms.custom: na
ms.date: "12/03/2016"
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
  - "CHeaderCtrl-Klasse, Bilderlisten"
  - "Headersteuerelemente, Bilderlisten"
  - "Bilderlisten [C++], Headersteuerelemente"
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von Bildlisten in Headersteuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Kopfzeilenelemente haben die Möglichkeit, ein Bild innerhalb eines Kopfzeilenelements anzuzeigen.  Dieses Bild gespeichert, in einer entsprechenden Bildliste, ist 16 x 16 Pixel und hat dieselben Merkmale wie der Symbolbilder, die in einem Listenansicht\-Steuerelement verwendet werden.  Um dieses Verhalten erfolgreich zu implementieren, müssen Sie die Bildliste zuerst erstellen und initialisieren, ordnen die Liste mit dem Header\-Steuerelement zu und ändern dann die Attribute des Kopfzeilenelements das Bild anzeigt.  
  
 Die folgende Prozedur veranschaulicht die Details, mithilfe eines Zeigers auf einen Header\-Steuerelement \(`m_pHdrCtrl`\) und eines Zeigers auf einer Bildliste \(`m_pHdrImages`\).  
  
### Um ein Bild in einem Headerelement anzeigen  
  
1.  Erstellen Sie eine neue Bildliste \(oder verwenden Sie ein vorhandenes Bildlistenobjekt\), mithilfe des [CImageList](../mfc/reference/cimagelist-class.md)\-Konstruktors und den resultierenden Zeiger speichern.  
  
2.  Initialisieren Sie das neue Bildlistenobjekt, indem Sie [CImageList::Create](../Topic/CImageList::Create.md) aufrufen.  Der folgende Code ist ein Beispiel dieses Aufrufs.  
  
     [!CODE [NVC_MFCControlLadenDialog#15](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#15)]  
  
3.  Fügen Sie den Bildern für jedes Headerelement hinzu.  Der folgende Code fügt zwei vordefinierte Bilder hinzu.  
  
     [!CODE [NVC_MFCControlLadenDialog#16](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#16)]  
  
4.  Ordnen Sie der Bildliste mit dem Header\-Steuerelement mit einem Aufruf von [CHeaderCtrl::SetImageList](../Topic/CHeaderCtrl::SetImageList.md).  
  
5.  Ändern Sie HeaderItem, um ein Bild aus der zugeordneten Bildliste anzuzeigen.  Im folgenden Beispiel wird das erste Bild, einer `m_phdrImages`, zum ersten Headerelement, `m_pHdrCtrl` zu.  
  
     [!CODE [NVC_MFCControlLadenDialog#17](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#17)]  
  
 Ausführliche Informationen über die verwendeten Parameterwerte, finden Sie entsprechende [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) nach.  
  
> [!NOTE]
>  Es ist möglich, mehrere Steuerelemente mithilfe derselben Bildliste zu haben.  Bei einem Standardlistenansicht\-steuerelement, könnte dies Bildlisten \(von Bildern geben mit 16 x 16 Pixeln\) verwendet durch kleine Symbolansicht eines Listenansicht\-Steuerelements und die Kopfzeilenelemente des Listenansicht\-Steuerelements.  
  
## Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)
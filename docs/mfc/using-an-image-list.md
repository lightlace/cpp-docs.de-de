---
title: "Verwenden einer Bildliste"
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
  - "CImageList-Klasse, Verwenden"
  - "Bilderlisten [C++]"
  - "Listen [C++], Bild"
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden einer Bildliste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typische Verwendungen einer Bildliste entspricht dem Muster unten:  
  
-   Erstellen Sie ein [CImageList](../mfc/reference/cimagelist-class.md)\-Objekt und rufen Sie eine der Überladungen seiner [Erstellen](../Topic/CImageList::Create.md)\-Funktion auf, um einer Bildliste zu erstellen und auf das Objekt `CImageList` anzufügen.  
  
-   Wenn Sie keine Bilder hinzugefügt haben, als Sie die Bildliste erstellt haben, fügen Sie der Bildliste Bilder hinzu, indem Sie die [Hinzufügen](../Topic/CImageList::Add.md) oder [Lesen](../Topic/CImageList::Read.md)\-Memberfunktion aufrufen.  
  
-   Ordnen Sie der Bildliste einem Steuerelement an, indem Sie die entsprechende Memberfunktion dieses Steuerelements oder Bildern Videofunktionen aus der Bildliste sich mithilfe der Memberfunktion [Zeichnen](../Topic/CImageList::Draw.md) der Bildliste aufrufen.  
  
-   Lassen Sie möglicherweise dem Benutzer, ein Bild, mithilfe der integrierten Unterstützung der Bildliste für das Ziehen zu ziehen.  
  
> [!NOTE]
>  Wenn die Bildliste mit dem Operator **neu** erstellt wurde, müssen Sie das `CImageList`\-Objekt zerstört, wenn Sie damit fertig sind.  
  
## Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
---
title: "Using the RichEdit 1.0 Control with MFC"
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
  - "C++"
helpviewer_keywords: 
  - "RichEdit 1.0 control"
  - "rich edit controls, RichEdit 1.0"
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Using the RichEdit 1.0 Control with MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zur Verwendung eines RichEdit\-Steuerelements müssen Sie zunächst [AfxInitRichEdit2](../Topic/AfxInitRichEdit2.md) aufrufen, um das RichEdit 2.0\-Steuerelement \(**RICHED20.DLL**\) zu laden, oder [AfxInitRichEdit](../Topic/AfxInitRichEdit.md), um das ältere RichEdit 1.0\-Steuerelement \(**RICHED32.DLL**\) zu laden.  
  
 Sie können auch die aktuelle [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\-Klasse mit dem älteren RichEdit 1.0\-Steuerelement verwenden, **CRichEditCtrl** wurde jedoch ausschließlich zur Unterstützung des RichEdit 2.0\-Steuerelements entwickelt.  Da die RichEdit 1.0\- und RichEdit 2.0\-Steuerelemente große Ähnlichkeit aufweisen, sind die meisten Methoden funktionsfähig. Sie sollten jedoch beachten, dass 1.0\- und 2.0\-Steuerelemente einige Unterschiede aufweisen, die bewirken, dass einige Methoden gar nicht oder falsch ausgeführt werden.  
  
## Anforderungen  
 MFC  
  
## Siehe auch  
 [Troubleshooting the Dialog Editor](../mfc/troubleshooting-the-dialog-editor.md)   
 [Dialog Editor](../mfc/dialog-editor.md)
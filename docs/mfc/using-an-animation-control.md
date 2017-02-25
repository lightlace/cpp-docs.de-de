---
title: "Verwenden eines Animationssteuerelements | Microsoft Docs"
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
  - "Animationssteuerungselemente [C++]"
  - "CAnimateCtrl-Klasse, Animationssteuerungselemente"
  - "Steuerelemente [MFC], Animation"
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Verwenden eines Animationssteuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typische Verwendung eines Animationssteuerelements entspricht dem Muster unten:  
  
-   Das Steuerelement wird erstellt.  Wenn das Steuerelement in einer Dialogfeldvorlage angegeben wird, ist Erstellung automatisch, wenn das Dialogfeld erstellt wird. \(Sie sollten [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) einen Member in der Dialogfeldklasse haben, die z Animationssteuerung entspricht.\) Alternativ können Sie die Memberfunktion [Erstellen](../Topic/CAnimateCtrl::Create.md) verwenden, um das Steuerelement als untergeordnetes Fenster eines jeden Fensters zu erstellen.  
  
-   Laden eines AVI\-Klipp in das Animationssteuerung, indem Sie die Memberfunktion [Öffnen](../Topic/CAnimateCtrl::Open.md) aufrufen.  Wenn das Animationssteuerung in einem Dialogfeld ist, ist ein gut, um dazu in der [OnInitDialog](../Topic/CDialog::OnInitDialog.md)\-Funktion der Dialogfeldklasse.  
  
-   Geben Sie dem Klipp erneut, indem Sie die Memberfunktion [Wiedergeben](../Topic/CAnimateCtrl::Play.md) aufrufen.  Wenn das Animationssteuerung in einem Dialogfeld ist, ist ein gut, um dazu in der **OnInitDialog** \-Funktion der Dialogfeldklasse.  **Wiedergeben** aufzurufen ist nicht erforderlich, wenn das Animationssteuerung den festgelegten `ACS_AUTOPLAY` Format hat.  
  
-   Wenn Sie Teile des Klipps anzeigen bzw. Frames durch Frames wiedergeben möchten, verwenden Sie die `Seek`\-Memberfunktion.  Um einen Klipp beendet der wiedergegeben wird, verwenden Sie die `Stop`\-Memberfunktion.  
  
-   Wenn Sie das Steuerelement sofort zerstören werden, entfernen Sie den Klipp aus dem Speicher, indem Sie die **Schließen**\-Memberfunktion aufrufen.  
  
-   Wenn das Animationssteuerung in einem Dialogfeld ist, werden diese und das `CAnimateCtrl`\-Objekt automatisch zerstört.  Falls nicht, müssen Sie sicherstellen, dass das Steuerelement und das `CAnimateCtrl`\-Objekt ordnungsgemäß gelöscht werden.  Das Löschen des Steuerelements stellt automatisch den AVI\-Klipp.  
  
## Siehe auch  
 [Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
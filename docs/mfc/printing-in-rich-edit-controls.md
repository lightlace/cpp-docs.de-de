---
title: "Drucken mit RichEdit-Steuerelementen"
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
  - "CRichEditCtrl-Klasse, Drucken"
  - "Drucken [MFC], CRichEditCtrl"
  - "Rich-Edit-Steuerelemente, Drucken"
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Drucken mit RichEdit-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können ein Rich\-Edit\-Steuerelement \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) mitteilen um die Ausgabe für ein bestimmtes Gerät, wie einen Drucker zu rendern.  Sie können dem Ausgabegerät auch angeben, das für Formate eines Rich\-Edit\-Steuerelements Text sein.  
  
 Um Teil des Inhalts eines Rich\-Edit\-Steuerelements für ein bestimmtes Gerät zu formatieren, können Sie die Memberfunktion [FormatRange](../Topic/CRichEditCtrl::FormatRange.md) verwenden.  Die [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911)\-Struktur, die dieser Funktion verwendet wird, gibt den Textbereich an, um zu formatieren sowie Gerätekontext \(DC\) für das Zielgerät.  
  
 Nachdem Sie Text für ein Ausgabegerät formatiert haben, können Sie die Ausgabe im Gerät senden, indem Sie die Memberfunktion [DisplayBand](../Topic/CRichEditCtrl::DisplayBand.md) verwenden.  Durch wiederholt mit `FormatRange` und `DisplayBand`, kann eine Anwendung, die gedruckt, der Inhalt eines Rich\-Edit\-Steuerelements Streifenbildung implementieren. \(Streifenbildung ist Division der Ausgabe in kleinere Teile an \(siehe folgendes.\)  
  
 Sie können die [SetTargetDevice](../Topic/CRichEditCtrl::SetTargetDevice.md)\-Memberfunktion verwenden, um dem Zielgerät anzugeben, für das Rich\-Edit\-Steuerelements Formate eines Text sein.  Diese Funktion ist für Formatierung WYSIWYG \(What You See Is What You Get\) nützlich, in der eine Anwendung Text mithilfe der Schriftartmetrik des Standarddruckers anstelle des Bildschirms positioniert.  
  
## Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
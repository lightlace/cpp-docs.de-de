---
title: "Verwenden eines Standardsteuerelements als untergeordnetes Fenster"
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
  - "Untergeordnete Fenster, Allgemeine Steuerelemente als"
  - "Allgemeine Steuerelemente [C++], Untergeordnete Fenster"
  - "Steuerelemente [MFC], Verwenden als untergeordnete Fenster"
  - "Fenster [C++], Allgemeine Steuerelemente als"
  - "Allgemeine Windows-Steuerelemente [C++], Untergeordnete Fenster"
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden eines Standardsteuerelements als untergeordnetes Fenster
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Alle der allgemeinen Windows\-Steuerelemente können als untergeordnetes Fenster eines beliebigen anderen Fensters verwendet werden.  Die folgende Prozedur beschreibt, wie eine sehr häufig vorkommende Steuerelement dynamisch erstellt und dann damit arbeitet.  
  
### So eine freigegebene Steuerelemente als untergeordnetes Fenster verwenden  
  
1.  Definieren Sie das Steuerelement in der entsprechenden Klasse oder im Handler.  
  
2.  Verwenden Sie die Überschreibung des Steuerelements der Methode [CWnd::Create](../Topic/CWnd::Create.md), um das Windows\-Steuerelement zu erstellen.  
  
3.  Nachdem das Steuerelement erstellt wurde \(noch im `OnCreate`\-Handler, wenn Sie das Steuerelement unterordnen\), können Sie das Steuerelement mithilfe ihrer Memberfunktionen bearbeiten.  Siehe die Beschreibungen der einzelnen Steuerelemente in der [Steuerelemente](../mfc/controls-mfc.md) für Informationen über Methoden.  
  
4.  Wenn Sie mit dem Steuerelement haben, dem [CWnd::DestroyWindow](../Topic/CWnd::DestroyWindow.md), das Steuerelement zu zerstören.  
  
## Siehe auch  
 [Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
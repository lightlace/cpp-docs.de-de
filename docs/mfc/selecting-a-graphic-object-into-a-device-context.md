---
title: "Ausw&#228;hlen eines Grafikobjekts f&#252;r einen Ger&#228;tekontext"
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
  - "Gerätekontexte, Grafikobjekte"
  - "Gerätekontexte, Auswählen von Grafikobjekten in"
  - "GDI-Objekte [C++], Gerätekontexte"
  - "Grafikobjekte, Auswählen im Gerätekontext"
  - "Lebensdauer, Grafikobjekte"
  - "SelectObject-Methode"
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Ausw&#228;hlen eines Grafikobjekts f&#252;r einen Ger&#228;tekontext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die Anwendung von Grafikobjekten im Gerätekontext eines Fensters zu.  Nachdem Sie [erstellen Sie ein Zeichnungsobjekt](../mfc/one-stage-and-two-stage-construction-of-objects.md), Sie es in den Gerätekontext anstelle des Standardobjekts auswählen müssen, die dort gespeichert wird:  
  
 [!CODE [NVC_MFCDocViewSDI#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocViewSDI#7)]  
  
## Lebensdauer von Grafikobjekten  
 Das Grafikobjekt, das vom [SelectObject](../Topic/CDC::SelectObject.md) zurückgegeben wird, ist "temporär." Das bedeutet, wird durch die [OnIdle](../Topic/CWinApp::OnIdle.md)\-Memberfunktion der Klasse `CWinApp` gelöscht beim nächsten Mal, wenn das Programm Leerlaufzeit abruft.  Solange Sie das Objekt verwenden, das von `SelectObject` in einer einzelnen Funktion zurückgegeben wird, ohne der Hauptnachrichtenschleife Steuerelement zurückzugeben, können Sie kein Problem.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Grafikobjekte](../mfc/graphic-objects.md)  
  
-   [Einstufige und zweistufige Konstruktion von Grafikobjekten](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Gerätekontexte](../mfc/device-contexts.md)  
  
-   [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)  
  
## Siehe auch  
 [Grafikobjekte](../mfc/graphic-objects.md)
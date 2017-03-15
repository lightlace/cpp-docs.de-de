---
title: "Ein- oder zweistufige Erstellung von Objekten | Microsoft Docs"
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
  - "Objekterstellung, Grafikobjekte"
  - "Objekte [C++], Erstellen von Grafikobjekten"
  - "Objekte [C++], Grafikobjekte"
  - "Ein- und zweistufige Konstruktion von Objekten"
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Ein- oder zweistufige Erstellung von Objekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie haben die Wahl zwischen zwei Techniken zum Erstellen von Grafikobjekten, wie Stifte und Pinsel:  
  
-   *Einstufige Konstruktion*: Erstellen und initialisieren Sie das Objekt in einer Phase, alle mit dem Konstruktor.  
  
-   *Zweistufige Konstruktion*: Erstellen und initialisieren Sie das Objekt in zwei verschiedenen Phasen.  Der Konstruktor erstellt das Objekt und eine Initialisierungsfunktion initialisiert.  
  
 Zweistufige Konstruktion ist immer sicherer.  In der einstufigen Konstruktion kann der Konstruktor eine Ausnahme auslösen, zählen fehlerhafte Argumente bereitstellen, Speicherbelegung oder fehlschlägt.  Dieses Problem wird durch zweistufige Konstruktion vermieden, obwohl Sie für Fehler überprüfen.  In jedem Fall ist das Objekt zu zerstören der gleiche Prozess.  
  
> [!NOTE]
>  Diese Methoden gelten auf das Erstellen aller Objekte, nicht nur Grafikobjekte.  
  
## Beispiel Konstruktions\-Techniken beider  
 Das folgende kurze Beispiel werden beide Methoden zum Erstellen eines Stiftsobjekts an:  
  
 [!CODE [NVC_MFCDocViewSDI#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocViewSDI#6)]  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Grafikobjekte](../mfc/graphic-objects.md)  
  
-   [Auswählen eines Grafikobjekts in einem Gerätekontext](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [Gerätekontexte](../mfc/device-contexts.md)  
  
-   [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)  
  
## Siehe auch  
 [Grafikobjekte](../mfc/graphic-objects.md)
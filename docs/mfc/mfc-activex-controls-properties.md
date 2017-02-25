---
title: "MFC-ActiveX-Steuerelemente: Eigenschaften | Microsoft Docs"
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
  - "MFC-ActiveX-Steuerelemente, Eigenschaften"
  - "Eigenschaften [MFC]"
  - "Eigenschaften [MFC], ActiveX-Steuerelemente"
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MFC-ActiveX-Steuerelemente: Eigenschaften
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein ActiveX\-Steuerelement löst Ereignisse aus, um den Steuerelementcontainer zu kommunizieren.  Der Container verwendet als Ausgleich Methoden und Eigenschaften, um das Steuerelement zu kommunizieren.  Methoden und Eigenschaften sind ähnlich gebräuchliches und beabsichtigen bzw. auf die Memberfunktionen und Membervariablen von eine C\+\+\-Datei Klasse.  Eigenschaften sind Datenmember des ActiveX\-Steuerelements, die jedem Container verfügbar gemacht werden.  Eigenschaften stellen eine Schnittstelle für Anwendungen, die ActiveX\-Steuerelemente enthalten, z Automatisierungsclients und ActiveX\-Steuerelementcontainer bereit.  
  
 Eigenschaften werden auch Attribute bezeichnet.  
  
 Weitere Informationen über ActiveX\-Steuerelement\-Methoden, finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md).  
  
 ActiveX\-Steuerelemente können beide vordefinierten und benutzerdefinierten Methoden und Eigenschaften implementiert.  `COleControl`\-Klasse stellt eine Implementierung für vordefinierte Eigenschaften. \(Eine vollständige Liste von vordefinierten Eigenschaften, finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Hinzufügen vordefinierter Eigenschaften](../mfc/mfc-activex-controls-adding-stock-properties.md).\) Die benutzerdefinierten Eigenschaften, definiert vom Entwickler, fügen speziellen Funktionen einem ActiveX\-Steuerelement hinzu.  Weitere Informationen finden Sie unter [MFC\-ActiveX\-Steuerelemente: Hinzufügen benutzerdefinierter Eigenschaften](../mfc/mfc-activex-controls-adding-custom-properties.md).  
  
 werden benutzerdefinierte Ressource und Vorrateigenschaften, wie Methoden, durch einen Mechanismus unterstützt, der aus einer Dispatchzuordnung besteht, die Eigenschaften behandelt und vorhandene Methoden und Memberfunktionen `COleControl`\-Klasse.  Darüber hinaus können diese Eigenschaften Parameter verfügen, die der Entwickler verwendet, um zusätzliche Informationen zum Steuerelement zu übergeben.  
  
 Die folgenden Elemente werden ActiveX\-Steuerelementeigenschaften ausführlich erläutert:  
  
-   [MFC\-ActiveX\-Steuerelemente: Hinzufügen vordefinierter Eigenschaften](../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [MFC\-ActiveX\-Steuerelemente: Hinzufügen benutzerdefinierter Eigenschaften](../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [MFC\-ActiveX\-Steuerelemente: Erweiterte Eigenschaften\-Implementierung](../mfc/mfc-activex-controls-advanced-property-implementation.md)  
  
-   [MFC\-ActiveX\-Steuerelemente: Zugreifen auf Ambient\-Eigenschaften](../mfc/mfc-activex-controls-accessing-ambient-properties.md)  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)
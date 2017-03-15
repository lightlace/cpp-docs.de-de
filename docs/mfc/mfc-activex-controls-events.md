---
title: "MFC-ActiveX-Steuerelemente: Ereignisse | Microsoft Docs"
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
  - "COleControl-Klasse, Behandlung von Ereignissen"
  - "Containerereignisse"
  - "Benutzerdefinierte Ereignisse, Hinzufügen zu ActiveX-Steuerelementen"
  - "Ereignisse [C++], ActiveX-Steuerelemente"
  - "Ereignisse [C++], Zuordnen"
  - "Zuordnungen, Ereignisse"
  - "MFC-ActiveX-Steuerelemente, Ereignisse"
  - "Benachrichtigungen [C++], Benachrichtigen von Containern von Ereignissen"
  - "OLE-Ereignisse"
  - "Bestandereignissen"
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC-ActiveX-Steuerelemente: Ereignisse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX\-Steuerelemente verwenden Ereignisse, um einen Container zu benachrichtigen, der einige dem Steuerelement auftreten hat.  Allgemeine Beispiele des Ereigniseinschließung klickt auf dem Steuerelement, die Daten, die mit der Tastatur eingegeben werden und ändert den Zustand des Steuerelements.  Wenn diese Aktionen auftreten, löst das Steuerelement ein Ereignis aus, um den Container zu warnen.  
  
 Ereignisse werden auch Meldungen bezeichnet.  
  
 MFC unterstützt zwei Arten Ereignisse: Bestand und Custom.  Vordefinierte Ereignisse sind diese Ereignisse, die [COleControl](../mfc/reference/colecontrol-class.md) Handles automatisch Klasse.  Eine vollständige Liste vordefinierter Ereignissen, finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Hinzufügen vordefinierter Ereignissen](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md).  Benutzerdefinierte Ereignisse ermöglichen einem Steuerelement die Möglichkeit, den Container zu benachrichtigen, wenn ein Aktionsbesondere zu diesem Steuerelement erfolgt.  Einige Beispiele sind eine Änderung im internen Zustand eines Steuerelements oder einer bestimmten Eingangs Fenstermeldung sein.  
  
 Damit das Steuerelement angemessen Ereignisse, die Steuerelementklasse muss jedem Ereignis des Steuerelements an eine Memberfunktion zuordnen auslöst, die aufgerufen werden soll, wenn das zusammengehörender Ereignis auftritt.  Dieser Zuordnungsmechanismus \(bezeichnet eine Ereigniszuordnung\) zentralisiert Informationen zum Ereignis und ermöglicht Visual Studio einfach zugreifen und bearbeiten auf die Ereignisse des Steuerelements.  Diese Ereigniszuordnung wird durch das folgende Makro deklariert, in der Headerdatei \(.H\) Datei der Steuerelementklassendeklaration:  
  
 [!CODE [NVC_MFC_AxUI#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#2)]  
  
 Nachdem die Ereigniszuordnung deklariert wurde, muss sie in der Implementierung des Steuerelements definiert werden \(.CPP\).  Die folgenden Codezeilen werden die Ereigniszuordnung und ermöglichen das Steuerelement zu den Ereignissen des Datei:  
  
 [!CODE [NVC_MFC_AxUI#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#3)]  
[!CODE [NVC_MFC_AxUI#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#4)]  
  
 Wenn Sie den MFC\-ActiveX\-Steuerelement\-Assistenten verwenden, um das Projekt zu erstellen, wird automatisch diese Zeilen hinzu.  Wenn Sie nicht den MFC\-ActiveX\-Steuerelement\-Assistenten verwenden, müssen Sie diese manuell Zeilen hinzufügen.  
  
 Mit Klassenansicht können Sie die vordefinierten Ereignisse, die vom `COleControl`\-Klasse unterstützt werden oder die benutzerdefinierten Ereignisse hinzufügen, die Sie definieren.  Für jedes neue Ereignis fügt Klassenansicht automatisch den gewünschten Eintrag der Ereigniszuordnung des Steuerelements und der IDL\-Datei des Steuerelements hinzu.  
  
 Zwei weitere Elemente werden Ereignisse im Detail beschrieben:  
  
-   [MFC\-ActiveX\-Steuerelemente: Hinzufügen vordefinierter Ereignissen](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [MFC\-ActiveX\-Steuerelemente: Hinzufügen von benutzerdefinierten Ereignissen](../mfc/mfc-activex-controls-adding-custom-events.md)  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)
---
title: "Festlegen des CStatusBarCtrl-Objektmodus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl-Klasse, Einfache und nicht einfache Modi"
  - "IsSimple-Methode, Verwenden"
  - "Nicht einfacher Modus und Statusleistensteuerelemente"
  - "SetSimple-Methode"
  - "Einfacher Modus und Statusleistensteuerelemente"
  - "Statusleiste-Steuerelement, Einfache und nicht einfache Modi"
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Festlegen des CStatusBarCtrl-Objektmodus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt zwei Modi für ein `CStatusBarCtrl`\-Objekt: einfach und nicht einfach.  In der Mehrzahl Fälle, verfügt Ihr StatusBar\-Steuerelement eine oder mehrere Teile, zusammen mit Text und möglicherweise einem Symbol oder Symbolen.  Dies wird nicht den einfachen Modus bezeichnet.  Weitere Informationen zu diesem Modus, finden Sie unter [Initialisieren der Teile eines CStatusBarCtrl\-Objekts](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).  
  
 Allerdings gibt es Fälle, in denen Sie nur eine einzelne Textzeile anzeigen müssen.  In diesem Fall ist der einfache Modus für Ihre Zwecke ausreichend.  So den Modus des `CStatusBarCtrl`\-Objekts in einfachem ändern, können Sie die Memberfunktion [SetSimple](../Topic/CStatusBarCtrl::SetSimple.md).  Sobald das StatusBar\-Steuerelement im einfachen Modus ist, legen Sie den Text fest, indem Sie die **SetText**\-Memberfunktion aufrufen und 255 als Wert für den Parameter **nPane** übergeben haben.  
  
 In Sie können die [IsSimple](../Topic/CStatusBarCtrl::IsSimple.md)\-Funktion verwenden, um zu bestimmen, in welchem Modus sich das `CStatusBarCtrl`\-Objekt.  
  
> [!NOTE]
>  Wenn das Statusleistenobjekt nicht von einfachem zu einfachem oder umgekehrt geändert wird, wird das Fenster sofort neu gezeichnet und es gegebenenfalls werden alle definierten Teilen automatisch wiederhergestellt.  
  
## Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
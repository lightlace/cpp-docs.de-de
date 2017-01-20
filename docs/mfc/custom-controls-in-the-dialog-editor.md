---
title: "Custom Controls in the Dialog Editor"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "Custom Control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [C++], templates"
  - "custom controls [Visual Studio], dialog boxes"
  - "custom controls [Visual Studio]"
  - "dialog box controls, custom (user) controls"
  - "Dialog editor, custom controls"
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Custom Controls in the Dialog Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Dialog\-Editor ermöglicht die Verwendung "angepasster" oder "benutzerdefinierter" Steuerelemente in einer Dialogfeldvorlage.  
  
> [!NOTE]
>  Benutzerdefinierte Steuerelemente dieser Art dürfen nicht mit ActiveX\-Steuerelementen verwechselt werden.  ActiveX\-Steuerelemente wurden zeitweise auch als benutzerdefinierte OLE\-Steuerelemente bezeichnet.  Außerdem sollten diese Steuerelemente auch nicht mit den ownerdrawn Steuerelementen in Windows verwechselt werden.  
  
 Diese Funktion soll Ihnen die Verwendung von Steuerelementen ermöglichen, die nicht zum Lieferumfang von Windows gehören.  Zur Laufzeit wird das Steuerelement mit einer Fensterklasse \(nicht identisch mit einer C\+\+\-Klasse\) verknüpft.  Ein gängigeres Verfahren, dieselbe Aufgabe auszuführen, besteht in der Installation eines beliebigen Steuerelements, z. B. eines statischen Steuerelements, im Dialogfeld.  Anschließend entfernen Sie zur Laufzeit das Steuerelement in der [OnInitDialog](../Topic/CDialog::OnInitDialog.md)\-Funktion und ersetzen es durch Ihr eigenes benutzerdefiniertes Steuerelement.  
  
 Dies ist ein altbewährtes Verfahren.  Heute wird in den meisten Fällen angeraten, ein ActiveX\-Steuerelement zu schreiben oder eine Unterklasse für ein allgemeines Windows\-Steuerelement zu erstellen.  
  
 Für benutzerdefinierte Steuerelemente werden folgende Tasks unterstützt:  
  
-   Festlegen der Position im Dialogfeld.  
  
-   Eingeben einer Beschriftung.  
  
-   Kennzeichnen des Namens der steuerelementspezifischen Windows\-Klasse \(das Steuerelement muss vom Anwendungscode unter diesem Namen registriert werden\).  
  
-   Eingeben eines hexadezimalen 32\-Bit\-Werts, der den Steuerelementstil festlegt.  
  
-   Festlegen des erweiterten Stiles.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
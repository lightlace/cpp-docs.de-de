---
title: "Bereitstellen kontextbezogener Hilfe | Microsoft Docs"
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
  - "Kontextbezogene Hilfe"
  - "Kontextbezogene Hilfe, Benutzerdefinierter Assistent"
  - "Benutzerdefinierte Assistenten, Implementieren der Hilfe"
ms.assetid: c6c4d961-29d3-4d16-9f39-b12545aba540
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Bereitstellen kontextbezogener Hilfe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie den [benutzerdefinierten Assistenten](../ide/application-settings-custom-wizard.md) verwenden, um einen Assistenten zu erstellen, wird eine Hilfeschaltfläche in den neuen Assistenten eingefügt.  
  
 Jede HTM\-Datei in Ihrem Projekt enthält folgenden Code zur Unterstützung der Hilfeschaltfläche des Assistenten.  
  
```  
<BUTTON CLASS="BUTTONS" ID="HelpBtn" ACCESSKEY="H"  
 onClick="window.external.OnHelp('vc.appwiz.custom.overview');">  
```  
  
 <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.OnHelp*> gibt das Schlüsselwort der HTML\-Hilfedatei an, die der jeweiligen Assistentenseite zugeordnet ist.  Weitere Informationen zum Erstellen von HTML\-Hilfedateien, die mit der Seite verknüpft werden sollen, finden Sie unter [HTML\-Hilfestartseite](vsconhh1start).  Um eigene Hilfe für die jeweilige Assistentenseite bereitzustellen, müssen Sie die Zeichenfolge `'vc.appwiz.custom.overview'` durch das Schlüsselwort ersetzen, mit dem das HTML\-Hilfethema für die Seite gekennzeichnet ist.  
  
 **Hinweis** Diese HTM\-Datei kann nicht in die kompilierte MSDN\-Hilfe integriert werden.  
  
## Siehe auch  
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)
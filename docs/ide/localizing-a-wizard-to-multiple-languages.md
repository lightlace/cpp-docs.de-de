---
title: "Lokalisieren eines Assistenten in mehrere Sprachen"
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
  - "Benutzerdefinierte Assistenten, Lokalisieren"
  - "Globalisierung [C++], Assistenten"
  - "Lokalisierung [C++], Assistenten"
  - "Assistenten [C++], Lokalisieren"
ms.assetid: 879885c2-fafd-44fd-8032-bf0c301f4f45
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Lokalisieren eines Assistenten in mehrere Sprachen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Assistenten können in jeder von Visual Studio unterstützten Sprache erstellt werden.  Bei der Installation von Visual Studio wird das Gebietsschema standardmäßig anhand der Registrierung ermittelt und die für dieses Schema geeigneten Vorlagen bereitgestellt.  
  
 Visual Studio verwendet Sprach\-IDs, um die von einem Assistenten benötigte Sprachunterstützung zu identifizieren.  Die Sprach\-ID wird standardmäßig auf den Dezimalwert des Registrierungseintrags **HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\7.0\\General\\UILanguage** festgelegt.  Wenn der Assistent keinen Spracheintrag findet, wird als Standardwert Englisch \(1033\) verwendet.  
  
> [!NOTE]
>  Eine Liste der Dezimalwerte für Sprachen finden Sie unter [Assistentenunterstützung für andere Sprachen](../ide/wizard-support-for-other-languages.md).  
  
 Die Sprach\-ID wird in der [VSZ\-Datei](../Topic/Configuring%20.Vsz%20Files%20to%20Start%20Wizards.md) in den Verzeichnissen, in denen die [HTML\-Dateien](../ide/html-files.md) und die [Vorlagendateien](../ide/template-files.md) gespeichert sind, als benutzerdefinierter Parameter angegeben.  
  
 Sie sollten die Pfade für jede Sprache angeben, für die Sie eine HTM\-Datei bereitstellen.  
  
## Beispiel  
 Wenn Sie die folgenden benutzerdefinierten Parameter in der VSZ\-Datei festlegen, geben Sie an, dass Sie die HTML\-Datei in Englisch \(1033\), Japanisch \(1041\) und Deutsch \(1031\) bereitstellen:  
  
```  
Param="START_PATH\HTML\1033"  
Param="START_PATH\HTML\1041"  
Param="START_PATH\HTML\1031"  
Param="START_PATH\Templates\1033"  
Param="START_PATH\Templates\1041"  
Param="START_PATH\Templates\1031"  
```  
  
 Indem Sie die benutzerdefinierten Parameter wie im obigen Beispiel angeben, richten Sie für den Assistenten die folgende Verzeichnisstruktur ein:  
  
```  
MyWizard1  
   HTML  
      1033  
         default.htm  
         myEnglishHTML.htm  
      1041  
         default.htm  
         myJapaneseHTML.htm  
      1031  
         default.htm  
         myGermanHTML.htm  
   Templates  
      1033  
         stdafx.h  
         stdafx.cpp  
      1041  
         stdafx.h  
         stdafx.cpp  
      1031  
         stdafx.h  
         stdafx.cpp  
   Images  
      HtmlPage1.bmp  
      HtmlPage2.jpg  
   Scripts  
      Default.js  
```  
  
## Siehe auch  
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [Benutzerdefinierte Parameter in der VSZ\-Assistentendatei](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md)
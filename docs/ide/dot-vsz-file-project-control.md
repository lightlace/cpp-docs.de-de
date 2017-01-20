---
title: "VSZ-Datei (Projektsteuerung)"
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
  - ".vsz-Dateien"
  - "Benutzerdefinierte Assistenten, VSZ-Datei"
  - "Benutzerdefinierte Assistenten, Projektsteuerelementdateien"
  - "Dateien [C++], Erstellt durch einen benutzerdefinierten Assistenten"
  - "VSZ-Dateien"
ms.assetid: b8678fee-6795-46d1-9338-48b22d5e9207
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# VSZ-Datei (Projektsteuerung)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Ausgangspunkt jedes Assistenten ist die VSZ\-Datei.  Die VSZ\-Datei ist eine Textdatei, die den aufzurufenden Assistenten sowie die Informationen bestimmt, die an den Assistenten übergeben werden.  Die Datei enthält einen zweizeiligen Header, gefolgt von verschiedenen optionalen Parametern, die an den Assistenten übergeben werden.  Eine Liste optionaler Parameter finden Sie unter [Benutzerdefinierte Parameter in der VSZ\-Assistentendatei](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md).  
  
 Im folgenden Beispiel ist der Header in einer VSZ\-Datei dargestellt:  
  
```  
VSWIZARD 7.0  
Wizard=VsWizard.VsWizardEngine.10.0  
Param="WIZARD_NAME = My AppWizard"  
```  
  
-   Die erste Headerzeile gibt die Versionsnummer des Vorlagendateiformats an.  Sie können diese Nummer als `6.0`, `7.0` oder `7.1` angeben.  Andere Versionsnummern sind nicht zulässig, da andernfalls der Fehler "Ungültiges Format" ausgegeben wird.  
  
-   In der zweiten Zeile wird für die **Wizard**\-Variable die ProgID des Assistenten festgelegt, die gleichzeitig von Visual Studio erstellt wird.  Eine ProgID entspricht der Zeichenfolgendarstellung einer CLSID, z. B. `VsWizard.VsWizardEngine.10.0`.  
  
     Wenn der Assistent eine Benutzeroberfläche besitzt, legt die ProgID automatisch fest, dass der Assistent <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI> implementiert.  Die Methoden dieser Oberfläche werden standardmäßig in den projektspezifischen [HTM\-Dateien](../ide/html-files.md) verwendet.  Sie können Änderungen am Verhalten des Assistenten vornehmen, indem Sie die Methoden für diese Oberfläche in den HTM\-Dateien verwenden.  Weitere Informationen finden Sie unter den Erläuterungen zu <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl>, der Co\-Klasse von <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI>.  
  
-   Auf diese beiden Zeilen folgt eine optionale Parameterliste, die es der VSZ\-Datei ermöglicht, weitere benutzerdefinierte Parameter an den Assistenten zu übergeben.  Jeder Wert wird als Zeichenfolgenelement in einem Variantenarray an die <xref:Microsoft.VisualStudio.VsWizard.VsWizardClass.Execute*>\-Methode des Wizard\-Steuerelements übergeben.  Ein Assistent mit Benutzeroberfläche erzeugt standardmäßig die folgenden Parameter:  
  
    ```  
    Param="START_PATH = <path to the wizard>"  
    Param="HTML_PATH = <path to the wizard's HTML file>"  
    Param="TEMPLATES_PATH = <path to the wizard's template file>"  
    Param="SCRIPT_PATH = <path to the wizard's script files>"  
    Param="IMAGES_PATH = <path to the wizard's images>"  
    ```  
  
     Wenn der Assistent keine Benutzeroberfläche besitzt, weist er anstelle des Parameters `IMAGES_PATH` die folgenden Parameter auf:  
  
    ```  
    Param="WIZARD_UI = FALSE"  
    Param="SOURCE_FILTER = txt"  
    ```  
  
-   Die VSZ\-Datei kann die folgenden Parameter enthalten, die Funktionen in der Datei [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) festlegen:  
  
    ```  
    Param="PREPROCESS_FUNCTION = CanAddATLClass"  
    Param="PREPROCESS_FUNCTION = CanAddMFCClass"  
    Param="PREPROCESS_FUNCTION = CanAddClass"  
    ```  
  
 Die Funktionen [CanAddATLClass](../ide/canaddatlclass.md), [CanAddMFCClass](../ide/canaddmfcclass.md) und [CanAddClass](../ide/canaddclass.md) werden vom Assistenten aufgerufen, um die Verfügbarkeit des [Visual C\+\+\-Codemodells](assetId:///dd6452c2-1054-44a1-b0eb-639a94a1216b) zu bestätigen.  Wenn eine der Funktionen den Wert **false** zurückgibt, wird der Assistent nicht gestartet.  
  
 Sie können den Assistenten dem Bereich "Vorlagen" im Dialogfeld **Neues Projekt** von Visual Studio hinzufügen, indem Sie die VSZ\-Datei im Verzeichnis "vcprojects" ablegen.  Der benutzerdefinierte Assistent schreibt die VSZ\-Datei standardmäßig in dieses Verzeichnis.  
  
> [!NOTE]
>  Wenn Sie die Assistentendateien und \-verzeichnisse löschen, müssen Sie zusätzlich die VSZ\-, VSDIR\- und ICO\-Projektdateien aus dem Verzeichnis "vcprojects" löschen.  
  
## Siehe auch  
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Visual C\+\+ Wizard Model](assetId:///159395ac-33c7-47bf-ad42-4e1435ddc758)   
 [Hinzufügen von Assistenten zu den Dialogfeldern Element hinzufügen und Neues Projekt mithilfe von VSDIR\-Dateien](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)
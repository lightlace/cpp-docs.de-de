---
title: "Anpassen des Assistenten | Microsoft Docs"
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
  - "Benutzerdefinierte Assistenten"
  - "Benutzerdefinierte Assistenten, Erstellen in Visual C++-Projekten"
ms.assetid: a3ff1c81-3eef-41e7-a6bc-2f98e4bf423f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Anpassen des Assistenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden allgemeinen Aufgaben sollten beim Anpassen des mit dem [benutzerdefinierten Assistenten](../ide/application-settings-custom-wizard.md) erstellten Assistenten beachtet werden.  
  
-   Legen Sie in der VSZ\-Datei alle benutzerdefinierten Parameter fest, die zur einwandfreien Ausführung des Assistenten erforderlich sind.  Weitere Informationen finden Sie unter [VSZ\-Datei \(Projektsteuerung\)](../ide/dot-vsz-file-project-control.md) und [Benutzerdefinierte Parameter in der VSZ\-Assistentendatei](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md).  
  
     Wenn Sie den Assistenten in mehrere Sprachen lokalisieren, fügen Sie der VSZ\-Datei die entsprechenden Sprachparameter hinzu.  Weitere Informationen finden Sie unter [Lokalisieren eines Assistenten in mehrere Sprachen](../ide/localizing-a-wizard-to-multiple-languages.md).  
  
-   Passen Sie die [Vorlagendateien](../ide/template-files.md) \(und [Templates.inf](../ide/templates-inf-file.md)\) an, um die Direktiven für Benutzeroptionen festzulegen.  
  
-   Passen Sie die [Datei "Default.js"](../ide/jscript-file.md) an, um zusätzliche gesonderte Behandlungen für den Assistenten festzulegen.  Sie können eigene Funktionen schreiben oder die in [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) bereitgestellten Funktionen verwenden.  
  
-   Entwerfen Sie Symbole und andere Bilder zur Verwendung in der HTML\-Benutzeroberfläche.  
  
-   Entwerfen Sie die HTML\-Benutzeroberfläche.  
  
-   Fügen Sie der HTML\-Symboltabelle die Symbole hinzu, die den Schaltflächen, Steuerelementen, Textfeldern und sonstigen Elementen entsprechen, die im Assistenten verwendet werden.  
  
     Der folgende HTML\-Codeauszug wurde vom benutzerdefinierten Assistenten erstellt:  
  
    ```  
    <SYMBOL NAME="WIZARD_DIALOG_TITLE" TYPE=text VALUE="MyCustomWiz">  
          </SYMBOL>  
    <SYMBOL NAME="SAMPLE_CHECKBOX" TYPE=checkbox VALUE=true>  
          </SYMBOL>  
    ```  
  
     Dieser Assistent mit der Bezeichnung "MyCustomWiz" zeigt ein Kontrollkästchen an, das standardmäßig aktiviert ist.  
  
-   Fügen Sie dem in den HTML\-Dateien anhand von `<SCRIPT LANGUAGE="JSCRIPT">` erkennbaren Abschnitt JScript\-Funktionsaufrufe hinzu, und greifen Sie auf das Visual Studio\-Objektmodell zu, um das Verhalten des Assistenten anzupassen.  Diese Funktionen müssen unter Verwendung von `window.external` folgendermaßen aufgerufen werden:  
  
    ```  
    window.external.AddSymbol("MAIN_FRAME_DEFAULT_STYLES", true);  
    window.external.AddSymbol("MAIN_FRAME_STYLE_FLAGS", "");  
    ```  
  
    > [!NOTE]
    >  Mithilfe der über [Automatisierung und Erweiterbarkeit für Visual Studio](../Topic/Automation%20and%20Extensibility%20for%20Visual%20Studio.md), [Visual C\+\+\-Codemodell](assetId:///dd6452c2-1054-44a1-b0eb-639a94a1216b), [Projektmodell](assetId:///06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f) und [Assistentenmodell](assetId:///159395ac-33c7-47bf-ad42-4e1435ddc758) verfügbaren Methoden, Eigenschaften und Ereignisse können Sie alle Aspekte des Assistentenprojekts von der Erstellung bis zum Build in JScript\-Dateien und HTM\-Dateien programmgesteuert verwalten.  
  
-   Passen Sie ggf. die [VSDIR\-Datei](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md) an, damit Informationen über die VSZ\-Datei und alle weiteren Vorlagen von der Shell gelesen werden können.  Verweisen Sie beispielsweise auf Symbolressourcen\-ID, Flags, lokalisierte Namen usw.  
  
-   Erstellen Sie HTM\-Dateien und Vorlagendateien in allen Sprachen, in die der Assistent lokalisiert wird.  Legen Sie sie in den entsprechenden Projektverzeichnissen ab.  
  
-   Stellen Sie [kontextbezogene Hilfe](../ide/providing-context-sensitive-help.md) für den Assistenten bereit.  
  
## Siehe auch  
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Schritte zum Entwerfen eines Assistenten](../ide/steps-to-designing-a-wizard.md)   
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Bereitstellen kontextbezogener Hilfe](../ide/providing-context-sensitive-help.md)   
 [Behandeln von Fehlern in Assistenten](../ide/handling-errors-in-wizards.md)
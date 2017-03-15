---
title: "Benutzerdefinierte Parameter in der VSZ-Assistentendatei"
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
  - "ABSOLUTE_PATH-Makro"
  - "Benutzerdefinierte Assistenten, VSZ-Datei"
  - "HTML_FILTER-Makro"
  - "HTML_PATH-Makro"
  - "IMAGE_FILTER-Makro"
  - "IMAGES_PATH-Makro"
  - "MISC_FILTER-Makro"
  - "PRODUCT-Makro"
  - "PRODUCT_INSTALLATION_DIR-Makro"
  - "PROJECT_TEMPLATE_NAME-Makro"
  - "PROJECT_TEMPLATE_PATH-Makro"
  - "RELATIVE_PATH-Makro"
  - "SCRIPT_COMMON_PATH-Makro"
  - "SCRIPT_FILTER-Makro"
  - "SCRIPT_PATH-Makro"
  - "START_PATH-Makro"
  - "TEMPLATE_FILTER-Makro"
  - "TEMPLATES_PATH-Makro"
  - "WIZARD_NAME-Makro"
  - "WIZARD_UI-Makro"
ms.assetid: 560dd5c0-7cff-4974-b856-5ca25b0669b8
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Benutzerdefinierte Parameter in der VSZ-Assistentendatei
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In den ersten beiden Zeilen der VSZ\-Datei werden die Assistentenversion und die ProgID oder CLSID des parallel zu erstellenden Assistenten identifiziert.  Die VSZ\-Datei kann außerdem optionale Kontextparameter und benutzerdefinierte Parameter umfassen, die der Symboltabelle \(zusammen mit den im HTML\-Symbolabschnitt bereitgestellten Symbolen\) hinzugefügt werden.  
  
 Durch die <xref:Microsoft.VisualStudio.VsWizard.VsWizardClass.Execute*>\-Methode wird der Assistent eingeblendet, der ein Array der in der VSZ\-Datei definierten Kontext\- und benutzerdefinierten Parameter als Parameter verwendet.  
  
 Die folgenden häufig verwendeten Symbole werden entweder in der [VSZ\-Datei](../ide/dot-vsz-file-project-control.md) oder in den HTM\-Dateien als benutzerdefinierte Parameter festgelegt und können in den HTML\-, Skript\- oder Vorlagendateien des Assistenten verwendet werden.  
  
## Beispiel  
 Wie aus den folgenden Einträgen in der VSZ\-Datei ersichtlich, besitzt der Assistent mit dem Namen "MyProjWiz" eine Benutzeroberfläche.  
  
```  
VSWIZARD 7.0  
Wizard=VsWizard.VsWizardEngine  
Param="WIZARD_NAME = MyProjWiz"  
Param="WIZARD_UI = TRUE"  
```  
  
### Symbole für benutzerdefinierte Parameter in der VSZ\-Assistentendatei  
  
|Symbol|Definition|  
|------------|----------------|  
|ABSOLUTE\_PATH|Der Speicherort der Assistentendateien.|  
|HTML\_FILTER|Wird in der VSZ\-Datei festgelegt.  Dateitypen, die im Ordner HTML\-Dateien im **Projektmappen\-Explorer** abgelegt werden.  Normalerweise im Format "HTM".|  
|HTML\_PATH|Wird in der VSZ\-Datei festgelegt.  Der Speicherort der assistentenspezifischen [HTML\-Dateien](../ide/html-files.md).  Er lautet standardmäßig *START\_PATH\\HTML\\*SPRACHE \(wobei *SPRACHE* dem in der Systemregistrierung festgelegten Gebietsschema entspricht\). **Note:**  Sie können eine andere Sprache angeben, indem Sie \<LangID\> auf den Dezimalwert von HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\7.0\\General\\UILanguage festlegen.  Weitere Informationen finden Sie unter [Lokalisieren eines Assistenten in mehrere Sprachen](../ide/localizing-a-wizard-to-multiple-languages.md).  Eine Liste der Dezimalwerte für Sprachen finden Sie unter [Assistentenunterstützung für andere Sprachen](../ide/wizard-support-for-other-languages.md).|  
|IMAGE\_FILTER|Wird in der VSZ\-Datei festgelegt.  Dateitypen, die im Ordner **Bilddateien** im Projektmappen\-Explorer abgelegt werden.  Normalerweise im Format "BMP;GIF".|  
|IMAGES\_PATH|Wird in der VSZ\-Datei festgelegt.  Der Speicherort der Bilddateien, die in den HTML\-Dateien verwendet werden.  Er lautet standardmäßig **START\_PATH\\Images**.|  
|MISC\_FILTER|Wird in der VSZ\-Datei festgelegt.  Dateitypen, die im Ordner für sonstige Dateien im Projektmappen\-Explorer abgelegt werden.  Normalerweise im Format "VSZ;VSDIR;ICO;VCPROJ;CSPROJ;CSS;INF".|  
|PRODUCT|Ist standardmäßig auf Visual C\+\+ festgelegt; Sie können diesen Wert jedoch auf Visual Basic setzen, um Visual Basic\-Assistenten usw. zu erstellen.|  
|PRODUCT\_INSTALLATION\_DIR|Das Verzeichnis, das in der Registrierung unter **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\7.0\\Setup\\\<Product\>\\ProductDir** aufgeführt ist.|  
|PROJECT\_TEMPLATE\_NAME|Wird in der VSZ\-Datei festgelegt.  Die Projektvorlagendatei, die der Assistent zum Erstellen von Projekten verwendet.  Normalerweise im Format "TXT".|  
|PROJECT\_TEMPLATE\_PATH|Das Verzeichnis, das die [Vorlagendateien](../ide/template-files.md) des Projekts enthält.  Für Visual C\+\+ lautet es standardmäßig **PRODUCT\_INSTALLATION\_DIR\\VCWizards**.|  
|RELATIVE\_PATH|Wenn **ABSOLUTE\_PATH** nicht gefunden wird, wird **RELATIVE\_PATH** verwendet.  Dies ist der Pfad relativ zu PRODUCT\_INSTALLATION\_DIR.  Bei Visual C\+\+ hat RELATIVE\_PATH den Wert PRODUCT\_INSTALLATION\_DIR\\VCWizards.|  
|SCRIPT\_COMMON\_PATH|Der Name des Verzeichnisses relativ zu **PRODUCT\_INSTALLATION\_DIR**, in dem sich die allgemeine Skriptdatei befindet.  Für Visual C\+\+ lautet er beispielsweise **VCWizards**.|  
|SCRIPT\_FILTER|Wird in der VSZ\-Datei festgelegt.  Dateitypen, die im Ordner **Skriptdateien** im Projektmappen\-Explorer abgelegt werden.  Normalerweise im Format "JS" \(JScript\) oder "VBS" \(VBScript\).|  
|SCRIPT\_PATH|Der Speicherort der [JScript\-Datei](../ide/jscript-file.md) des Assistenten.  Er lautet standardmäßig **START\_PATH\\Scripts**.|  
|START\_PATH|Wird in der VSZ\-Datei festgelegt.  Wird nicht vom Benutzer festgelegt, sondern intern verwendet, um entweder **RELATIVE\_PATH** oder **ABSOLUTE\_PATH** zu identifizieren.  Der Name des Assistenten \(**WIZARD\_NAME**\) wird an diesen Wert angefügt.|  
|TEMPLATE\_FILTER|Wird in der VSZ\-Datei festgelegt.  Dateitypen, die im Ordner **Vorlagendateien** im Projektmappen\-Explorer abgelegt werden.  Normalerweise im Format "TXT".|  
|TEMPLATES\_PATH|Wird in der VSZ\-Datei festgelegt.  Der Speicherort der assistentenspezifischen Vorlagendateien.  Er lautet standardmäßig **START\_PATH\\Templates\\\<LangID\>**. **Note:**  Weitere Informationen zu LangID finden Sie in den Erläuterungen zu HTML\_PATH.|  
|WIZARD\_NAME|Gibt den Namen des Assistenten an.  Befindet sich in der VSZ\-Datei und wird von den übrigen Symbolen verwendet.|  
|WIZARD\_UI|Wird in der VSZ\-Datei festgelegt.  Ein boolescher Wert, der angibt, ob der Assistent eine Benutzeroberfläche besitzt.  **TRUE** gibt an, dass der Assistent eine Benutzeroberfläche besitzt, und **FALSE** gibt an, dass keine vorhanden ist.|  
  
## Siehe auch  
 <xref:EnvDTE.IDTWizard.Execute*>   
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)
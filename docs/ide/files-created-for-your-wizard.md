---
title: "F&#252;r den Assistenten erstellte Dateien | Microsoft Docs"
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
  - "Benutzerdefinierte Assistenten, Löschen von Dateien"
  - "Benutzerdefinierte Assistenten, Dateien erstellt"
  - "Dateien [C++], Erstellt durch einen benutzerdefinierten Assistenten"
  - "Symbole, Löschen"
ms.assetid: 7f0e393c-395e-491b-add2-904cf8838e81
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# F&#252;r den Assistenten erstellte Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Assistent verwendet den Namen, den Sie im Dialogfeld **Neues Projekt** im Feld **Name** angeben, um die Namen für einige Dateien und Klassen abzuleiten.  
  
 Der [benutzerdefinierte Assistent](../ide/custom-wizard.md) fügt den für den Assistent erstellten Dateien Kommentare hinzu.  Darüber hinaus erstellt der benutzerdefinierte Assistent im neuen Anwendungsverzeichnis die Textdatei "readme.txt".  In dieser Datei werden Inhalt und Verwendung anderer neuer Dateien, die vom benutzerdefinierten Assistenten erstellt wurden, erläutert.  
  
 In der folgenden Tabelle werden die Dateien beschrieben, die vom benutzerdefinierten Assistenten erstellt werden.  Weitere Informationen dazu, wie die wichtigsten Elemente bei der Erstellung eines Assistenten interagieren, finden Sie unter [Entwerfen eines Assistenten](../ide/designing-a-wizard.md).  
  
|Datei|Beschreibung|  
|-----------|------------------|  
|[Project.vsz](../ide/dot-vsz-file-project-control.md)|Eine Textdatei, die dem alten INI\-Format gleicht.  Sie identifiziert das Assistentenmodul und liefert Kontextparameter und optionale [benutzerdefinierte Parameter](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md).|  
|[Project.vsdir](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md)|Eine Textdatei, mit der die Visual Studio\-Shell den Assistent suchen und im Dialogfeld **Neues Projekt** anzeigen kann.|  
|[HTML\-Dateien \(optional\)](../ide/html-files.md)|Ein Assistent kann über eine Benutzeroberfläche \(UI, User Interface\) in Form einer HTML\-Oberfläche verfügen.  Ein Assistent ohne Benutzeroberfläche enthält keine HTML\-Dateien.<br /><br /> Weist ein Assistent eine Benutzeroberfläche auf, werden die einzelnen Bildschirme im Assistent als *Seite* bezeichnet, und jede Seite dient der Angabe von Benutzeroberflächenfunktionen.<br /><br /> Die Datei "default.htm" definiert die erste Seite im Assistenten.  Verwenden Sie das Listenfeld **Seitenanzahl** unter [Anwendungseinstellungen, Benutzerdefinierter Assistent](../ide/application-settings-custom-wizard.md), um weitere Seiten anzugeben.  Jede weitere Seite wird von einer "Page\_*Seitenanzahl*.htm"\-Datei definiert, wobei *Seitenanzahl* von 2 bis zur Anzahl der von Ihnen angegebenen Seiten reicht.|  
|[Skriptdateien](../ide/jscript-file.md)|Der benutzerdefinierte Assistent erstellt für jeden erstellten Assistent eine JScript\-Datei, "default.js".  Diese Datei enthält JScript\-Funktionen, die auf den Visual C\+\+\-Assistenten, auf den Code und auf die Umgebungsobjektmodelle zugreifen, um einen Assistenten anzupassen.  In der standardmäßigen Datei "Default.js" des Assistenten können Sie Funktionen anpassen und hinzufügen.<br /><br /> Darüber hinaus umfasst der Assistent die Datei [common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md), die häufig verwendete JScript\-Funktionen enthält und von allen Assistenten gemeinsam genutzt wird. Dazu gehören auch die Assistenten, die von Visual C\+\+ zum Erstellen anderer Projekttypen verwendet werden.  Weitere Informationen finden Sie unter [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md).|  
|[Vorlagen](../ide/template-files.md)|Bei den Vorlagen eines Assistenten handelt es sich um eine Zusammenstellung von Textdateien mit Direktiven, die analysiert und abhängig von den im Assistenten ausgewählten Benutzeroptionen in die Symboltabelle eingefügt werden.  Die Vorlagentextdateien werden entsprechend den Benutzereingaben gerendert und dem vom Assistent erstellten Projekt hinzugefügt.  Die benötigten Informationen werden durch den direkten Zugriff auf die Symboltabelle der Assistentensteuerung ermittelt.|  
|[Templates.inf](../ide/templates-inf-file.md)|Eine Textdatei, in der alle mit dem Projekt verknüpften Vorlagen aufgelistet sind.|  
|Default.vcxproj|Eine XML\-Datei, die die Informationen zum Projekttyp enthält.|  
|Sample.txt|Eine Vorlagendatei, in der aufgezeigt wird, wie die Assistentendirektiven verwendet werden.|  
|ReadMe.txt|Eine Vorlagendatei, die eine Zusammenfassung aller Dateien enthält, die vom benutzerdefinierten Assistenten erstellt wurden.|  
|Bilder \(optional\)|Sie können beliebige Bilder, z. B. Symbole, GIF\- oder BMP\-Dateien und andere Bildformate mit HTML\-Unterstützung, bereitstellen, um die Benutzeroberfläche des Assistenten weiter zu gestalten.  Ein Assistent ohne Benutzeroberfläche erfordert keine Bilder.|  
|Styles.css \(optional\)|Eine Datei, in der die Benutzeroberflächenstile definiert sind.  Wenn der Assistent keine Benutzeroberfläche besitzt, erstellt der benutzerdefinierte Assistent keine CSS\-Datei.|  
  
 Wenn Sie die Assistentendateien und \-verzeichnisse löschen, müssen Sie zusätzlich die folgenden Dateien aus dem Verzeichnis "\\vc7\\vcprojects" löschen.  Solange diese Dateien nicht entfernt wurden, werden im Dialogfeld **Neues Projekt** weiterhin Symbole für den Assistenten angezeigt.  
  
-   *Projektname*.vsz  
  
-   *Projektname*.ico  
  
-   *Projektname*.vsdir  
  
## Siehe auch  
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)
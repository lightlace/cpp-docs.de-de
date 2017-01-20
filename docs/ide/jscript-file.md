---
title: "JScript-Datei"
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
  - "AddConfig-Methode"
  - "AddFilesToCustomProj-Methode"
  - "AddFilters-Methode"
  - "Common.js (Datei)"
  - "CreateCustomInfFile-Methode"
  - "CreateCustomProject-Methode"
  - "Benutzerdefinierte Assistenten, Zugreifen auf das Assistentenobjektmodell"
  - "Benutzerdefinierte Assistenten, JScript-Datei"
  - "Debuggen [JScript], Aktivieren des Skriptdebuggens"
  - "Debuggen [JScript], JScript-Dateien"
  - "Debuggen von Skripts"
  - "Debuggen von Skripts, Aktivieren des Skriptdebuggens"
  - "Default.js (Datei)"
  - "DelFile-Methode"
  - "Dateien [C++], Erstellt durch einen benutzerdefinierten Assistenten"
  - "GetTargetName-Methode"
  - "JScript-Dateien"
  - "OnFinish-Methode"
  - "PchSettings-Methode"
ms.assetid: 7841a09e-2dd2-4f1a-a13a-39ac53f24315
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# JScript-Datei
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der [benutzerdefinierte Assistent](../ide/custom-wizard.md) greift auf das Skriptmodul zu und erstellt für jedes Projekt eine JScript\-Datei mit dem Namen **Default.js**.  Zusätzlich ist die Datei [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) enthalten.  Diese Dateien enthalten JScript\-Funktionen, über die Sie Zugriff auf das Visual Studio\- und das Visual C\+\+\-Objektmodell erhalten, um einen Assistenten anzupassen.  \(Eine Liste dieser Modelle finden Sie unter [Entwerfen eines Assistenten](../ide/designing-a-wizard.md).\) Sie können der Datei **Default.js** des Assistentenprojekts eigene Funktionen hinzufügen.  Um von einer JScript\-Datei aus auf die Eigenschaften und Methoden im Assistentenobjektmodell oder Umgebungsmodell zuzugreifen, stellen Sie dem Objektmodellelement "wizard." bzw. "dte." voran.  
  
 Beispiele:  
  
```  
function CreateCustomProject(strProjectName, strProjectPath)  
{  
   try  
   {  
      var strProjTemplatePath = wizard.FindSymbol('PROJECT_TEMPLATE_PATH');  
var strProjTemplate = '';  
      strProjTemplate = strProjTemplatePath + '\\default.vcproj';  
  
      var Solution = dte.Solution;  
      var strSolutionName = "";  
      if (wizard.FindSymbol("CLOSE_SOLUTION"))  
...  
```  
  
 Wenn Sie im [benutzerdefinierten Assistenten](../ide/custom-wizard.md) auf **Fertig stellen** klicken, lädt der Assistent die Datei **Default.js** in den Ordner **Skriptdateien** im Projektmappen\-Explorer.  Wenn ein Benutzer im Assistenten auf **Fertig stellen** klickt, werden durch diese JScript\-Datei Projekte erstellt sowie Vorlagen gerendert und anschließend der Projektmappe hinzugefügt.  
  
 Die Projektdatei **Default.js** umfasst standardmäßig die folgenden Funktionen:  
  
|Funktionsname|Beschreibung|  
|-------------------|------------------|  
|**AddConfig**|Fügt die Projektkonfigurationen hinzu.  Sie können Compiler\- und Linkereinstellungen angeben.|  
|**AddFilesToCustomProj**|Fügt dem Projekt die angegebenen Dateien hinzu, wenn der Benutzer auf **Fertig stellen** klickt.|  
|**AddFilters**|Fügt dem Projekt die angegebenen Quellfilter hinzu, wenn der Benutzer auf **Fertig stellen** klickt.|  
|**CreateCustomProject**|Erstellt das Projekt am angegebenen Speicherort, wenn der Benutzer auf **Fertig stellen** klickt.|  
|**CreateCustomInfFile**|Erstellt die projektspezifische [Datei "Templates.inf"](../ide/templates-inf-file.md).|  
|**DelFile**|Löscht die angegebene Datei.|  
|**GetTargetName**|Ruft den Namen der angegebenen Datei ab.|  
|**OnFinish**|Wird vom Assistenten aufgerufen, wenn der Benutzer auf **Fertig stellen** klickt, um das Projekt zu erstellen, Dateien und Filter hinzuzufügen, Vorlagen zu rendern und die Konfiguration festzulegen.|  
|**PchSettings**|Legt die vorkompilierten Headereinstellungen fest.  Weitere Informationen finden Sie in der Referenz zu **Common.js** unter [SetCommonPchSettings](../ide/setcommonpchsettings.md).|  
  
 Jeder Assistent verfügt über eine eindeutige Datei **Default.js**. Die Datei enthält TODO\-Anmerkungen, mit deren Hilfe Sie feststellen können, an welchen Stellen die Datei angepasst werden muss.  
  
 Visual C\+\+ umfasst außerdem die Datei [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md), die von allen Assistenten gemeinsam genutzt wird und im Assistentenprojekt enthalten ist.  Sie können die Funktionen in **Common.js** verwenden.  
  
> [!NOTE]
>  Die Datei Common.js enthält für jede Funktion und die zugehörigen Parameter eine Beschreibung.  Weitere Informationen finden Sie in den Kommentaren in **Common.js**.  
  
 Falls Funktionen von Assistentenprojekten gemeinsam genutzt werden sollen, können Sie sie der Datei Common.js hinzufügen.  Dazu erstellen Sie eine eigene Version von Common.js, speichern sie unter einem freigegebenen Pfad und geben anschließend diesen Pfad in der [VSZ\-Datei](../ide/dot-vsz-file-project-control.md) unter SCRIPT\_COMMON\_PATH an.  
  
> [!NOTE]
>  Die in Visual C\+\+ enthaltenen Assistenten verwenden die JScript\-Funktionen in der Datei Common.js.  Wenn Sie diese Funktionen ändern, reagieren die Visual C\+\+\-Assistenten möglicherweise nicht wie erwartet.  
  
 Weitere Informationen zu JScript finden Sie unter [Writing, Compiling, and Debugging JScript Code](assetId:///13e57e7d-4867-4555-b9e4-fc24aa75e628).  
  
## Debuggen von Skript  
 Um Skript in vom Assistenten erstellten HTML\-Dateien zu debuggen, müssen Sie Skriptdebugging aktivieren.  
  
#### So aktivieren Sie das Skriptdebuggen  
  
1.  Klicken Sie in Internet Explorer im Menü **Extras** auf **Internetoptionen**.  
  
2.  Klicken Sie auf die Registerkarte **Erweitert**.  
  
3.  Deaktivieren Sie in der Kategorie **Browsing** das Kontrollkästchen **Skriptdebugging deaktivieren**.  
  
 Auf diese Weise werden common.js und default.js im Fenster **Aktive Dokumente** angezeigt, wenn Sie im Assistenten auf die Schaltfläche Fertig stellen klicken.  
  
## Siehe auch  
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)
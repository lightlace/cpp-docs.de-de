---
title: "JScript-Funktionen f&#252;r C++-Assistenten"
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
  - "JScript-Methoden (Assistent)"
  - "JScript-Methoden (Assistent), Erstellen von C++-Assistenten"
ms.assetid: f3046c56-cf67-4aaa-919e-8c066bfb6760
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# JScript-Funktionen f&#252;r C++-Assistenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

|||  
|-|-|  
|[AddATLSupportToProject](../ide/addatlsupporttoproject.md)|Fügt einem MFC\-Projekt ATL\-Unterstützung hinzu.|  
|[AddCoclassFromFile](../ide/addcoclassfromfile.md)|Rendert eine Vorlagendatei, die eine Co\-Klasse enthält, und fügt sie in die IDL\-Datei des Projekts ein.|  
|[AddCommonConfig](../ide/addcommonconfig.md)|Fügt dem Projekt die Standardkonfigurationen hinzu.|  
|[AddFilesToProject](../ide/addfilestoproject.md)|Fügt dem Projekt alle in der Datei **Templates.inf** aufgelisteten Dateien hinzu.|  
|[AddInterfaceFromFile](../ide/addinterfacefromfile.md)|Rendert eine Vorlagendatei, die eine Schnittstelle enthält, und fügt sie in die IDL\-Datei des Projekts ein.|  
|[CanAddATLClass](../ide/canaddatlclass.md)|Wird vom Assistenten aufgerufen, um zu überprüfen, ob das Projekt mit dem auszuführenden Code\-Assistenten kompatibel ist \(d. h., ob das Projekt eine ATL\-Klasse annehmen kann\).<br /><br /> Der Assistent ruft diese Funktion auf, wenn die [VSZ\-Datei der Projektsteuerung](../ide/dot-vsz-file-project-control.md) den PREPROCESS\_FUNCTION\-Parameter enthält. Er überprüft, ob das [Visual C\+\+ Code Model](assetId:///dd6452c2-1054-44a1-b0eb-639a94a1216b) verfügbar ist.  Wenn das Codemodell nicht verfügbar ist, meldet die Funktion einen Fehler und gibt **false** zurück.|  
|[CanAddClass](../ide/canaddclass.md)|Der Assistent ruft diese Funktion auf, wenn die VSZ\-Datei der Projektsteuerung den **PREPROCESS\_FUNCTION**\-Parameter enthält.<br /><br /> Er überprüft, ob das Visual C\+\+\-Codemodellobjekt verfügbar ist.  Wenn das Codemodell nicht verfügbar ist, meldet die Funktion einen Fehler und gibt **false** zurück.|  
|[CanAddMFCClass](../ide/canaddmfcclass.md)|Wird vom Assistenten aufgerufen, um zu überprüfen, ob das Projekt mit dem auszuführenden Code\-Assistenten kompatibel ist \(d. h., ob das Projekt eine MFC\-Klasse annehmen kann\).<br /><br /> Der Assistent ruft diese Funktion auf, wenn die VSZ\-Datei der Projektsteuerung den **PREPROCESS\_FUNCTION**\-Parameter enthält. Er überprüft, ob das Visual C\+\+\-Codemodellobjekt verfügbar ist.  Wenn das Codemodell nicht verfügbar ist, meldet die Funktion einen Fehler und gibt **false** zurück.|  
|[CanAddNonAttributed](../ide/canaddnonattributed.md)|Gibt an, ob das Projekt sowohl attributierte als auch nicht attributierte ATL\-Objekte unterstützt.|  
|[CanUseFileName](../ide/canusefilename.md)|Überprüft, ob eine Datei vorhanden ist.  Falls ja, fordert der Assistent den Benutzer auf, den hinzuzufügenden Code mit der vorhandenen Datei zusammenzuführen.|  
|[ConvertProjectToAttributed](../ide/convertprojecttoattributed.md)|Konvertiert ein ATL\-Projekt in ein attributiertes Projekt.|  
|[CreateInfFile](../ide/createinffile.md)|Erstellt die Datei **Templates.inf**.|  
|[CreateProject](../ide/createproject.md)|Erstellt ein C\+\+\-Projekt.|  
|[CreateSafeName](../ide/createsafename.md)|Generiert einen C\+\+\-Anzeigenamen.|  
|[DeleteFile](../ide/deletefile.md)|Löscht die angegebene Datei.|  
|[DoesIncludeExist](../ide/doesincludeexist.md)|Gibt an, ob die Datei eine `#include`\-Anweisung enthält.|  
|[GetCodeForDllCanUnloadNow](../ide/getcodefordllcanunloadnow.md)|Ruft Code ab, der zum Entladen der DLL erforderlich ist.|  
|[GetCodeForDllGetClassObject](../ide/getcodefordllgetclassobject.md)|Ruft den Code für das DLL\-Klassenobjekt ab.|  
|[GetCodeForDllRegisterServer](../ide/getcodefordllregisterserver.md)|Ruft den Code zum Registrieren eines Servers ab.|  
|[GetCodeForDllUnregisterServer](../ide/getcodefordllunregisterserver.md)|Ruft den Code zum Aufheben der Registrierung eines Servers ab.|  
|[GetCodeForExitInstance](../ide/getcodeforexitinstance.md)|Hilfsfunktion zum Abrufen des Textes für `ExitInstance`.|  
|[GetCodeForInitInstance](../ide/getcodeforinitinstance.md)|Hilfsfunktion zum Abrufen des Textes für [InitInstance](../Topic/CWinApp::InitInstance.md).|  
|[GetExportPragmas](../ide/getexportpragmas.md)|Ruft die Pragmas zum Exportieren von Funktionen ab.|  
|[GetInterfaceClasses](../ide/getinterfaceclasses.md)|Gibt das einer Schnittstelle zugehörige `VCCodeClass`\-Objekt zurück.|  
|[GetInterfaceType](../ide/getinterfacetype.md)|Gibt den Schnittstellentyp zurück \(z. B. **custom**, **dual**, **dispinterface**, **oleautomation**\).|  
|[GetMaxID](../ide/getmaxid.md)|Gibt die höchste `dispid` der Member dieser Schnittstelle sowie aller zugehörigen Basisschnittstellen zurück.|  
|[GetMemberfunction](../ide/getmemberfunction.md)|Gibt ausgehend vom angegebenen Namen ein Funktionsobjekt zurück.|  
|[GetProjectFile](../ide/getprojectfile.md)|Gibt den Dateinamen der pro Projekt gültigen Dateitypen an \(**.rc**, **.idl** usw.\).|  
|[GetProjectPath](../ide/getprojectpath.md)|Gibt den Verzeichnispfad des Projekts zurück.|  
|[GetRuntimeErrorDesc](../ide/getruntimeerrordesc.md)|Gibt eine Beschreibung des Typs der Ausnahme zurück.|  
|[GetUniqueFileName](../ide/getuniquefilename.md)|Gibt einen eindeutigen Dateinamen zurück.|  
|[IncludeCodeElementDeclaration](../ide/includecodeelementdeclaration.md)|Fügt `strInFile` die **include**\-Anweisung hinzu, wobei auch der Header mit dem implementierten `strCodeElemName` eingefügt wird, falls das Projekt einen solchen Header enthält.|  
|[InsertIntoFunction](../ide/insertintofunction.md)|Hilfsfunktion, die in `AddATLSupportToProject` aufgerufen wird, um Code in `InitInstance` einzufügen.|  
|[IsATLProject](../ide/isatlproject.md)|Gibt an, ob ein Projekt ATL\-basiert ist.|  
|[IsAttributedProject](../ide/isattributedproject.md)|Gibt an, ob ein Projekt attributiert ist.|  
|[IsMFCProject](../ide/ismfcproject.md)|Überprüft, ob ein Projekt MFC\-basiert ist.|  
|[LineBeginsWith](../ide/linebeginswith.md)|Hilfsfunktion, die in `InsertIntoFunction` aufgerufen wird, um zu ermitteln, ob eine Zeile mit einer bestimmten Zeichenfolge beginnt.|  
|[OffsetToLineNumber](../ide/offsettolinenumber.md)|Sucht die Zeilennummer einer bestimmten Position in einem Funktionsrumpf.|  
|[OnWizFinish](../ide/onwizfinish.md)|Wird vom HTML\-Skript des Assistenten aufgerufen, wenn der Benutzer auf **Fertig stellen** klickt.  Ruft die **Finish**\-Methode der Assistentensteuerung auf.|  
|[RenderAddTemplate](../ide/renderaddtemplate.md)|Rendert eine Vorlagendatei und fügt sie optional dem Projekt hinzu.|  
|[SetCommonPchSettings](../ide/setcommonpchsettings.md)|Richtet den vorkompilierten Header für das Projekt ein.|  
|[SetErrorInfo](../ide/seterrorinfo.md)|Liefert Fehlerinformationen.|  
|[SetFilters](../ide/setfilters.md)|Fügt Quell\-, Include\- und Ressourcenfilter für Projektordner hinzu.|  
|[SetMergeProxySymbol](../ide/setmergeproxysymbol.md)|Wird vom Assistenten aufgerufen, um bei Bedarf das Symbol **\_MERGE\_PROXYSTUB** hinzuzufügen.|  
|[SetNoPchSettings](../ide/setnopchsettings.md)|Richtet die Eigenschaften der Projektkonfiguration ein, wenn kein vorkompilierter Header verwendet wird.|  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)
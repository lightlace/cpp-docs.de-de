---
title: "GetProjectFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetProjectFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProjectFile-Methode"
ms.assetid: e5fdc468-755a-4b4e-81bd-e63881531bed
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# GetProjectFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt den Namen des angegebenen Dateityps zurück.  
  
## Syntax  
  
```  
  
      function GetProjectFile(   
   oProj,   
   strType,   
   bFullPath,   
   bMFC    
);  
```  
  
#### Parameter  
 oProj  
 Das ausgewählte Projekt.  
  
 `strType`  
 Der Typ der abzurufenden Datei, z. B. STDAFX, RC, IDL, CPP, H, ODL oder DEF.  
  
 *bFullPath*  
 Flag, das anzeigt, ob der vollständige Pfadname zurückgegeben werden soll.  
  
 *bMFC*  
 Zeigt an, ob das Projekt ein MFC\-basiertes Projekt ist.  Wenn `strType` den Wert **.cpp** oder **.h** besitzt, wird das Projekt als MFC\-basiert betrachtet.  Andernfalls wird angenommen, dass das Projekt ATL\-basiert ist.  
  
## Rückgabewert  
 Der Dateiname des pro Projekt gültigen Dateityps.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um den Dateinamen des angegebenen Typs im angegebenen Projekt zu ermitteln.  
  
## Beispiel  
  
```  
// The selected MFC project's CPP file is retrieved and   
// assigned to strFileName.  
var strFileName = GetProjectFile(selProj, "CPP", false, true);  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [GetProjectPath](../ide/getprojectpath.md)   
 [GetUniqueFileName](../ide/getuniquefilename.md)
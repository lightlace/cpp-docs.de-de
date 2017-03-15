---
title: "RenderAddTemplate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RenderAddTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RenderAddTemplate-Methode"
ms.assetid: 84c898d6-8676-4ae1-9245-c023e1c9ab92
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# RenderAddTemplate
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rendert eine Vorlagendatei und fügt sie optional dem Projekt hinzu.  
  
## Syntax  
  
```  
  
      function RenderAddTemplate(   
   strTemplateFile,   
   strProjectFile,   
   ProjToAddTo,   
   bOpen    
);  
```  
  
#### Parameter  
 *strTemplateFile*  
 Der Name der Vorlagendatei ohne Pfadangabe, relativ zu **TEMPLATES\_PATH**.  
  
 *strProjectFile*  
 Der Name der neu erstellten Datei.  Diese Zeichenfolge kann den Pfad enthalten, allerdings nur relativ zu **PROJECT\_PATH**.  
  
 *ProjToAddTo*  
 Das Projektobjekt.  Geben Sie den Projektnamen an, falls die erstellte Datei dem Projekt hinzugefügt werden soll; ignorieren Sie andernfalls die Angabe, oder geben Sie **false** an, wenn die Datei nicht dem Projekt hinzugefügt wird.  
  
 *bOpen*  
 Falls **true**, öffnen Sie die Datei im Standard\-Editor, nachdem Sie sie dem Projekt hinzugefügt haben.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um eine Vorlagendatei zu rendern und sie optional dem Projekt hinzuzufügen.  
  
## Beispiel  
  
```  
// Declare the project path and the template path.  
var strProjectPath = wizard.FindSymbol("PROJECT_PATH");  
var strTemplatePath = wizard.FindSymbol("TEMPLATES_PATH");  
// Declare the template header and implementation files.  
var strTemplateHeader = wizard.FindSymbol("TEMPLATE_HEADER");  
var strTemplateImpl = wizard.FindSymbol("TEMPLATE_IMPL");  
// Render the template strTemplateHeader and open it in the editor.  
RenderAddTemplate(strTemplateHeader, strHeaderFile, selProj, true);   
// Render the template strTemplateImpl, but do not open it   
// in the editor.  
RenderAddTemplate(strTemplateImpl, strImplFile, selProj, false);  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)
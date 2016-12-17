---
title: "CreateInfFile"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CreateInfFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInfFile-Methode"
ms.assetid: 941ea2ce-db10-428e-b423-8dc2a7e825cf
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CreateInfFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt die Datei **Templates.inf** des Assistenten.  
  
## Syntax  
  
```  
  
function CreateInfFile( );  
  
```  
  
## Rückgabewert  
 Die Vorlagendatei des Assistenten.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um von **Templatesinf.txt**, einer temporären Textdatei, die entsprechend den vom Benutzer ausgewählten Optionen im temporären Verzeichnis erstellt wird, die Datei **Templates.inf** des Assistenten zu bilden.  **Templates.inf** enthält die Liste der Dateinamen, die der Assistent erstellt.  Weitere Informationen finden Sie unter [Vorlagendateien](../ide/template-files.md).  
  
 Wenn die Datei **Templatesinf.txt** durch diese Funktion nicht im temporären Verzeichnis erstellt werden kann, erscheint eine Fehlermeldung.  
  
## Beispiel  
 Siehe [AddFilesToProject](../ide/addfilestoproject.md).  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [AddFilesToProject](../ide/addfilestoproject.md)   
 [SetFilters](../ide/setfilters.md)   
 [AddFilesToProject](../ide/addfilestoproject.md)
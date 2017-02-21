---
title: "OffsetToLineNumber | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OffsetToLineNumber"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OffsetToLineNumber-Funktion"
ms.assetid: ac7e3c22-6b3b-432c-85cc-b50bbef9ce8c
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# OffsetToLineNumber
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird von [InsertIntoFunction](../ide/insertintofunction.md) aufgerufen, um einen Index in einem Funktionsrumpf in eine Zeilennummer zu konvertieren.  
  
## Syntax  
  
```  
  
      function OffsetToLineNumber(   
   strString,   
   nPos    
);  
```  
  
#### Parameter  
 `strString`  
 Die Zeichenfolge, die den Funktionsrumpf enthält.  Der Funktionsrumpf ist eine aus mehreren Zeilen bestehende Zeichenfolge, deren Zeilen durch CR\-LF\-Zeichenpaare \(Wagenrücklauf\/Zeilenvorschub\-Zeichenpaare\) getrennt sind.  
  
 `nPos`  
 Eine Position innerhalb der Zeichenfolge.  
  
## Rückgabewert  
 Die Zeile innerhalb des Funktionsrumpfes, in der sich `nPos` befindet.  Die erste Zeile der Funktion hat die Nummer 1 \(nicht 0\).  
  
## Hinweise  
 Sucht die Zeilennummer einer bestimmten Position in einem Funktionsrumpf.  
  
 Diese Funktion wird von `InsertIntoFunction` aufgerufen, um den Index, der sich bei `nPos` in einem Funktionsrumpf befindet, in eine Zeilennummer zu konvertieren.  
  
## Beispiel  
  
```  
strString = "function DelFile(fso,  
 strWizTempFile)\r\n{\r\n\ttry\r\n\t{\r\nif   
(fso.FileExists(strWizTempFile))\r\nreturn true;\r\n";  
  
nLine =  OffsetToLineNumber(strString, 60);  
  
// The return value for the above is 5, because character 60 in the string   
// occurs in the 5th line within the string.  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [LineBeginsWith](../ide/linebeginswith.md)
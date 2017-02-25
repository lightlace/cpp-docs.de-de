---
title: "GetRuntimeErrorDesc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetRuntimeErrorDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ConversionError-Methode"
  - "GetRuntimeErrorDesc-Methode"
  - "RangeError-Methode"
  - "ReferenceError-Methode"
  - "RegExpError-Methode"
  - "SyntaxError-Methode"
  - "TypeError-Methode"
  - "URIError-Methode"
ms.assetid: d56fdd2e-6ad0-4c49-9e98-bcf0105e1b12
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# GetRuntimeErrorDesc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt eine Beschreibung des Ausnahmetyps zurück.  
  
## Syntax  
  
```  
  
      function GetRuntimeErrorDesc(   
   strRuntimeErrorName    
);  
```  
  
#### Parameter  
 *strRuntimeErrorName*  
 Der Name des aufgetretenen Ausnahmetyps.  
  
## Rückgabewert  
 Eine Beschreibung des Ausnahmetyps.  
  
## Hinweise  
 Gibt eine Beschreibung des Ausnahmetyps zurück.  Einer der folgenden Ausnahmetypen ist möglich:  
  
|Ausnahmetypen|Beschreibung|  
|-------------------|------------------|  
|ConversionError|Tritt immer dann auf, wenn versucht wird, ein Objekt in etwas zu konvertieren, in das es nicht konvertiert werden kann.|  
|RangeError|Tritt auf, wenn eine Funktion mit einem Argument angegeben wird, das außerhalb des zulässigen Bereichs liegt.  Beispielsweise tritt dieser Fehler auf, wenn Sie versuchen, ein `Array`\-Objekt mit einer Länge zu erstellen, die keine gültige positive ganze Zahl ist.|  
|ReferenceError|Tritt auf, wenn ein ungültiger Verweis entdeckt wurde.  Der Fehler wird beispielsweise ausgegeben, wenn ein erwarteter Verweis den Wert **NULL** hat.|  
|RegExpError|Tritt auf, wenn bei einem regulären Ausdruck ein Kompilierungsfehler auftritt.  Nachdem der reguläre Ausdruck kompiliert wurde, kann dieser Fehler nicht mehr auftreten.  Beispielsweise tritt der Fehler auf, wenn ein regulärer Ausdruck mit einem Muster deklariert wird, das eine ungültige Syntax aufweist, oder wenn er mit anderen Flags als *i*, *g* oder *m* deklariert wird bzw. das gleiche Flag mehr als einmal enthält.|  
|SyntaxError|Tritt auf, wenn Quelltext analysiert wird und nicht die richtige Syntax aufweist.  Beispielsweise tritt der Fehler auf, wenn die `eval`\-Funktion mit einem Argument aufgerufen wird, das kein gültiger Programmtext ist.|  
|TypeError|Tritt immer dann auf, wenn der tatsächliche Typ eines Operanden nicht mit dem erwarteten Typ übereinstimmt.  Ein Beispiel für das Auftreten dieses Fehlers ist ein Funktionsaufruf für etwas, das kein Objekt ist oder den Aufruf nicht unterstützt.|  
|URIError|Tritt auf, wenn ein ungültiger Uniform Resource Indicator \(URI\) entdeckt wird.  Beispielsweise tritt dieser Fehler auf, wenn in einer zu codierenden oder zu decodierenden Zeichenfolge ein ungültiges Zeichen gefunden wird.|  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)
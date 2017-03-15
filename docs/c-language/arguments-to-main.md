---
title: "Argumente f&#252;r &quot;main&quot; | Microsoft Docs"
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
ms.assetid: 39824fef-05ad-461d-ae82-49447dda8060
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Argumente f&#252;r &quot;main&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 2.1.2.2.1** Die Semantik der Argumente für "main"  
  
 In Microsoft C wird die Funktion, die beim Programmstart aufgerufen wird, als **main** bezeichnet.  Für **main** wurde kein Prototyp deklariert, und für die Definition können null, zwei oder drei Parameter verwendet werden:  
  
```  
int main( void )  
int main( int argc, char *argv[] )  
int main( int argc, char *argv[], char *envp[] )  
```  
  
 Die dritte Zeile oben, in der **main** drei Parameter akzeptiert, ist eine Microsoft\-Erweiterung zum ANSI C\-Standard.  Der dritte Parameter, **envp**, ist ein Array von Zeigern auf Umgebungsvariablen.  Das **envp**\-Array wird durch einen Null\-Zeiger beendet.  Weitere Informationen zu **main** und **envp** erhalten Sie unter [Die Hauptfunktion und die Programmausführung](../c-language/main-function-and-program-execution.md).  
  
 Die Variable **argc** hat niemals einen negativen Wert.  
  
 Das Zeichenfolgenarray endet mit **argv\[argc\]**, das einen NULL\-Zeiger enthält.  
  
 Alle Elemente des Arrays **argv** sind Zeiger auf Zeichenfolgen.  
  
 Ein Programm, das ohne Befehlszeilenargumente aufgerufen wird, erhält den Wert eins für **argc**, während der Name der ausführbaren Datei in **argv\[0\]** platziert wird. \(In MS\-DOS\-Versionen vor 3.0 ist der Name der ausführbaren Datei nicht verfügbar.  Der Buchstabe "C" wird in **argv\[0\]** platziert.\) Zeichenfolgen, auf die durch **argv\[1\]** über **argv\[argc – 1\]** gezeigt wird, stellen Programmparameter dar.  
  
 Die Parameter **argc** und **argv** sind änderbar und legen die Werte der letzten Speicherung zwischen Programmstart und Programmbeendigung fest.  
  
## Siehe auch  
 [Umgebung](../c-language/environment.md)
---
title: "naked (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "naked_cpp"
  - "naked"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], naked"
  - "naked __declspec-Schlüsselwort"
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# naked (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Für die Funktionen, die mit dem `naked`\-Attribut deklariert werden, generiert der Compiler Code ohne Prolog\- und Epilogcode.  Sie können diese Funktion verwenden, um eigene Prolog\-\/Epilogcodesequenzen mithilfe von Inlineassemblercode zu schreiben.  Naked\-Funktionen sind vor allem beim Schreiben von virtuellen Gerätetreibern hilfreich.  Beachten Sie, dass das `naked`\-Attribut nur für x86 und ARM gültig und nicht für [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] verfügbar ist.  
  
## Syntax  
  
```  
__declspec(naked) declarator  
```  
  
## Hinweise  
 Da das `naked`\-Attribut nur für die Definition einer Funktion relevant ist und kein Typmodifizierer ist, müssen naked\-Funktionen eine erweiterte Attributsyntax und das [\_\_declspec](../cpp/declspec.md)\-Schlüsselwort verwenden.  
  
 Der Compiler kann keine Inlinefunktion für eine Funktion generieren, die mit dem naked\-Attribut gekennzeichnet ist, selbst wenn die Funktion auch mit dem [\_\_forceinline](../misc/inline-inline-forceinline.md)\-Schlüsselwort gekennzeichnet ist.  
  
 Der Compiler gibt einen Fehler aus, wenn das `naked`\-Attribut auf einen anderen Wert als die Definition einer Nichtmembermethode angewendet wird.  
  
## Beispiele  
 Dieser Code definiert eine Funktion mit dem `naked`\-Attribut:  
  
```  
__declspec( naked ) int func( formal_parameters ) {}  
```  
  
 Oder auch:  
  
```  
#define Naked __declspec( naked )  
Naked int func( formal_parameters ) {}  
```  
  
 Das `naked`\-Attribut wirkt sich nur auf die Codegenerierung des Compilers für die Prolog\- und Epilogsequenzen der Funktion aus.  Es hat keine Auswirkungen auf den Code, der zum Aufrufen solcher Funktionen generiert wird.  Daher gilt das `naked`\-Attribut nicht als Teil des Typs der Funktion, und Funktionszeiger dürfen nicht das `naked`\-Attribut enthalten.  Darüber hinaus kann das `naked`\-Attribut nicht auf eine Datendefinition angewendet werden.  Beispielsweise wird mit diesem Codebeispiel ein Fehler generiert:  
  
```  
__declspec( naked ) int i;       // Error--naked attribute not  
                                 // permitted on data declarations.  
```  
  
 Das `naked`\-Attribut ist nur für die Funktionsdefinition relevant und kann nicht im Funktionsprototyp angegeben werden.  Beispielsweise wird mit dieser Deklaration ein Compilerfehler generiert:  
  
```  
__declspec( naked ) int func();  // Error--naked attribute not   
                                 // permitted on function declarations  
```  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Naked\-Funktionsaufrufe](../cpp/naked-function-calls.md)
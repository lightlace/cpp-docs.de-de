---
title: "C-Zuweisungsoperatoren"
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
  - "C"
helpviewer_keywords: 
  - "%=-Operator"
  - "&=-Operator"
  - "*=-Operator"
  - "/=-Operator"
  - "^=-Operator, Zuweisungsoperatoren"
  - "|=-Operator"
  - "+=-Operator"
  - "<<=-Operator"
  - "=-Operator"
  - "-=-Operator"
  - "=-Operator, Zuweisungsoperatoren"
  - ">>-Operator"
  - ">>=-Operator"
  - "Zuweisungskonvertierungen"
  - "Zuweisungsoperatoren"
  - "Zuweisungsoperatoren, C"
  - "Bitweiser AND-Zuweisungsoperator"
  - "Divisionszuweisungsoperator"
  - "Multiplikationszuweisungsoperator (*=)"
  - "Operator >>=, C-Zuweisungsoperatoren"
  - "Operatoren [C], Zuweisung"
  - "Operatoren [C], Schiebeoperatoren"
  - "Restzuweisungsoperator (%=)"
  - "Rechtsschiebeoperatoren"
  - "Schiebeoperatoren, Rechts"
  - "Subtraktionsoperator"
  - "Subtraktionsoperator, C-Zuweisungsoperatoren"
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# C-Zuweisungsoperatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Zuweisungsvorgang weist den Wert des rechten Operanden dem Speicherort zu, der vom linken Operanden benannt wird.  Deshalb muss der linke Operand eines Zuweisungsvorgangs ein änderbarer l\-Wert sein.  Nach der Zuweisung hat ein Zuweisungsausdruck den Wert des linken Operanden, ist jedoch kein l\-Wert.  
  
 **Syntax**  
  
 *assignment\-expression*:  
 *conditional\-expression*  
  
 *unary\-expression assignment\-operator assignment\-expression*  
  
 *assignment\-operator*: Einer von  
 **\= \*\=** `/=` `%=` `+=` **–\= \<\<\= \>\>\= &\=** `^=` `|=`  
  
 Die Zuweisungsoperatoren in C können Werte in einem einzelnen Vorgang transformieren und zuweisen.  C stellt die folgenden Zuweisungsoperatoren bereit:  
  
|Operator|Vorgang ausgeführt|  
|--------------|------------------------|  
|**\=**|Einfache Zuweisung|  
|**\*\=**|Multiplikationszuweisung|  
|`/=`|Divisionszuweisung|  
|`%=`|Restzuweisung|  
|`+=`|Additionszuweisung|  
|**–\=**|Subtraktionszuweisung|  
|**\<\<\=**|Left Shift\-Zuweisung|  
|**\>\>\=**|Right Shift\-Zuweisung|  
|**&\=**|Bitweise AND\-Zuweisung|  
|`^=`|Bitweise exklusive OR\-Zuweisung|  
|`&#124;=`|Bitweise inklusive OR\-Zuweisung|  
  
 In der Zuweisung wird der Typ des rechten Werts in den Typ des linken Werts konvertiert, und der Wert wird im linken Operanden gespeichert, nachdem die Zuweisung stattgefunden hat.  Der linke Operand darf kein Array, keine Funktion und keine Konstante sein.  Der bestimmte Konvertierungspfad, der von zwei Typen abhängt, wird ausführlich in [Typkonvertierungen](../c-language/type-conversions-c.md) erläutert.  
  
## Siehe auch  
 [Zuweisungsoperatoren](../cpp/assignment-operators.md)
---
title: "C-Ganzzahlkonstanten"
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
  - "Ganzzahlkonstanten"
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# C-Ganzzahlkonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine "Ganzzahlkonstante" ist eine dezimale \(Basis 10\), oktale \(Basis 8\) oder hexadezimale Zahl \(Basis 16\), die einen ganzzahligen Wert darstellt.  Verwenden Sie ganzzahlige Konstanten, um ganzzahlige Werte darzustellen, die nicht geändert werden können.  
  
## Syntax  
 *integer\-constant*:  
 *decimal\-constant integer\-suffix*  opt  
  
 *octal\-constant integer\-suffix*  opt  
  
 *hexadecimal\-constant integer\-suffix*  opt  
  
 *decimal\-constant*:  
 *nonzero\-digit*  
  
 *decimal\-constant digit*  
  
 *octal\-constant*:  
 **0**  
  
 *octal\-constant octal\-digit*  
  
 *hexadecimal\-constant*:  
 **0x**  *hexadecimal\-digit*  
  
 **0X**  *hexadecimal\-digit*  
  
 *hexadecimal\-constant hexadecimal\-digit*  
  
 *nonzero\-digit*: one of  
 **1 2 3 4 5 6 7 8 9**  
  
 *octal\-digit*: one of  
 **0 1 2 3 4 5 6 7**  
  
 *hexadecimal\-digit*: one of  
 **0 1 2 3 4 5 6 7 8 9**  
  
 **a b c d e f**  
  
 **A B C D E F**  
  
 *integer\-suffix*:  
 *unsigned\-suffix long\-suffix*  opt  
  
 *long\-suffix unsigned\-suffix*  opt  
  
 *unsigned\-suffix*: one of  
 **u U**  
  
 *long\-suffix*: one of  
 **l L**  
  
 *64\-bit integer\-suffix*:  
 **i64**  
  
 Ganzzahlige Konstanten sind positiv, es sei denn, ihnen wird ein Minuszeichen \(**–**\) vorangestellt.  Das Minuszeichen wird als unärer arithmetischer Negationsoperator interpretiert. \(Weitere Informationen über diesen Operator finden Sie auf der Seite über [unäre arithmetische Operatoren](../c-language/unary-arithmetic-operators.md).\)  
  
 Wenn eine ganzzahlige Konstante mit **0x** oder **0X** beginnt, ist sie hexadezimal.  Wenn sie mit der Ziffer **0** beginnt, ist sie oktal.  Andernfalls wird davon ausgegangen, dass es sich hierbei um ein Dezimal handelt.  
  
 Die nachfolgenden Zeilen sind identisch:  
  
```  
0x1C   /* = Hexadecimal representation for decimal 28 */  
034    /* = Octal representation for decimal 28 */  
```  
  
 Die Ziffern einer ganzzahligen Konstante können nicht durch Leerzeichen getrennt werden.  In diesen Beispielen werden gültige dezimale, oktale und hexadezimale Konstanten veranschaulicht.  
  
```  
/* Decimal Constants */  
10  
132  
32179  
  
/* Octal Constants */  
012  
0204  
076663  
  
/* Hexadecimal Constants */  
0xa or 0xA  
0x84  
0x7dB3 or 0X7DB3  
```  
  
## Siehe auch  
 [C\-Konstanten](../c-language/c-constants.md)
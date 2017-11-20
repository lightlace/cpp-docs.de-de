---
title: C-Ganzzahlkonstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 20025ae47491084436864481357125e741ccc486
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="c-integer-constants"></a>C-Ganzzahlkonstanten
Eine "Ganzzahlkonstante" ist eine dezimale (Basis 10), oktale (Basis 8) oder hexadezimale Zahl (Basis 16), die einen ganzzahligen Wert darstellt. Verwenden Sie ganzzahlige Konstanten, um ganzzahlige Werte darzustellen, die nicht geändert werden können.  
  
## <a name="syntax"></a>Syntax  
 *integer-constant*:  
 *decimal-constant integer-suffix*-Opt  
  
 *octal-constant integer-suffix*-Opt  
  
 *hexadecimal-constant integer-suffix*-Opt  
  
 *decimal-constant*:  
 *nonzero-digit*  
  
 *decimal-constant digit*  
  
 *octal-constant*:  
 **0**  
  
 *octal-constant octal-digit*  
  
 *hexadecimal-constant*:  
 **0x** *hexadecimal-digit*  
  
 **0X** *hexadecimal-digit*  
  
 *hexadecimal-constant hexadecimal-digit*  
  
 *nonzero-digit*: eines der folgenden Zeichen  
 **1 2 3 4 5 6 7 8 9**  
  
 *octal-digit*: eines der folgenden Zeichen  
 **0 1 2 3 4 5 6 7**  
  
 *hexadecimal-digit*: eines der folgenden Zeichen  
 **0 1 2 3 4 5 6 7 8 9**  
  
 **a b c d e f**  
  
 **A B C D E F**  
  
 *integer-suffix*:  
 *unsigned-suffix long-suffix*-Opt  
  
 *long-suffix unsigned-suffix*-Opt  
  
 *unsigned-suffix*: eines der folgenden Zeichen  
 **u U**  
  
 *long-suffix*: eines der folgenden Zeichen  
 **l L**  
  
 *64-bit integer-suffix*:  
 **i64**  
  
 Ganzzahlige Konstanten sind positiv, es sei denn, ihnen wird ein Minuszeichen (**-**) vorangestellt. Das Minuszeichen wird als unärer arithmetischer Negationsoperator interpretiert. (Weitere Informationen zu diesen Operator finden Sie auf der Seite [Unäre arithmetische Operatoren](../c-language/unary-arithmetic-operators.md).)  
  
 Wenn eine ganzzahlige Konstante mit **0x** oder **0X** beginnt, ist sie hexadezimal. Wenn sie mit der Ziffer **0** beginnt, ist sie oktal. Andernfalls wird davon ausgegangen, dass es sich hierbei um ein Dezimal handelt.  
  
 Die nachfolgenden Zeilen sind identisch:  
  
```  
0x1C   /* = Hexadecimal representation for decimal 28 */  
034    /* = Octal representation for decimal 28 */  
```  
  
 Die Ziffern einer ganzzahligen Konstante können nicht durch Leerzeichen getrennt werden. In diesen Beispielen werden gültige dezimale, oktale und hexadezimale Konstanten veranschaulicht.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [C-Konstanten](../c-language/c-constants.md)
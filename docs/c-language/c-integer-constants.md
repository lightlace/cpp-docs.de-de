---
title: C-Ganzzahlkonstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 02/01/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c23e90d235e1ad2a8cca577c5cfbf2be55b52b6
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
# <a name="c-integer-constants"></a>C-Ganzzahlkonstanten

Eine "Ganzzahlkonstante" ist eine dezimale (Basis 10), oktale (Basis 8) oder hexadezimale Zahl (Basis 16), die einen ganzzahligen Wert darstellt. Verwenden Sie ganzzahlige Konstanten, um ganzzahlige Werte darzustellen, die nicht geändert werden können.

## <a name="syntax"></a>Syntax

*integer-constant*:  
&nbsp;&nbsp;*decimal-constant* *integer-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*octal-constant* *integer-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*hexadecimal-constant* *integer-suffix*<sub>opt</sub>  

*decimal-constant*:  
&nbsp;&nbsp;*nonzero-digit*  
&nbsp;&nbsp;*decimal-constant* *digit*  

*octal-constant*:  
&nbsp;&nbsp;**0**  
&nbsp;&nbsp;*octal-constant* *octal-digit*  

*hexadecimal-constant*:  
&nbsp;&nbsp;**0x** *hexadecimal-digit*  
&nbsp;&nbsp;**0X** *hexadecimal-digit*  
&nbsp;&nbsp;*hexadecimal-constant* *hexadecimal-digit*  

*nonzero-digit*: eines der folgenden Zeichen  
&nbsp;&nbsp;**1 2 3 4 5 6 7 8 9**  

*octal-digit*: eines der folgenden Zeichen  
&nbsp;&nbsp;**0 1 2 3 4 5 6 7**  

*hexadecimal-digit*: eines der folgenden Zeichen  
&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**  
&nbsp;&nbsp;**a b c d e f**  
&nbsp;&nbsp;**A B C D E F**  
  
*integer-suffix*:  
&nbsp;&nbsp;*unsigned-suffix* *long-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*long-suffix* *unsigned-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*unsigned-suffix* *64-bit-integer-suffix*<sub>opt</sub>

*unsigned-suffix*: eines der folgenden Zeichen  
&nbsp;&nbsp;**u U**  

*long-suffix*: eines der folgenden Zeichen  
&nbsp;&nbsp;**l L**  
  
*64-bit-integer-suffix*: eines von &nbsp;&nbsp;**i64 I64**  

Ganzzahlige Konstanten sind positiv, es sei denn, ihnen wird ein Minuszeichen (**-**) vorangestellt. Das Minuszeichen wird als unärer arithmetischer Negationsoperator interpretiert. (Weitere Informationen zu diesen Operator finden Sie auf der Seite [Unäre arithmetische Operatoren](../c-language/unary-arithmetic-operators.md).)

Wenn eine ganzzahlige Konstante mit **0x** oder **0X** beginnt, ist sie hexadezimal. Wenn sie mit der Ziffer **0** beginnt, ist sie oktal. Andernfalls wird davon ausgegangen, dass es sich hierbei um ein Dezimal handelt.

Die nachfolgenden Zeilen sind identisch:

```C
0x1C   /* = Hexadecimal representation for decimal 28 */
034    /* = Octal representation for decimal 28 */
```

Die Ziffern einer ganzzahligen Konstante können nicht durch Leerzeichen getrennt werden. In diesen Beispielen werden gültige dezimale, oktale und hexadezimale Konstanten veranschaulicht.

```C
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

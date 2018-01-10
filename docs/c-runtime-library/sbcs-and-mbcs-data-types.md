---
title: SBCS- und MBCS-Datentypen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MBCS
- SBCS
dev_langs: C++
helpviewer_keywords:
- SBCS and MBCS data types
- data types [C], MBCS and SBCS
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c54b6e9716e7f0aee9a0b211148b76804d9520bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sbcs-and-mbcs-data-types"></a>SBCS- und MBCS-Datentypen
Jede Microsoft `MBCS`-Laufzeitbibliotheksroutine, die nur ein Multibytezeichen oder ein Byte eines Multibytezeichens verarbeitet, erwartet ein `unsigned int`-Argument (wobei 0x00 <= Zeichenwert <= 0xFFFF und 0x00 <= Bytewert <= 0xFF ). Ein `MBCS`-Routine, die Multibyte-Bytes oder -zeichen in einem Zeichenfolgenkontext verarbeitet, erwartet eine Multibyte-Zeichenfolge, um als `unsigned char`-Zeiger dargestellt zu werden.  
  
> [!CAUTION]
>  Jedes Byte von einem Multibytezeichen kann in einem 8-Bit-`char` dargestellt werden. Jedes Byte eines `SBCS`- oder `MBCS`-Einzelbytezeichen vom Typ `char` mit einem Wert größer als 0x7F ist negativ. Wenn ein solches Zeichen direkt in ein `int` oder ein `long` konvertiert wird, wird das Ergebnis vom Compiler signaturerweitert und kann daher zu unerwartete Ergebnissen führen.  
  
 Aus diesem Grund empfiehlt sich, ein Byte eines Multibytezeichens als 8-Bit-`unsigned char` darzustellen. Um ein negatives Ergebnis zu vermeiden, konvertieren Sie einfach ein Einzelbytezeichen vom Typ `char` in ein `unsigned char`, bevor Sie es in ein `int` oder ein `long` konvertieren.  
  
 Da für einige Funktionen zur Zeichenfolgenbehandlung bei `SBCS` `char*`-Parameter (mit Vorzeichen) erforderlich sind, wird bei der Definition von `_MBCS` eine Compiler-Warnung ausgegeben, die auf einen Typenkonflikt hinweist. Es gibt drei Möglichkeiten, diese Warnung zu vermeiden, die in der Reihenfolge ihrer Effizienz aufgeführt werden:  
  
1.  Verwenden Sie die typsicheren Inlinefunktionen in TCHAR.H. Dies ist das Standardverhalten.  
  
2.  Verwenden Sie die direkten Makros in TCHAR.H, indem Sie in der Befehlszeile `_MB_MAP_DIRECT` definieren. In diesem Fall müssen Sie die Typübereinstimmung manuell sicherstellen. Dies ist die schnellste Methode; sie ist jedoch nicht typsicher.  
  
3.  Verwenden Sie die typsicheren statisch verknüpften Bibliotheksfunktionen in TCHAR.H. Definieren Sie hierzu in der Befehlszeile die Konstante `_NO_INLINING`. Dies ist die langsamste Methode; sie bietet jedoch auch die größte Typsicherheit.  
  
## <a name="see-also"></a>Siehe auch  
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
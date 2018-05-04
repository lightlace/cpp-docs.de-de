---
title: SBCS- und MBCS-Datentypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/11/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- MBCS
- SBCS
dev_langs:
- C++
helpviewer_keywords:
- SBCS and MBCS data types
- data types [C], MBCS and SBCS
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f75999b1436ef350e12c47405cac911367ffda2b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="sbcs-and-mbcs-data-types"></a>SBCS- und MBCS-Datentypen

Jede Microsoft MBCS-Laufzeitbibliotheksroutine, die nur ein Multibytezeichen oder ein Byte eines Multibytezeichens verarbeitet, erwartet ein `unsigned int`-Argument (wobei 0x00 <= Zeichenwert <= 0xFFFF und 0x00 <= Bytewert <= 0xFF ). Eine MBCS-Routine, die Multibyte-Bytes oder -zeichen in einem Zeichenfolgenkontext verarbeitet, erwartet eine Multibyte-Zeichenfolge, um als `unsigned char`-Zeiger dargestellt zu werden.

> [!CAUTION]
> Jedes Byte von einem Multibytezeichen kann in einem 8-Bit-**char** dargestellt werden. Allerdings ist ein SBCS- oder MBCS-Einzelbytezeichen vom Typ **char** mit einem Wert größer als 0x7F negativ. Wenn ein solches Zeichen direkt in einen **int**- oder **long**-Datentyp konvertiert wird, wird das Ergebnis vom Compiler signaturerweitert und kann daher zu unerwarteten Ergebnissen führen.

Aus diesem Grund empfiehlt sich, ein Byte eines Multibytezeichens als 8-Bit-`unsigned char` darzustellen. Zum Vermeiden eines negativen Ergebnisses können Sie alternativ ein Einzelbytezeichen vom Typ **char** in `unsigned char` konvertieren, bevor Sie es in den Datentyp **int** oder **long** konvertieren.

Da für einige SBCS-Funktionen zur Zeichenfolgenbehandlung bei **char\***-Parametern (mit Vorzeichen) erforderlich sind, wird bei der Definition von **_MBCS** eine Compilerwarnung ausgegeben, die auf einen Typenkonflikt hinweist. Es gibt drei Möglichkeiten, diese Warnung zu vermeiden, die in der Reihenfolge ihrer Effizienz aufgeführt werden:

1. Verwenden Sie die typsicheren Inlinefunktionen in TCHAR.H. Dies ist das Standardverhalten.

1. Verwenden Sie die direkten Makros in TCHAR.H, indem Sie **_MB_MAP_DIRECT** in der Befehlszeile definieren. In diesem Fall müssen Sie die Typübereinstimmung manuell sicherstellen. Dies ist die schnellste Methode; sie ist jedoch nicht typsicher.

1. Verwenden Sie die typsicheren statisch verknüpften Bibliotheksfunktionen in TCHAR.H. Definieren Sie hierzu in der Befehlszeile die Konstante **_NO_INLINING**. Dies ist die langsamste Methode; sie bietet jedoch auch die größte Typsicherheit.

## <a name="see-also"></a>Siehe auch

[Internationalisierung](../c-runtime-library/internationalization.md)<br/>
[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>

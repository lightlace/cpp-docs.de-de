---
title: SBCS- und MBCS-Datentypen
ms.date: 04/11/2018
f1_keywords:
- MBCS
- SBCS
helpviewer_keywords:
- SBCS and MBCS data types
- data types [C], MBCS and SBCS
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
ms.openlocfilehash: 2d73155e36909efb1a7261f9fe45c2431525437a
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742907"
---
# <a name="sbcs-and-mbcs-data-types"></a>SBCS- und MBCS-Datentypen

Jede Microsoft MBCS-Laufzeitbibliotheksroutine, die nur ein Multibytezeichen oder ein Byte eines Multibytezeichens verarbeitet, erwartet ein `unsigned int`-Argument (wobei 0x00 <= Zeichenwert <= 0xFFFF und 0x00 <= Bytewert <= 0xFF ). Eine MBCS-Routine, die Multibyte-Bytes oder -zeichen in einem Zeichenfolgenkontext verarbeitet, erwartet eine Multibyte-Zeichenfolge, um als `unsigned char`-Zeiger dargestellt zu werden.

> [!CAUTION]
> Jedes Byte von einem Multibytezeichen kann in einem 8-Bit-**char** dargestellt werden. Allerdings ist ein SBCS- oder MBCS-Einzelbytezeichen vom Typ **char** mit einem Wert größer als 0x7F negativ. Wenn ein solches Zeichen direkt in einen **int**- oder **long**-Datentyp konvertiert wird, wird das Ergebnis vom Compiler signaturerweitert und kann daher zu unerwarteten Ergebnissen führen.

Aus diesem Grund empfiehlt sich, ein Byte eines Multibytezeichens als 8-Bit-`unsigned char` darzustellen. Zum Vermeiden eines negativen Ergebnisses können Sie alternativ ein Einzelbytezeichen vom Typ **char** in `unsigned char` konvertieren, bevor Sie es in den Datentyp **int** oder **long** konvertieren.

Da für einige SBCS-Funktionen zur Zeichenfolgenbehandlung **char**<strong>\*</strong>-Parameter (mit Vorzeichen) erforderlich sind, wird bei der Definition von **_MBCS** eine Compilerwarnung ausgegeben, die auf einen Typenkonflikt hinweist. Es gibt drei Möglichkeiten, diese Warnung zu vermeiden, die in der Reihenfolge ihrer Effizienz aufgeführt werden:

1. Verwenden Sie die typsicheren Inlinefunktionen in TCHAR.H. Dies ist das Standardverhalten.

1. Verwenden Sie die direkten Makros in TCHAR.H, indem Sie **_MB_MAP_DIRECT** in der Befehlszeile definieren. In diesem Fall müssen Sie die Typübereinstimmung manuell sicherstellen. Dies ist die schnellste Methode; sie ist jedoch nicht typsicher.

1. Verwenden Sie die typsicheren statisch verknüpften Bibliotheksfunktionen in TCHAR.H. Definieren Sie hierzu in der Befehlszeile die Konstante **_NO_INLINING**. Dies ist die langsamste Methode; sie bietet jedoch auch die größte Typsicherheit.

## <a name="see-also"></a>Siehe auch

[Internationalisierung](../c-runtime-library/internationalization.md)<br/>
[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>

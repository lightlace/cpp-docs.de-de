---
title: Verwenden von "wmain" anstelle von "main"
ms.date: 11/04/2016
f1_keywords:
- wmain
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
ms.openlocfilehash: f47d7219a54b197ec59f109cf08879774b48e6f7
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857215"
---
# <a name="using-wmain-instead-of-main"></a>Verwenden von "wmain" anstelle von "main"

**Microsoft-spezifisch**

Im Unicode-Programmiermodell können Sie eine breit Zeichen Version der `main`-Funktion definieren. Verwenden Sie **wmain** anstelle von `main`, wenn Sie portablen Code schreiben möchten, der der Unicode-Spezifikation entspricht.

Sie deklarieren die formalen Parameter für **wmain** unter Verwendung eines ähnlichen Formats wie für `main`. Sie können anschließend Breitzeichen-Argumente und optional einen Breitzeichen-Umgebungszeiger übergeben, der auf das Programm verweist. Die *argv* -und die *TVP* -Parameter für **wmain** sind vom Typ `wchar_t*`.

Wenn das Programm eine `main` Funktion verwendet, wird die multibytezeichenumgebung vom Betriebssystem beim Programmstart erstellt. Eine breit Zeichen Kopie der Umgebung wird nur bei Bedarf erstellt (z. b. durch einen Aufrufens der Funktionen [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) oder [_wputenv](../c-runtime-library/reference/putenv-wputenv.md) ). Wenn bereits eine MBCS-Umgebung vorhanden ist, wird beim ersten Aufruf von `_wputenv` oder beim ersten Aufruf von `_wgetenv` eine entsprechende Breitzeichen-Zeichenfolgenumgebung erstellt. Auf diese Umgebung zeigt dann die globale Variable `_wenviron`, die eine Breitzeichenversion der globalen Variablen `_environ` ist. Zu diesem Zeitpunkt sind zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden und werden während der Lebensdauer des Programms vom Betriebssystem verwaltet.

Wenn das Programm eine **wmain** -Funktion verwendet, wird eine MBCS-Umgebung (ASCII) beim ersten `_putenv`-oder `getenv`-aufrufswert erstellt, auf die von der `_environ` globalen Variablen verwiesen wird.

Weitere Informationen zur MBCS-Umgebung finden Sie unter [Einzel Byte-und Multibytezeichensätze](../c-runtime-library/single-byte-and-multibyte-character-sets.md) in der *Lauf Zeit Bibliotheks Referenz.*

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[main: Programmstart](../cpp/main-program-startup.md)
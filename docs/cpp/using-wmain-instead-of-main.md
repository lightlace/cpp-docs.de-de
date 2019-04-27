---
title: Verwenden von "wmain" anstelle von "main"
ms.date: 11/04/2016
f1_keywords:
- wmain
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
ms.openlocfilehash: 8cdc986d1582d2b26f137e3147ce78bc83e9daca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257964"
---
# <a name="using-wmain-instead-of-main"></a>Verwenden von "wmain" anstelle von "main"

## <a name="microsoft-specific"></a>Microsoft-spezifisch

Im Unicode-Programmiermodell, können Sie definieren eine Breitzeichen-Version von der `main` Funktion. Verwendung **Wmain** anstelle von `main` sollten Sie portablen Code schreiben, die der Unicode-Spezifikation entspricht.

Sie deklarieren die formalen Parameter, um **Wmain** mithilfe eines ähnlichen Formats wie für `main`. Sie können anschließend Breitzeichen-Argumente und optional einen Breitzeichen-Umgebungszeiger übergeben, der auf das Programm verweist. Die *Argv* und *Envp* Parameter **Wmain** sind vom Typ `wchar_t*`.

Wenn ein Programm verwendet eine `main` -Funktion, die Multibyte-zeichenumgebung wird vom Betriebssystem beim Programmstart erstellt. Eine breitzeichenkopie der Umgebung ist nur bei Bedarf erstellt (z. B. durch einen Aufruf der [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) oder [_wputenv](../c-runtime-library/reference/putenv-wputenv.md) Funktionen). Wenn bereits eine MBCS-Umgebung vorhanden ist, wird beim ersten Aufruf von `_wputenv` oder beim ersten Aufruf von `_wgetenv` eine entsprechende Breitzeichen-Zeichenfolgenumgebung erstellt. Auf diese Umgebung zeigt dann die globale Variable `_wenviron`, die eine Breitzeichenversion der globalen Variablen `_environ` ist. Zu diesem Zeitpunkt sind zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden und werden während der Lebensdauer des Programms vom Betriebssystem verwaltet.

Auf ähnliche Weise, wenn ein Programm verwendet eine **"wmain"** -Funktion, eine Umgebung MBCS (ASCII) wird erstellt, auf dem ersten Aufruf von `_putenv` oder `getenv`, und verweist die `_environ` globale Variable.

Weitere Informationen zur MBCS-Umgebung finden Sie unter [Einzelbyte- und Mehrbyte-Zeichensätze](../c-runtime-library/single-byte-and-multibyte-character-sets.md) in die *Run-Time Library Reference.*

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[main: Programmstart](../cpp/main-program-startup.md)
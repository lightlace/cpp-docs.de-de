---
title: Unterstützung für die Verwendung von wmain
ms.date: 11/04/2016
f1_keywords:
- wWinMain
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
ms.openlocfilehash: 4af389c00f6065df631f891dadcb0b2f350f984d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491203"
---
# <a name="support-for-using-wmain"></a>Unterstützung für die Verwendung von wmain

Visual C++ unterstützt das Definieren einer **wmain** -Funktion und das Übergeben von breit Zeichen Argumenten an Ihre Unicode-Anwendung. Sie deklarieren die formalen Parameter für **wmain**unter Verwendung eines ähnlichen `main`Formats wie. Sie können anschließend Breitzeichen-Argumente und optional einen Breitzeichen-Umgebungszeiger übergeben, der auf das Programm verweist. Der `argv`-Parameter und der `envp`-Parameter, die auf **wmain** verweisen, sind vom Typ `wchar_t*`. Beispiel:

```cpp
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

> [!NOTE]
> MFC-Unicode- `wWinMain` Anwendungen verwenden als Einstiegspunkt. In diesem Fall `CWinApp::m_lpCmdLine` ist eine Unicode-Zeichenfolge. Stellen Sie sicher, `wWinMainCRTStartup` dass Sie mit der Option [/Entry](../build/reference/entry-entry-point-symbol.md) Linker festlegen.

Wenn in einem Programm eine **main**-Funktion verwendet wird, wird die Multibyte-Zeichenumgebung von der Laufzeitbibliothek beim Programmstart erstellt. Eine Breitzeichen-Kopie der Umgebung wird nur bei Bedarf erstellt (z. B. durch Aufruf der `_wgetenv`-Funktion bzw. der `_wputenv`-Funktion). Wenn bereits eine MBCS `_wputenv`-Umgebung vorhanden ist, wird beim ersten Aufrufe von oder beim ersten-Befehl eine entsprechende breit Zeichen-Zeichen folgen Umgebung erstellt. `_wgetenv` Auf die Umgebung wird dann von der `_wenviron` globalen Variablen verwiesen, die eine breit Zeichen Version `_environ` der globalen Variablen ist. Zu diesem Zeitpunkt sind zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden und werden während der gesamten Lebensdauer des Programms vom Laufzeitsystem verwaltet.

Wenn ein Programm eine **wmain**-Funktion verwendet, wird beim Programmstart eine Breitzeichenumgebung erstellt, auf die die globale Variable `_wenviron` verweist. Beim ersten Aufrufe `_putenv` von oder `getenv` wird eine MBCS-Umgebung (ASCII) erstellt, auf die die `_environ` globale Variable verweist.

## <a name="see-also"></a>Siehe auch

[Unterstützung für Unicode](../text/support-for-unicode.md)<br/>
[Zusammenfassung der Unicode-Programmierung](../text/unicode-programming-summary.md)<br/>
[WinMain-Funktion](/windows/win32/api/winbase/nf-winbase-winmain)

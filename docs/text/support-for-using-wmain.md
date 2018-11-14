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
ms.openlocfilehash: 4dabb10bc4e0a53b0ad86f72ef7ddc5a5559cc21
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331918"
---
# <a name="support-for-using-wmain"></a>Unterstützung für die Verwendung von wmain

Visual C++ unterstützt das Definieren einer **Wmain** -Funktion und die Breitzeichen-Argumente an eine Unicode-Anwendung übergeben. Sie deklarieren die formalen Parameter, um **Wmain**, verwenden ein ähnliches Format `main`. Sie können anschließend Breitzeichen-Argumente und optional einen Breitzeichen-Umgebungszeiger übergeben, der auf das Programm verweist. Der `argv`-Parameter und der `envp`-Parameter, die auf **wmain** verweisen, sind vom Typ `wchar_t*`. Zum Beispiel:

```cpp
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

> [!NOTE]
> MFC-Unicode-Anwendungen verwenden `wWinMain` als Einstiegspunkt. In diesem Fall `CWinApp::m_lpCmdLine` ist eine Unicodezeichenfolge. Achten Sie darauf, dass Sie festzulegende `wWinMainCRTStartup` mit der [/Entry](../build/reference/entry-entry-point-symbol.md) -Linkeroption.

Wenn in einem Programm eine **main**-Funktion verwendet wird, wird die Multibyte-Zeichenumgebung von der Laufzeitbibliothek beim Programmstart erstellt. Eine Breitzeichen-Kopie der Umgebung wird nur bei Bedarf erstellt (z. B. durch Aufruf der `_wgetenv`-Funktion bzw. der `_wputenv`-Funktion). Beim ersten Aufruf von `_wputenv`, oder klicken Sie auf dem ersten Aufruf von `_wgetenv` ist eine MBCS-Umgebung bereits vorhanden, wird eine entsprechende Zeichenfolge mit Breitzeichen-Umgebung erstellt. Die Umgebung zeigt dann durch die `_wenviron` globale Variable, die eine Breitzeichen-Version ist von der `_environ` globale Variable. An diesem Punkt werden zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden und werden vom System zur Laufzeit während der Lebensdauer des Programms beibehalten.

Wenn ein Programm eine **wmain**-Funktion verwendet, wird beim Programmstart eine Breitzeichenumgebung erstellt, auf die die globale Variable `_wenviron` verweist. Eine MBCS (ASCII)-Umgebung wird erstellt, auf dem ersten Aufruf von `_putenv` oder `getenv` und verweist die `_environ` globale Variable.

## <a name="see-also"></a>Siehe auch

[Unterstützung für Unicode](../text/support-for-unicode.md)<br/>
[Zusammenfassung der Unicode-Programmierung](../text/unicode-programming-summary.md)<br/>
[WinMain-Funktion](https://msdn.microsoft.com/library/windows/desktop/ms633559)
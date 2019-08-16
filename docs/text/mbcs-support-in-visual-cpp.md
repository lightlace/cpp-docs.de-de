---
title: MBCS-Unterstützung in Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- tools [C++], MBCS support
- Asian languages [C++]
- Code Editor [C++], MBCS support
- IME [C++]
- Chinese characters [C++]
- Input Method Editor [C++], MBCS
- resource editors [C++], MBCS support
- debugger [C++], MBCS support
- character sets [C++], multibyte
- Japanese characters [C++]
- multibyte characters [C++]
- Kanji character support [C++]
- NMAKE program, MBCS support
- double-byte character sets [C++]
- IME [C++], MBCS
- Input Method Editor [C++]
- MBCS [C++], enabling
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
ms.openlocfilehash: b5f2b6dd56d3a755ee73058c024152e12157a6bd
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501946"
---
# <a name="mbcs-support-in-visual-c"></a>MBCS-Unterstützung in Visual C++

Bei der Ausführung auf einer MBCS-aktivierten Windows-Version ist C++ das visuelle Entwicklungssystem (einschließlich des integrierten Quell Code-Editors, des Debuggers und der Befehlszeilen Tools) MBCS-aktiviert, mit Ausnahme des Arbeitsspeicher Fensters.

Das Arbeitsspeicher Fenster interpretiert Daten Bytes nicht als MBCS-Zeichen, obwohl Sie als ANSI-oder Unicode-Zeichen interpretiert werden können. ANSI-Zeichen sind immer 1 Byte groß, und Unicode-Zeichen sind 2 Bytes groß. Bei MBCS können Zeichen 1 oder 2 Bytes groß sein, und ihre Interpretation hängt davon ab, welche Codepage verwendet wird. Aus diesem Grund ist es für das Arbeitsspeicher Fenster schwierig, MBCS-Zeichen zuverlässig anzuzeigen. Das Fenster "Arbeitsspeicher" weiß nicht, welches Byte den Anfang eines Zeichens ist. Der Entwickler kann die Byte Werte im Arbeitsspeicher Fenster anzeigen und den Wert in Tabellen nachschlagen, um die Zeichen Darstellung zu ermitteln. Dies ist möglich, da der Entwickler die Startadresse einer Zeichenfolge auf Grundlage des Quellcodes kennt.

Visual C++ akzeptiert doppelte Byte Zeichen, wenn dies angebracht ist. Dies schließt Pfadnamen und Dateinamen in Dialogfeldern und Texteinträgen im visuellen C++ Ressourcen-Editor ein (z. b. statischer Text im Dialog-Editor und statische Texteinträge im Symbol-Editor). Außerdem erkennt der Präprozessor einige Doppelbyte-Direktiven – z. b. Dateinamen in `#include` -Anweisungen und als Argumente für die `code_seg` - `data_seg` und-Pragmas. Im Quellcode-Editor werden Doppelbyte Zeichen in Kommentaren und Zeichenfolgenliteralen akzeptiert, aber nicht in C/C++ Language-Elementen (z. b. Variablennamen).

##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a>Unterstützung für den Eingabemethoden-Editor (IME)

Anwendungen, die für ostasiatische Märkte geschrieben wurden und MBCS (z. b. Japan) verwenden, unterstützen normalerweise den Windows-IME für die Eingabe von Einzel-und Doppelbyte Zeichen. Die visuelle C++ Entwicklungsumgebung enthält vollständige Unterstützung für den IME.

Japanische Tastaturen unterstützen Kanji-Zeichen nicht direkt. Der IME konvertiert eine phonetische Zeichenfolge, die in einem der anderen japanischen Alphabete (Romaji, Katakana oder Hiragana) eingegeben wurde, in die möglichen Kanji-Darstellungen. Wenn Mehrdeutigkeiten vorliegen, können Sie aus verschiedenen alternativen auswählen. Wenn Sie das beabsichtigte Kanji-Zeichen ausgewählt haben, übergibt das IME `WM_CHAR` zwei Nachrichten an die steuernde Anwendung.

Der durch die Kombination aus Alt +\` Schlüssel aktivierte IME wird als Satz von Schaltflächen (ein Indikator) und einem Konvertierungs Fenster angezeigt. Die Anwendung positioniert das Fenster an der Text Einfügemarke. Die Anwendung muss- `WM_MOVE` und `WM_SIZE` -Nachrichten verarbeiten, indem das Konvertierungs Fenster neu positioniert wird, sodass es der neuen Position oder Größe des Zielfensters entspricht.

Wenn Sie möchten, dass Benutzer Ihrer Anwendung Kanji-Zeichen eingeben können, muss die Anwendung Windows-IME-Nachrichten verarbeiten. Weitere Informationen zur IME-Programmierung finden Sie unter [Eingabemethoden-Manager](/windows/win32/intl/input-method-manager).

## <a name="visual-c-debugger"></a>Visueller C++ Debugger

Der visuelle C++ Debugger bietet die Möglichkeit, Breakpoints für IME-Nachrichten festzulegen. Außerdem kann im Arbeitsspeicher Fenster Doppelbyte Zeichen angezeigt werden.

## <a name="command-line-tools"></a>Befehlszeilentools

Die visuellen C++ Befehlszeilen Tools, einschließlich des Compilers, NMAKE und des Ressourcen Compilers (RC). EXE), sind MBCS-fähig. Sie können die/c-Option des Ressourcen Compilers verwenden, um beim Kompilieren der Ressourcen der Anwendung die Standard Codepage zu ändern.

Verwenden Sie [#pragma setlocale](../preprocessor/setlocale.md), um das Standard Gebiets Schema zum Zeitpunkt der Kompilierung des Quellcodes zu ändern.

## <a name="graphical-tools"></a>Grafische Tools

Die Visual C++ Windows-basierten Tools, wie z. b. Spy + + und die Tools zur Ressourcen Bearbeitung, unterstützen IME-Zeichen folgen vollständig.

## <a name="see-also"></a>Siehe auch

[Unterstützung von Multibyte-Zeichensätzen (MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
[Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)

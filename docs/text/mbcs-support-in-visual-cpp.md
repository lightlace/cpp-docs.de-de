---
title: MBCS-Unterstützung in Visual C++ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8efb63565ea8c33bfa56de197c0ab6541e43f9f6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379523"
---
# <a name="mbcs-support-in-visual-c"></a>MBCS-Unterstützung in Visual C++

Wenn in einer MBCS-aktivierten Version von Windows ausführen, ist das Visual C++-Entwicklungssystem (einschließlich der integrierten Quellcode-Code-Editor, Debugger und über die Befehlszeile-Tools) MBCS-aktiviert, mit Ausnahme der Fenster "Arbeitsspeicher".

Das Fenster "Arbeitsspeicher" kann nicht als MBCS-Zeichen, Bytes an Daten interpretieren, obwohl diese als ANSI oder Unicode-Zeichen interpretiert werden können. ANSI-Zeichen sind immer 1 Byte Groß und Unicode-Zeichen werden 2 Bytes groß. Mit MBCS-Zeichen können die Größe von 1 oder 2 Bytes werden, und die Interpretation hängt von der Codepage verwendet wird. Aus diesem Grund ist es schwierig für das Fenster "Arbeitsspeicher", um zuverlässig MBCS-Zeichen anzuzeigen. Das Fenster "Arbeitsspeicher" wissen nicht, welche Byte der Start eines Zeichens liegt. Der Entwickler kann die Bytewerte in das Fenster "Arbeitsspeicher" anzeigen und den Wert in Tabellen, um die Darstellung zu bestimmen. Dies ist möglich, da die Startadresse einer Zeichenfolge basierend auf den Quellcode der Entwickler informiert wird.

Visual C++ akzeptiert Double-Byte-Zeichen, wo es angemessen ist. Dies schließt Pfad und Dateinamen in Dialogfeldern und Einträge in der Visual C++ Ressourcen-Editor (z. B. statischer Text in den Dialog-Editor) und statischen Texteinträge in der Symbol-Editor. Der Präprozessor erkennt darüber hinaus einige Doppelbyte-Direktiven, z. B. den Dateinamen in `#include` -Anweisungen, und als Argumente für die `code_seg` und `data_seg` Pragmas. In der Quellcode-Editor werden Double-Byte-Zeichen in Kommentaren und Zeichenfolgenliterale akzeptiert, jedoch nicht in C/C++-Sprachelemente (z. B. Variablennamen).

##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> Unterstützung für den Eingabemethoden-Editor (IME)

Anwendungen, die geschrieben wurden, für die ostasiatischen Märkte, die MBCS (z. B. Japan) in der Regel verwenden den Windows-IME-Unterstützung für beide Single und Double-Byte-Zeichen eingeben. Die Entwicklungsumgebung von Visual C++ enthält die vollständige Unterstützung für den IME.

Japanische Tastaturen unterstützen keine direkte Kanji-Zeichen. Der IME konvertiert phonetische String, als möglichen Kanji-Darstellungen eines der anderen japanische Alphabet (Romaji, Katakana-Zeichen oder Hiragana) eingetragen. Wenn die Mehrdeutigkeit vorliegt, können Sie verschiedene Möglichkeiten zur Auswahl auswählen. Wenn Sie das beabsichtigte Kanji Zeichen ausgewählt haben, der IME übergibt zwei `WM_CHAR` Nachrichten an die Anwendung steuern.

Der IME aktiviert, indem die ALT-Taste +\` Tastenkombination, die als eine Reihe von Schaltflächen (eine Indicator) und eine Konvertierungsfenster angezeigt wird. Im Fenster auf der die Einfügemarke positioniert. Die Anwendung muss behandeln `WM_MOVE` und `WM_SIZE` Nachrichten durch Neupositionieren der Konvertierung-Fenster, um die neue Position und Größe des Zielfensters entsprechen.

Wenn Sie die Benutzer der Anwendung, um die Möglichkeit haben, Kanji Zeichen eingeben möchten, muss die Anwendung Windows IME behandeln. Weitere Informationen zu IME-Programmierung, finden Sie unter [Eingabe-Methodenmanager](/windows/desktop/intl/input-method-manager).

## <a name="visual-c-debugger"></a>Visual C++-Debugger

Visual C++-Debugger ermöglicht das Festlegen von Haltepunkten für den IME-Nachrichten. Darüber hinaus kann das Fenster "Arbeitsspeicher" Double-Byte-Zeichen anzeigen.

## <a name="command-line-tools"></a>Befehlszeilentools

Die Visual C++-Befehlszeilentools, einschließlich der Compiler, NMAKE und den Ressourcencompiler (RC. (EXE), MBCS-aktiviert ist. Sie können der Ressourcencompiler/c-Option verwenden, die Standardcodepage zu ändern, wenn die Ressourcen der Anwendung zu kompilieren.

Um das Standardgebietsschema beim Kompilieren des Quellcodes zu ändern, verwenden [#pragma Setlocale](../preprocessor/setlocale.md).

## <a name="graphical-tools"></a>Grafische Tools

Die Visual C++-Windows-basierte Tools, z. B. Spy++ und die Ressource, die Tools zum Bearbeiten unterstützen vollständig IME-Zeichenfolgen.

## <a name="see-also"></a>Siehe auch

[Unterstützung von Multibyte-Zeichensätzen (MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
[Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)
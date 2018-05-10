---
title: MBCS-Unterstützung in Visual C++ | Microsoft Docs
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41d075edb01fc139660d8e72a7fe53f03ee9e80b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="mbcs-support-in-visual-c"></a>MBCS-Unterstützung in Visual C++
Bei der Ausführung unter einer MBCS-aktivierten Version von Windows ist die Visual C++-Entwicklungssystem (einschließlich der integrierten Quellcode-Editors, Debuggers und der über die Befehlszeile mit Tools) MBCS-aktiviert, davon ausgenommen sind die Fenster "Arbeitsspeicher".  
  
 Das Fenster "Arbeitsspeicher" interpretiert Datenbytes als MBCS-Zeichen nicht, obwohl diese als ANSI- oder Unicode-Zeichen interpretiert werden können. ANSI-Zeichen sind immer 1 Byte Groß und Unicode-Zeichen 2 Byte lang. Mit MBCS Zeichen kann es sich um 1 oder 2 Bytes Groß und deren Interpretation hängt von der Codepage verwendet wird. Aus diesem Grund ist es schwierig, für das Fenster "Arbeitsspeicher", um zuverlässig MBCS-Zeichen anzuzeigen. Das Fenster "Arbeitsspeicher" wissen nicht, welche Byte der Start eines Zeichens ist. Der Entwickler kann Byte-Werten im Fenster "Arbeitsspeicher" anzeigen und suchen Sie den Wert in den Tabellen, um zu bestimmen, die Darstellung von Zeichen. Dies ist möglich, da die Startadresse einer Zeichenfolge basierend auf den Quellcode der Entwickler informiert wird.  
  
 Visual C++ akzeptiert Doppelbyte-Zeichen an, wo es dazu geeignet ist. Dies schließt Pfad und Dateinamen in Dialogfeldern und Einträge in der Visual C++ Ressourcen-Editor (z. B. statischer Text in den Dialog-Editor) und statischen Texteinträge in der Symbol-Editor. Der Präprozessor erkennt außerdem einige Doppelbyte-Direktiven – z. B. Dateinamen in `#include` -Anweisungen und als Argumente für die **Code_seg** und **Data_seg** Pragmas. In der Quellcode-Editors werden Doppelbyte-Zeichen in Kommentaren und Zeichenfolgenliterale in C-/C++-Sprachelemente (z. B. Variablennamen) jedoch nicht akzeptiert.  
  
##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> Unterstützung für den Eingabemethoden-Editor (IME)  
 Anwendungen für ostasiatische Märkte, die normalerweise MBCS (z. B. Japan) Verwenden des Windows-IME-Unterstützung für sowohl einzelne und Doppelbyte-Zeichen eingeben. Die Entwicklungsumgebung von Visual C++ enthält die vollständige Unterstützung für den IME. Weitere Informationen finden Sie unter [IME-Beispiel: veranschaulicht, wie Steuerelement IME-Modus und Implementieren von IME Level 3](http://msdn.microsoft.com/en-us/87ebdf65-cef0-451d-a6fc-d5fb64178b14).  
  
 Tastaturen japanische unterstützt Kanji-Zeichen nicht direkt. Der IME konvertiert eine phonetische Zeichenfolge, in seiner möglichen Kanji-Darstellung in einem der anderen japanische Alphabete (Romaji, Katakana oder Hiragana) eingegeben. Bei einer Mehrdeutigkeit, können Sie verschiedene Alternativen auswählen. Wenn Sie das beabsichtigte Kanji Zeichen ausgewählt haben, die IME übergibt zwei `WM_CHAR` Nachrichten an die Anwendung steuern.  
  
 Der IME aktiviert, indem Sie ALT +\` Tastenkombination, die als eine Reihe von Schaltflächen (einen Indikator) und eine Konvertierungsfenster angezeigt wird. Das Fenster an der Texteinfügemarke positioniert. Die Anwendung muss behandeln `WM_MOVE` und `WM_SIZE` Nachrichten durch Neupositionieren der Konvertierung Fenster entsprechen, die neue Position und Größe des Zielfensters.  
  
 Wenn Sie Benutzer der Anwendung, um die Fähigkeit haben, Kanji Zeichen eingeben möchten, muss die Anwendung Windows-IME-Nachrichten verarbeiten. Weitere Informationen zur IME-Programmierung finden Sie unter [Eingabemethoden-Editors](https://msdn.microsoft.com/en-us/library/ms776145.aspx).  
  
## <a name="visual-c-debugger"></a>Visual C++-Debugger  
 Visual C++-Debugger bietet die Möglichkeit zum Festlegen von Haltepunkten für IME-Nachrichten. Darüber hinaus kann das Fenster "Arbeitsspeicher" Double-Byte-Zeichen anzeigen.  
  
## <a name="command-line-tools"></a>Befehlszeilentools  
 Die Visual C++-Befehlszeilentools, einschließlich der Compiler, NMAKE und der Ressourcencompiler (RC. EXE-Datei), MBCS-aktiviert sind. Der Ressourcencompiler/c-Option können die Standardcodepage zu ändern, wenn die Ressourcen der Anwendung zu kompilieren.  
  
 Um das Standard-Gebietsschema beim Kompilieren des Quellcodes zu ändern, verwenden [#pragma Setlocale](../preprocessor/setlocale.md).  
  
## <a name="graphical-tools"></a>-Grafiktools  
 Die Visual C++-Windows-basierten Tools, z. B. Spy++ und die Ressource Bearbeitungstools, unterstützen vollständig IME-Zeichenfolgen.  
  
## <a name="see-also"></a>Siehe auch  
 [Unterstützung von Mehrbyte-Zeichensätzen (MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)   
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)
---
title: "MBCS-Unterst&#252;tzung in Visual C++"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Asiatische Sprachen [C++]"
  - "Zeichensätze [C++], Mehrbyte"
  - "Chinesische Zeichen [C++]"
  - "Code-Editor [C++], MBCS-Unterstützung"
  - "Debugger [C++], MBCS-Unterstützung"
  - "Doppelbyte-Zeichensätze [C++]"
  - "IME [C++]"
  - "IME [C++], MBCS"
  - "Eingabemethoden-Editor [C++]"
  - "Eingabemethoden-Editor [C++], MBCS"
  - "Japanische Zeichen [C++]"
  - "Kanji-Zeichenunterstützung [C++]"
  - "MBCS [C++], Aktivieren"
  - "Mehrbytezeichen [C++]"
  - "NMAKE (Programm), MBCS-Unterstützung"
  - "Ressourcen-Editoren [C++], MBCS-Unterstützung"
  - "Tools [C++], MBCS-Unterstützung"
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "ghogen"
manager: "ghogen"
---
# MBCS-Unterst&#252;tzung in Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei der Ausführung unter einer MBCS\-aktivierten Version des Betriebssystems Windows 2000 oder Windows XP ist das Visual C\+\+\-Entwicklungssystem MBCS\-aktiviert \(einschließlich des integrierten Quellcode\-Editors, Debuggers und der Befehlszeilentools\), aber mit Ausnahme des Speicherfensters.  
  
 Das Speicherfenster interpretiert Datenbytes nicht als MBCS\-Zeichen, kann diese jedoch als ANSI\- oder Unicode\-Zeichen interpretieren.  ANSI\-Zeichen belegen immer 1 Byte an Größe und Unicode\-Zeichen sind 2 Bytes an Größe.  Mit MBCS können Zeichen 1, oder 2 Bytes an Größe und ihre Interpretation hängt davon ab, welcher Codepage verwendet wird.  Daher ist es schwierig für das Speicherfenster, MBCS\-Zeichen zuverlässig anzuzeigen.  Das Speicherfenster kann nicht feststellen, welches Byte der Anfang eines Zeichens ist.  Der Entwickler kann die Bytewerte im Speicherfenster anzeigen und diese in Tabellen suchen, um die Zeichendarstellung zu ermitteln.  Dies ist möglich, da der Entwickler die Startadresse einer Zeichenfolge auf Grundlage des Quellcodes kennt.  
  
 Visual C\+\+ nimmt in allen geeigneten Fällen Doppelbytezeichen an.  Hierzu zählen Pfad\- und Dateinamen in Dialogfeldern sowie Texteinträge im Visual C\+\+Ressourcen\-Editor \(z. B. statischer Text im Dialog\-Editor und statische Texteinträge im Symbol\-Editor\).  Darüber hinaus erkennt der Präprozessor bestimmte Doppelbyte\-Direktiven, z. B. Dateinamen in `#include`\-Anweisungen und als Argumente von **code\_seg**\- und **data\_seg**\-Pragmas.  Im Quellcode\-Editor werden Doppelbytezeichen angenommen, in C\/C\+\+\-Sprachelementen \(z. B. Variablennamen\) jedoch nicht.  
  
##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> Unterstützung für den Eingabemethoden\-Editor  
 Anwendungen für fernöstliche Märkte \(z. B. Japan\), von denen MBCS verwendet wird, unterstützen in der Regel den Eingabemethoden\-Editor \(Input Method Editor, IME\) von Windows für die Eingabe von Einzel\- und Doppelbytezeichen.  Die Visual C\+\+\-Entwicklungsumgebung bietet vollständige Unterstützung für IME.  Weitere Informationen finden Sie unter [IME\-Beispiel: Demonstration der Steuerung des IME\-Modus und der Implementierung von IME Level 3](assetId:///87ebdf65-cef0-451d-a6fc-d5fb64178b14).  
  
 Japanische Tastaturen unterstützen Kanji\-Zeichen nicht direkt.  IME konvertiert eine phonetische Zeichenfolge eines anderen japanischen Alphabets \(Romaji, Katakana oder Hiragana\) in entsprechende Kanji\-Darstellungen.  Bei Mehrdeutigkeiten können Sie zwischen verschiedenen Vorschlägen wählen.  Wenn Sie das gewünschte Kanji\-Zeichen ausgewählt haben, übergibt IME zwei `WM_CHAR`\-Meldungen an die steuernde Anwendung.  
  
 IME wird mit der Tastenkombination ALT\+' aktiviert und dann in Form einer Schaltflächengruppe \(einem Indikator\) und einem Konvertierungsfenster angezeigt.  Das Fenster wird an der Texteinfügemarke positioniert.  Die Anwendung muss die `WM_MOVE`\-Meldung und die `WM_SIZE`\-Meldung durch Neupositionieren des Konvertierungsfensters so behandeln, dass es an die neue Position und Größe des Zielfensters angepasst wird.  
  
 Wenn Sie den Benutzern einer Anwendung die Möglichkeit zur Eingabe von Kanji\-Zeichen geben möchten, muss die Anwendung Windows IME\-Meldungen behandeln können.  Weitere Informationen zur IME\-Programmierung finden Sie unter [Eingabemethoden\-Editor](https://msdn.microsoft.com/en-us/library/ms776145.aspx).  
  
## Visual C\+\+ Debugger  
 Mit dem Visual C\+\+ Debugger können Sie Haltepunkte auf IME\-Meldungen setzen.  Darüber hinaus können im Fenster für die Speicherbelegung Doppelbytezeichen angezeigt werden.  
  
## Befehlszeilentools  
 Die Befehlszeilentools von Visual C\+\+, zu denen der Compiler, NMAKE sowie der Ressourcencompiler \(RC.EXE\) zählen, sind MBCS\-aktiviert.  Mit der Option \/c des Ressourcencompiler können Sie beim Kompilieren der Ressourcen einer Anwendung die Standard\-Codepage ändern.  
  
 Verwenden Sie [\#pragma setlocale](../preprocessor/setlocale.md), um das Standard\-Gebietsschema beim Kompilieren des Quellcodes zu ändern.  
  
## Grafische Tools  
 Die Windows\-basierten Visual C\+\+\-Tools, z. B. Spy\+\+ und die Tools zur Ressourcenbearbeitung, bieten vollständige Unterstützung von IME\-Zeichenfolgen.  
  
## Siehe auch  
 [Unterstützung von Mehrbyte\-Zeichensätzen \(MBCS\)](../text/support-for-multibyte-character-sets-mbcss.md)   
 [Tipps für die MBCS\-Programmierung](../text/mbcs-programming-tips.md)
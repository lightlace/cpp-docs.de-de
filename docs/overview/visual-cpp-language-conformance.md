---
title: 'Microsoft C++-Sprachkonformität: Tabelle'
ms.date: 05/19/2019
ms.technology: cpp-language
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
author: corob-msft
ms.author: corob
ms.openlocfilehash: c36256988e2698cb6f04e0ab71dbf6211b596033
ms.sourcegitcommit: 61121faf879cc581a4d39e4baccabf7cf1f673a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "65934172"
---
# <a name="microsoft-c-language-conformance-table"></a>Microsoft C++-Sprachkonformität: Tabelle

Dieses Thema enthält einen Überblick über die Konformität von Compiler- und Standardbibliotheksfeatures des Microsoft C++-Compilers in Visual Studio 2019 und früheren Versionen mit den Sprachstandards ISO C++03, C++11, C++14, C++17 und C++20. Jeder Name eines Features im Compiler und in der Standardbibliothek verweist auf das ISO C++-Standardvorschlagsdokument, in dem das Feature beschrieben ist, falls zum Zeitpunkt der Veröffentlichung ein solches Dokument verfügbar ist. Die Spalte „Supported“ (Unterstützt) listet die Visual Studio-Version auf, in der die Unterstützung für die Funktion zum ersten Mal aufgetreten ist.

Ausführliche Informationen zu Verbesserungen bei der Konformität und zu anderen Änderungen in Visual Studio 2017 oder Visual Studio 2019 erhalten Sie, indem Sie die Versionsauswahl oben links auf dieser Seite verwenden und dann [Verbesserungen der C++-Konformität in Visual Studio](cpp-conformance-improvements.md) und [Neuerungen bei Visual C++ in Visual Studio](what-s-new-for-visual-cpp-in-visual-studio.md) lesen. Kompatibilitätsänderungen in früheren Versionen finden Sie unter [Änderungsverlauf von Visual C++ von 2003 bis 2015](../porting/visual-cpp-change-history-2003-2015.md) und [Visual C++ What's New 2003 through 2015](../porting/visual-cpp-what-s-new-2003-through-2015.md) (Visual C++ – Neuerungen von 2003 bis 2015). Aktuelle Nachrichten vom C++-Team finden Sie im [C++-Teamblog](https://devblogs.microsoft.com/cppblog/).

> [!NOTE]
> Es gibt keine binären Änderungen zwischen Visual Studio 2015, Visual Studio 2017 und Visual Studio 2019.

## <a name="compiler-features"></a>Compilerfunktionen

|Bereich „Funktionen“| |
|----|---|
|__Funktionen der C++03/11-Kernsprache__|__Unterstützt__|
|&nbsp;&nbsp;Alles andere|VS 2015 <sup>[A](#note_A)</sup>|
|&nbsp;&nbsp;Zwei-Phasen Namenssuche|VS 2017 15.7 <sup>[B](#note_B)</sup>|
|&nbsp;&nbsp;[N2634 SFINAE für Ausdrücke](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|VS 2017 15.7|
|&nbsp;&nbsp;[N1653 C99-Präprozessor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|Teilweise <sup>[C](#note_C)</sup>|
|__Funktionen der C++14-Kernsprache__|__Unterstützt__|
|&nbsp;&nbsp;[N3323 Optimierte Formulierungen für kontextbezogene Konvertierungen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3323.pdf)|VS 2013|
|&nbsp;&nbsp;[N3472 Binäre Literale](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3472.pdf)|VS 2015|
|&nbsp;&nbsp;[N3638 Rückagebetypen „auto“ und „decltype(auto)“](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3638.html)|VS 2015|
|&nbsp;&nbsp;[N3648 init-captures](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3648.html)|VS 2015|
|&nbsp;&nbsp;[N3649 Generische Lambda-Ausdrücke](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3649.html)|VS 2015|
|&nbsp;&nbsp;[N3760: \[\[deprecated\]\]-Attribut](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3760.html)|VS 2015|
|&nbsp;&nbsp;[N3778 Zuordnungsaufhebung mit Größenangabe](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3781 Zahlentrennzeichen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3781.pdf)|VS 2015|
|&nbsp;&nbsp;[N3651 Variablenvorlagen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf)|VS 2015.2|
|&nbsp;&nbsp;[N3652 Erweiterte constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)|VS 2017 15.0|
|&nbsp;&nbsp;[N3653: Standardmemberinitialisierer für Aggregate](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3653.html)|VS 2017 15.0|
|__Funktionen der C++17-Kernsprache__|__Unterstützt__|
|&nbsp;&nbsp;[N4086 Entfernen von Trigraphen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)|VS 2010 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N3922 Neue Regeln für „auto“ mit „braced-init-lists“](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4051 „typename“ in Vorlagen-Vorlagenparametern](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4266 Attribute für Namespaces und Enumeratoren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4267 u8-Zeichenliterale](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4230 Geschachtelte Namespacedefinitionen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4230.html)|VS 2015.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N3928 Knappes static_assert](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)|VS 2017 15.0 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0184R0 Generalisierte bereichsbasierte for-Schleifen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)|VS 2017 15.0 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0188R1: \[\[fallthrough\]\]-Attribut](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r1.pdf)|VS 2017 15.0 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0001R1 Entfernen des register-Schlüsselworts](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0002R1 Entfernen von operator++ für bool](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0018R3 *dies nach Wert erfassen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0028R4 Verwenden des Attribut Namespaces ohne Wiederholung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0028r4.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0061R1: \_\_has_include](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0061r1.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0138R2 Direct-Liste-Init von festen Enumerationen von Ganzzahlen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0170R1 constexpr-Lambdas](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0170r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0189R1: \[\[nodiscard\]\]-Attribut](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0189r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0212R1: \[\[maybe_unused\]\]-Attribut](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0212r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0217R3 Strukturierte Bindungen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0217r3.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0292R2 constexpr if-Anweisung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0292r2.html)|VS 2017 15.3 <sup>[D](#note_D)</sup>|
|&nbsp;&nbsp;[P0305R1 Auswahlanweisungen mit Initialisierern](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0305r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0245R1 Hexfloat-Literale](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0245r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N4268 Mehr Nicht-Typen-Vorlagenargumente erlauben](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4268.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N4295 Fold-Ausdrücke](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4295.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0003R5 Entfernen von dynamischen Ausnahmespezifikationen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0012R1 noexcept zum Typsystem hinzufügen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0012r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0035R4 Über-ausgerichtete dynamische Speicherbelegung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0035r4.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0386R2 Inline-Variablen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0386r2.pdf)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0522R0 Übereinstimmender template-Vorlagenparameter zu kompatiblen Argumenten](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0522r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0036R0 Entfernen einiger leerer unärer Folds](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0036r0.pdf)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N4261 Qualifikationskonvertierungen beheben](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4261.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0017R1 Erweiterte ungültige Aggregatinitialisierung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0091R3 Vorlagenargumentableitung für Klassenvorlagen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)<br/>&nbsp;&nbsp;[P0512R0 Probleme mit der Argumentableitung für Klassenvorlagen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0512r0.pdf)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0127R2 Deklarieren von Nichttyp-Vorlagenparameter mit auto](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0135R1 Garantierte copy elision](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0135r1.html)|VS 2017 15.6|
|&nbsp;&nbsp;[P0136R1 Umformulierung der Konstruktorvererbung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0137R1 std::launder](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0137r1.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0145R3 Reihenfolge der Ausdrucksauswertung optimieren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0145r3.pdf)<br/>&nbsp;&nbsp;[P0400R0 Auswertungsreihenfolge von Funktionsargumenten](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0400r0.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0195R2 Pack-Erweiterungen in der using-Deklarationen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0195r2.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0283R2 Ignoriert nicht erkannte Attribute](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0283r2.html)|VS 2015 <sup>[14](#note_14)</sup>|


|Bereich „Funktionen“| |
|----|---|
|__Hauptfeatures von C++ 17 (Fehlerberichte)__|__Unterstützt__|
|&nbsp;&nbsp;[P0702R1 Beheben von Problemen mit der Argumentableitung für Klassenvorlagen für „initializer-list ctors“](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0702r1.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0588R1: Vereinfachen der Erfassung impliziter Lambdas](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0588r1.html)|Nein|
|&nbsp;&nbsp;[P0961R1: Lockern der Regeln für das Suchen von Anpassungspunkten von strukturierten Bindungen](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0961r1.html)|VS 2019 16.0 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0962R2: Lockern der Regeln für das Suchen von Anpassungspunkten von range-for-Schleifen](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0962r1.html)|Nein|
|&nbsp;&nbsp;[P0969R0: Zulassen strukturierter Bindungen an zugängliche Members](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0969r0.pdf)|VS 2019 16.0 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0859R0 CWG 1581: Wann werden constexpr-Memberfunktionen definiert?](https://wg21.link/P0859R0)|Nein|
|&nbsp;&nbsp;[P0929R2: Überprüfen auf abstrakte Klassentypen](https://wg21.link/P0929R2)|Nein|
|&nbsp;&nbsp;[P1009R2: Arraygrößenableitung in neuen Ausdrücken](https://wg21.link/P1009R2)|Nein|
|&nbsp;&nbsp;[P1286R2: Contra CWG DR1778](https://wg21.link/P1286R2)|Nein|

|Bereich „Funktionen“| |
|----|---|
|__C++20-Kernsprachfunktionen__|__Unterstützt__|
|&nbsp;&nbsp;[P0704R1 Beheben von „const lvalue ref“-qualifizierten Zeigern auf Member](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0704r1.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0972R0: noexcept for \<chrono> zero(), min(), max()](https://wg21.link/P0972R0)|VS 2017 15.7 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P1330R0: Ändern des aktiven Members einer Union in constexpr](https://wg21.link/P1330R0)|VS 2017 15.0 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0329R4 Designierte Initialisierung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0409R2: Zulassen von „lambda-capture \[=, this\]“](http://open-std.org/JTC1/SC22/WG21/docs/papers/2017/p0409r2.html)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0515R3: Drei-Wege-Vergleichsoperator (Spaceship) <=>](https://wg21.link/P0515R3) und [P0905R1: Symmetrie für Spaceship](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0905r1.html)|VS 2019 16.0 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0941R2: Makros für Featuretest](https://wg21.link/P0941R2)|VS 2019 16.0 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P1008R1: Unterbindung von Aggregaten mit benutzerdeklarierten Konstruktoren](https://wg21.link/P1008R1)|VS 2019 16.0 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0846R0: ADL und Funktionsvorlagen, die nicht sichtbar sind](https://wg21.link/P0846R0)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0641R2: const-Konflikt mit Standardkopierkonstruktor](https://wg21.link/P0641R2)|Partial|
|&nbsp;&nbsp;[P0306R4: Hinzufügen von \_\_VA_OPT\_\_ für das Auslassen und Löschen von Kommas](https://wg21.link/P0306R4) und [P1042R1: \_\_VA_OPT\_\_-Wortlautklärungen](https://wg21.link/P1042R1)|Nein|
|&nbsp;&nbsp;[P0315R4: Zulassen von Lambdas in nicht ausgewerteten Kontexten](https://wg21.link/P0315R4)|Nein|
|&nbsp;&nbsp;[P0409R2: Zulassen von „lambda-capture \[=, this\]“](https://wg21.link/P0409R2)|Nein|
|&nbsp;&nbsp;[P0428R2 Bekannte Vorlagensyntax für generische Lambdas](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0428r2.pdf)|Nein|
|&nbsp;&nbsp;[P0479R5: \[\[likely\]\]- und \[\[unlikely\]\]-Attribut](https://wg21.link/P0479R5)|Nein|
|&nbsp;&nbsp;[P0542R5: Verträge](https://wg21.link/P0542R5)|Nein|
|&nbsp;&nbsp;[P0614R1: Bereichsbasierte for-Schleifen mit Initialisierern](https://wg21.link/P0614R1)|Nein|
|&nbsp;&nbsp;[P0624R2: Konstruierbare und zuweisbare zustandslose Standard-Lambdas](https://wg21.link/P0624R2)|Nein|
|&nbsp;&nbsp;[P0634R3: Gegen Typnamen!](https://wg21.link/P0634R3)|Nein|
|&nbsp;&nbsp;[P0683R1 Standardmemberinitialisierer für „bit-fields“](https://wg21.link/P0683R1)|Nein|
|&nbsp;&nbsp;[P0692R1: Lockern der Zugriffsprüfung für Spezialisierungen](https://wg21.link/P0692R1)|Nein|
|&nbsp;&nbsp;[P0722R3: Löschen mit effizienter Größe für Klassen mit variabler Größe](https://wg21.link/P0722R3)|Nein|
|&nbsp;&nbsp;[P0732R2: Klassentypen in Vorlagenparametern ohne Typ](https://wg21.link/P0732R2)|Nein|
|&nbsp;&nbsp;[P0734R0 Konzepte](https://wg21.link/P0734R0)|Nein|
|&nbsp;&nbsp;[P0780R2: Zulassen der Paketerweiterung in Lambda „init-capture“](https://wg21.link/P0780R2)|Nein|
|&nbsp;&nbsp;[P0806R2: Kennzeichnen der impliziten Erfassung als veraltet per \[=\]](https://wg21.link/P0806R2)|Nein|
|&nbsp;&nbsp;[P0840R2: \[\[no_unique_address\]\]-Attribut](https://wg21.link/P0840R2)|Nein|
|&nbsp;&nbsp;[P0857R0: Beheben von Funktionalitätslücken in Einschränkungen](https://wg21.link/P0857R0)|Nein|
|&nbsp;&nbsp;[P0892R2: Bedingt explizit](https://wg21.link/P0892R2)|Nein|
|&nbsp;&nbsp;[P0912R5: Coroutinen](https://wg21.link/P0912R5)|Nein|
|&nbsp;&nbsp;[P0960R3: Zulassen der Initialisierung von Aggregaten über eine in Klammern gesetzte Liste mit Werten](https://wg21.link/P0960R3)|Nein|
|&nbsp;&nbsp;[P1002R1: try-catch-Blöcke in constexpr-Funktionen](https://wg21.link/P1002R1)|Nein|
|&nbsp;&nbsp;[P1041R4: Konvertieren von char16_t/char32_t-Zeichenfolgenliteralen in UTF-16/32](https://wg21.link/P1041R4)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P1064R0: Zulassen von virtuellen Funktionsaufrufen in konstanten Ausdrücken](https://wg21.link/P1064R0)|Nein|
|&nbsp;&nbsp;[P1073R3: Direkte Funktionen](https://wg21.link/P1073R3)|Nein|
|&nbsp;&nbsp;[P1084R2: Derzeitige Rückgabetypanforderungen sind unzureichend](https://wg21.link/P1084R2)|Nein|
|&nbsp;&nbsp;[P1091R3: Erweitern von strukturierten Bindungen zur Annäherung an Variablendeklarationen](https://wg21.link/P1091R3)|Nein|
|&nbsp;&nbsp;[P1094R2: Geschachtelte Inlinenamespaces](https://wg21.link/P1094R2)|Nein|
|&nbsp;&nbsp;[P1103R3: Module](https://wg21.link/P1103R3)|Nein|
|&nbsp;&nbsp;[P1120R0: Konsistenzverbesserungen für <=> und andere Vergleichsoperatoren](https://wg21.link/P1120R0)|Nein|
|&nbsp;&nbsp;[P1139R2: Beheben von Wortlautproblemen in Bezug auf ISO 10646](https://wg21.link/P1139R2)|Nein|
|&nbsp;&nbsp;[P1141R2: Ein weiterer Ansatz für eingeschränkte Deklarationen](https://wg21.link/P1141R2)|Nein|
|&nbsp;&nbsp;[P1185R2: \<=\> != ==](https://wg21.link/P1185R2)|Nein|
|&nbsp;&nbsp;[P1236R1: Ganze Zahlen mit Vorzeichen sind Zweierkomplement](https://wg21.link/P1236R1)|Nein|
|&nbsp;&nbsp;[P1289R1: Zugriffssteuerung in Vertragsbedingungen](https://wg21.link/P1289R1)|Nein|
|&nbsp;&nbsp;[P1323R2: Vertragsnachbedingungen und Rückgabetypableitung](https://wg21.link/P1323R2)|Nein|
|&nbsp;&nbsp;[P1327R1: Zulassen von polymorpher dynamic_cast typeid in konstanten Ausdrücken](https://wg21.link/P1327R1)|Nein|
|&nbsp;&nbsp;[P1353R0: Fehlende Makros für Featuretest](https://wg21.link/P1353R0)|Nein|
|&nbsp;&nbsp;[P1381R1: Verweiserfassung von strukturierten Bindungen](https://wg21.link/P1381R1)|Nein|

## <a name="standard-library-features"></a>Standardbibliotheksfeatures

|Bereich „Funktionen“| |
|---|---|
|__C++20-Standardbibliotheksfunktionen__|__Unterstützt__|
|&nbsp;&nbsp;[P0019R8: atomic_ref](https://wg21.link/P0019R8)|Nein|
|&nbsp;&nbsp;[P0020R6: atomic\<float>, atomic\<double>, atomic\<long double>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0020r6.html)|Nein|
|&nbsp;&nbsp;[P0053R7: \<syncstream>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0053r7.pdf)<br/>&nbsp;&nbsp;[P0753R2: osyncstream-Manipulatoren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0753r2.pdf)|Nein|
|&nbsp;&nbsp;[P0122R7: \<span>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0122r7.pdf)|Nein|
|&nbsp;&nbsp;[P0202R3: constexpr für \<algorithm> und exchange()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0202r3.html)|Nein|
|&nbsp;&nbsp;[P0318R1: unwrap_reference, unwrap_ref_decay](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0318r1.pdf)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0339R6: polymorphic_allocator<>](https://wg21.link/P0339R6)|Nein|
|&nbsp;&nbsp;[P0340R3: SFINAE-freundliches underlying_type-Element](https://wg21.link/P0340R3)|Nein|
|&nbsp;&nbsp;[P0355R7: \<chrono> Kalender und Zeitzonen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0355r7.html)|Nein|
|&nbsp;&nbsp;[P0356R5: bind_front()](https://wg21.link/P0356R5)|Nein|
|&nbsp;&nbsp;[P0357R3: Unterstützung von unvollständigen Typen in reference_wrapper](https://wg21.link/P0357R3)|Nein|
|&nbsp;&nbsp;[P0415R1: constexpr für \<complex> (noch einmal)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0415r1.html)|Nein|
|&nbsp;&nbsp;[P0439R0: memory_order für Enumerationsklasse](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0439r0.html)|Nein|
|&nbsp;&nbsp;[P0457R2: starts_with()/ends_with() für basic_string/basic_string_view](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0457r2.html)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0458R2 contains() für sortierte und unsortierte assoziative Container](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0458r2.html)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0463R1 Endian](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0463r1.html)|Nein|
|&nbsp;&nbsp;[P0475R1: Garantierte Auslassung von „copy“ für stückweise Konstruktion](https://wg21.link/P0475R1)|Nein|
|&nbsp;&nbsp;[P0476R2: <bit> bit_cast](https://wg21.link/P0476R2)|Nein|
|&nbsp;&nbsp;[P0482R6 char8_t: Ein Typ für UTF-8-Zeichen und -Zeichenfolgen](https://wg21.link/P0482R6)|Nein|
|&nbsp;&nbsp;[P0487R1: Behebung von operator>>(basic_istream&, CharT*)](https://wg21.link/P0487R1)|Nein|
|&nbsp;&nbsp;[P0528R3: Atomisches Vergleichen und Austauschen mit Auffüll-Bits](https://wg21.link/P0528R3)|Nein|
|&nbsp;&nbsp;[P0550R2: remove_cvref](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf)|VS 2019 16.0 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0556R3: <bit> ispow2(), ceil2(), floor2(), log2p1()](https://wg21.link/P0556R3)|Nein|
|&nbsp;&nbsp;[P0591R4: Hilfsfunktionen für Uses-Allocator-Konstruktion](https://wg21.link/P0591R4)|Nein|
|&nbsp;&nbsp;[P0600R1: \[\[nodiscard\]\] Für STL, Teil 1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0600r1.pdf)|Nein|
|&nbsp;&nbsp;[P0608R3: Verbessern des Konvertierungskonstruktors/der Zuweisung der Variante](https://wg21.link/P0608R3)|Nein|
|&nbsp;&nbsp;[P0616R0: Verwenden von move() in \<numeric>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0616r0.pdf)|Nein|
|&nbsp;&nbsp;[P0619R4: Entfernen von veralteten C++17-Features in C++20](https://wg21.link/P0619R4)|Nein|
|&nbsp;&nbsp;[P0646R1: list/forward_list remove()/remove_if()/unique() Return size_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0646r1.pdf)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0653R2: to_address()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0653r2.html)|Nein|
|&nbsp;&nbsp;[P0655R1: visit<R>()](https://wg21.link/P0655R1)|Nein|
|&nbsp;&nbsp;[P0674R1 „make_shared()“ für Arrays](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0674r1.html)|Nein|
|&nbsp;&nbsp;[P0718R2: atomic\<shared_ptr\<T>>, atomic\<weak_ptr\<T>>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0718r2.html)|Nein|
|&nbsp;&nbsp;[P0738R2: istream_iterator-Bereinigung](https://wg21.link/P0738R2)|Nein|
|&nbsp;&nbsp;[P0754R2: \<version>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0754r2.pdf)|Nein|
|&nbsp;&nbsp;[P0758R1: is_nothrow_convertible](https://wg21.link/P0758R1)|Nein|
|&nbsp;&nbsp;[P0767R1: Unterstützung für is_pod wird eingestellt](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0767r1.html)|Nein|
|&nbsp;&nbsp;[P0768R1: Bibliotheksunterstützung für den Spaceship-Vergleichsoperator \<=>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0768r1.pdf)|Nein|
|&nbsp;&nbsp;[P0769R2: shift_left(), shift_right()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0769r2.pdf)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0771R1: noexcept für Bewegungskonstruktor von std::function](https://wg21.link/P0771R1)|Nein|
|&nbsp;&nbsp;[P0777R1: Vermeiden unnötigen Verfalls](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf)|VS 2017 15.7 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0809R0: Vergleichen unsortierter Container](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0809r0.pdf)| VS 2010 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0811R3: midpoint(), lerp()](https://wg21.link/P0811R3)|Nein|
|&nbsp;&nbsp;[P0858R0: Anforderungen des Constexpr-Iterators](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0858r0.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0879R0: constexpr für Austauschfunktionen](https://wg21.link/P0879R0)|Nein|
|&nbsp;&nbsp;[P0887R1: type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0896R4: \<ranges\>](https://wg21.link/P0896R4)|Nein|
|&nbsp;&nbsp;[P0898R3: Standardbibliothekskonzepte](https://wg21.link/P0898R3)|Nein|
|&nbsp;&nbsp;[P0912R5: Bibliotheksunterstützung für Coroutinen](https://wg21.link/P0912R5)|Nein|
|&nbsp;&nbsp;[P0919R3: Heterogenes Nachschlagen für unsortierte Container](https://wg21.link/P0919R3)|Nein|
|&nbsp;&nbsp;[P0920R2: Nachschlagen mit vorausberechnetem Hashwert](https://wg21.link/P0920R2)|Nein|
|&nbsp;&nbsp;[P0935R0: Beseitigen von unnötig expliziten Standardkonstruktoren](https://wg21.link/P0935R0)|Nein|
|&nbsp;&nbsp;[P0966R1: string::reserve() sollte sich nicht verkleinern](https://wg21.link/P0966R1)|Nein|
|&nbsp;&nbsp;[P1001R2: execution::unseq](https://wg21.link/P1001R2)|Nein|
|&nbsp;&nbsp;[P1006R1: constexpr für pointer_traits<T*>::pointer_to()](https://wg21.link/P1006R1)|Nein|
|&nbsp;&nbsp;[P1007R3: assume_aligned()](https://wg21.link/P1007R3)|Nein|
|&nbsp;&nbsp;[P1020R1: Erstellung eines intelligenten Zeigers mit Standardinitialisierung](https://wg21.link/P1020R1)|Nein|
|&nbsp;&nbsp;[P1023R0: constexpr für std::array-Vergleiche](https://wg21.link/P1023R0)|Nein|
|&nbsp;&nbsp;[P1032R1: constexpr – Verschiedenes](https://wg21.link/P1032R1)|Nein|
|&nbsp;&nbsp;[P1164R1: Erhöhen der Intuitivität für create_directory() (Fehlerbericht)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1164r1.pdf)|VS 2019 16.0 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P1165R1: Einheitliches Weitergeben von zustandsbehafteten Zuweisungen in operator+() von basic_string](https://wg21.link/P1165R1)|Nein|
|&nbsp;&nbsp;[P1209R0: erase_if(), erase()](https://wg21.link/P1209R0)|Nein|
|&nbsp;&nbsp;[P1227R2: std::ssize() mit Vorzeichen, span::size() ohne Vorzeichen](https://wg21.link/P1227R2)|Nein|
|&nbsp;&nbsp;[P1285R0: Verbessern der Vollständigkeitsanforderungen für Typmerkmale](https://wg21.link/P1285R0)|Nein|
|&nbsp;&nbsp;[P1357R1: is_bounded_array, is_unbounded_array](https://wg21.link/P1357R1)|Nein|
|__C++17 Standardbibliotheksfunktionen__|__Unterstützt__|
|&nbsp;&nbsp;[LWG 2221: Formatierter Ausgabeoperator für nullptr](https://cplusplus.github.io/LWG/issue2221)|VS 2019 16.1|
|&nbsp;&nbsp;[N3911 void_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3911.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4089 Sichere Konvertierungen in unique_ptr\<T[]>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4089.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4169 invoke()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4169.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4190 Entfernen von auto_ptr, random_shuffle(), und altem \<functional> Stuff](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4190.htm)|VS 2015 <sup>[rem](#note_rem)</sup>|
|&nbsp;&nbsp;[N4258 noexcept-Bereinigungen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4258.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4259 uncaught_exceptions()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4259.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4277 Einfach kopierbare reference_wrapper](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4277.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4279 insert_or_assign()/try_emplace() für map/unordered_map](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4279.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4280 size(), empty(), data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4280.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4366 Exakt eingeschränkte unique_ptr-Zuweisungen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4366.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4387 Verbessern von pair und tuple](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4387.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4389 bool_constant](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4389.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4508 shared_mutex (nicht zeitgesteuert)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4508.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4510 Unterstützung von unvollständigen Typen in vector/list/forward_list](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4510.html)|VS 2013 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4562 Bibliotheksgrundlagen: \<algorithm> sample()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#alg.random.sample)|VS 2017 15.0|
|&nbsp;&nbsp;[N4562 Bibliotheksgrundlagen: \<any>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#any)|VS 2017 15.0|
|&nbsp;&nbsp;[N4562 Bibliotheksgrundlagen: \<memory_resource >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#memory.resource.synop)<br/>&nbsp;&nbsp;[P0337R0 Löschen der polymorphic_allocator-Zuweisung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0337r0.html)|VS 2017 15.6|
|&nbsp;&nbsp;[N4562 Bibliotheksgrundlagen: \<optional>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#optional)|VS 2017 15.0|
|&nbsp;&nbsp;[N4562 Bibliotheksgrundlagen: \<string_view>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#string.view)|VS 2017 15.0|
|&nbsp;&nbsp;[N4562 Bibliotheksgrundlagen: \<tuple> apply()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#tuple)|VS 2017 15.0|
|&nbsp;&nbsp;[N4562 Bibliotheksgrundlagen: Boyer-Moore search()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 Beheben der Suchprogramm-Rückgabetypen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0253r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0003R5 Entfernen von dynamischen Ausnahmespezifikationen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0004R1 Veraltete Iostreams-Aliase entfernen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0004r1.html)|VS 2015.2 <sup>[rem](#note_rem)</sup>|
|&nbsp;&nbsp;[P0005R4 not_fn()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html)<br/>&nbsp;&nbsp;[P0358R1 Korrekturen für not_fn()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0006R0 Variable Vorlagen für Typmerkmale (is_same_v, usw.).](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0006r0.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0007R1 as_const()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0007r1.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0013R1 Typmerkmale von logischen Operatoren (conjunction, usw.).](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0013r1.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0024R2 Parallele Algorithmen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html)<br/>&nbsp;&nbsp;[P0336R1 Umbenennen der Richtlinien für parallele Ausführung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0336r1.pdf)<br/>&nbsp;&nbsp;[P0394R4 Parallele Algorithmen müssen bei Ausnahmefehlern „terminate()“ aufrufen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0394r4.html)<br/>&nbsp;&nbsp;[P0452R1 Vereinheitlichen von parallelen \<numeric>-Algorithmen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0452r1.html)|VS 2017 15.7|
|&nbsp;&nbsp;[P0025R1 clamp()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0025r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0030R1 hypot(x, y, z)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf)|VS 2017 15.7|
|&nbsp;&nbsp;[P0031R0 constexpr für \<array> (erneut) und \<iterator>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0031r0.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0032R3 Homogene Schnittstelle für variant/any/optional](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0032r3.pdf)|VS 2017 15.0|
|&nbsp;&nbsp;[P0033R1 enable_shared_from_this umformulieren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html)|VS 2017 15.5 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0040R3 Erweitern von Speicher-Verwaltungstools](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0040r3.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0063R3 C11-Standardbibliothek](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0063r3.html)|VS 2015 <sup>[C11](#note_C11), [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0067R5 Elementare Zeichenfolgenkonvertierungen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html)|VS 2017 15.7 <sup>[charconv](#note_charconv)</sup>|
|&nbsp;&nbsp;[P0074R0 owner_less\<>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0074r0.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0077R2 is_callable, is_nothrow_callable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0077r2.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0083R3 Zusammenführen von Zuordnungen und Festlegungen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)<br/>&nbsp;&nbsp;[P0508R0 insert_return_type klarstellen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0084R2 Emplace-Rückgabetyp](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0084r2.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0088R3 \<variant>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0088r3.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0092R1 \<chrono> floor(), ceil(), round(), abs()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0092r1.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0152R1 atomic::is_always_lock_free](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0152r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size, usw.](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0154r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0156R0 Variadic lock_guard](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r0.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0156R2 Umbenennen von „Variadic lock\_guard“ in „scoped\_lock“](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0156r2.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0163R0 shared_ptr::weak_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0163r0.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0174R2 Veraltete rudimentäre Bibliotheksteile](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0185R1 is_swappable, is_nothrow_swappable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0185r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0209R2 make_from_tuple()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0209r2.pdf)|VS 2017 15.0|
|&nbsp;&nbsp;[P0218R1 \<filesystem>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html)<br/>&nbsp;&nbsp;[P0219R1 Relative Pfade für Dateisystem](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0219r1.html)<br/>&nbsp;&nbsp;[P0317R1 Zwischenspeichern von Verzeichniseinträgen für Dateisystem](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0317r1.html)<br/>&nbsp;&nbsp;[P0392R0 Unterstützung von string_view in Dateisystempfaden](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0392r0.pdf)<br/>&nbsp;&nbsp;[P0430R2 Unterstützung von Nicht-POSIX-Dateisystemen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0430r2.pdf)<br/>&nbsp;&nbsp;[P0492R2 Auflösen von NB-Kommentaren für Dateisystem](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0492r2.html)|VS 2017 15.7 <sup>[E](#note_E)</sup>|
|&nbsp;&nbsp;[P0220R1 Bibliotheksgrundlagen V1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html)|VS 2017 15.6 <sup>[F](#note_F)</sup>|
|&nbsp;&nbsp;[P0226R1 Mathematische spezielle Funktionen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0226r1.pdf)|VS 2017 15.7|
|&nbsp;&nbsp;[P0254R2 string_view und std::string integrieren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0254r2.pdf)|VS 2017 15.0|
|&nbsp;&nbsp;[P0258R2 has_unique_object_representations](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0258r2.html)|VS 2017 15.3 <sup>[G](#note_G)</sup>|
|&nbsp;&nbsp;[P0272R1 Non-const basic_string::data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0272r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0295R0 gcd(), lcm()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0295r0.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0298R3 std::byte](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0298r3.pdf)|VS 2017 15.3 <sup>[17](#note_17),&nbsp;[byte](#note_byte)</sup>|
|&nbsp;&nbsp;[P0302R1 Entfernen der Unterstützung für Zuweisung in std::function](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0307R2 Optional wieder größer gleich machen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0307r2.pdf)|VS 2017 15.0|
|&nbsp;&nbsp;[P0393R3 Variant größer gleich machen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0393r3.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0403R1 UDLs für \<string_view> ("meow"sv, usw.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0403r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0414R2 shared_ptr\<T[]>, shared_ptr\<T[N]>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html)<br/>&nbsp;&nbsp;[P0497R0 Beheben von shared_ptr für Arrays](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html)|VS 2017 15.5 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0418R2 atomic compare_exchange memory_order-Anforderungen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0418r2.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0426R1 constexpr für char_traits](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html)|VS 2017 15.7|
|&nbsp;&nbsp;[P0433R2 Integrieren der Vorlagenableitung für Klassenvorlagen in die Standardbibliothek](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html)<br/>&nbsp;&nbsp;[P0739R0 Verbessern der Integration der Argumentableitung für Klassenvorlagen in die Standardbibliothek](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html)|VS 2017 15.7|
|&nbsp;&nbsp;[P0435R1 common_type überholen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0435r1.pdf)<br/>&nbsp;&nbsp;[P0548R1 Anpassung von „common\_type“ und „duration“](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0548r1.pdf)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0504R0 Erneute Betrachtung von in_place_t/in_place_type_t\<T>/in_place_index_t\<I>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0504r0.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0505R0 constexpr für \<chrono> (erneut)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0505r0.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0510R0 Ablehnen von Varianten von Nothing, Arrays, Verweisen und unvollständigen Typen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0510r0.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0513R0 Hashwerte verfälschen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0513r0.pdf)<br/>&nbsp;&nbsp;[P0599R1 noexcept-Hash](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0599r1.pdf)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0516R0 Kopieren von shared_future als noexcept markieren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0516r0.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0517R0 future_error aus future_errc erstellen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0517r0.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0521R0 Veraltete shared_ptr::unique()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0521r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0558R1: Auflösen von Inkonsistenzen in benannten atomic\<T>-Basisklassen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0558r1.pdf)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0595R2: std::is_constant_evaluated()](https://wg21.link/P0595R2)|Nein|
|&nbsp;&nbsp;[P0602R4: Weitergeben von Copy/Move-Trivialität in variant/optional](https://wg21.link/P0602R4)|VS 2017 15.3<sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0604R0 Ändern von „is\_callable/result\_of“ in „invoke\_result“, „is\_invocable“, „is\_nothrow\_invocable“](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0604r0.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0607R0 Inlinevariablen für die Standardbibliothek](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0618R0 Kennzeichnen von „\<codecvt>“ als veraltet](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0618r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0682R1: Reparieren von elementaren Zeichenfolgenkonvertierungen](https://wg21.link/P0682R1)|VS 2015 15.7 <sup>[17](#note_17)</sup>|
|__C++14 Standardbibliotheksfunktionen__|__Unterstützt__|
|&nbsp;&nbsp;[N3462 SFINAE-freundliche result_of](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3462.html)|VS 2015.2|
|&nbsp;&nbsp;[N3302 constexpr für \<complex>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3302.html)|VS 2015|
|&nbsp;&nbsp;[N3469 constexpr für \<chrono>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3469.html)|VS 2015|
|&nbsp;&nbsp;[N3470 constexpr für \<array>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3470.html)|VS 2015|
|&nbsp;&nbsp;[N3471 constexpr für \<initializer_list>, \<tuple>, \<utility>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3471.html)|VS 2015|
|&nbsp;&nbsp;[N3545 integral_constant::operator()()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3545.pdf)|VS 2015|
|&nbsp;&nbsp;[N3642 UDLs für \<chrono>, \<string> (1729ms, „meow“s, usw.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3642.pdf)|VS 2015|
|&nbsp;&nbsp;[N3644 NULL-Forward-Iteratoren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3644.pdf)|VS 2015|
|&nbsp;&nbsp;[N3654 quoted()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3654.html)|VS 2015|
|&nbsp;&nbsp;[N3657 Heterogenes assoziatives Nachschlagen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3657.htm)|VS 2015|
|&nbsp;&nbsp;[N3658 integer_sequence](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3658.html)|VS 2015|
|&nbsp;&nbsp;[N3659 shared_mutex (zeitgesteuert)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3659.html)|VS 2015|
|&nbsp;&nbsp;[N3668 exchange()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3668.html)|VS 2015|
|&nbsp;&nbsp;[N3669 constexpr-Memberfunktionen ohne const beheben](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3669.pdf)|VS 2015|
|&nbsp;&nbsp;[N3670 get\<T>()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3670.html)|VS 2015|
|&nbsp;&nbsp;[N3671 Zweibereich equal(), is_permutation(), mismatch()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3671.html)|VS 2015|
|&nbsp;&nbsp;[N3778 Zuordnungsaufhebung mit Größenangabe](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3779 UDLs für \<complex> (3.14i, usw.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3779.pdf)|VS 2015|
|&nbsp;&nbsp;[N3789 constexpr für \<functional>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3789.htm)|VS 2015|
|&nbsp;&nbsp;[N3887 tuple_element_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3887.pdf)|VS 2015|
|&nbsp;&nbsp;[N3891 Umbenennen von shared_mutex (zeitgesteuert) in shared_timed_mutex](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3891.htm)|VS 2015|
|&nbsp;&nbsp;[N3346 Minimale Containerelement-Anforderungen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3346.pdf)|VS 2013|
|&nbsp;&nbsp;[N3421 Transparente Operatorfunktionselemente (less\<>, usw.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3421.htm)|VS 2013|
|&nbsp;&nbsp;[N3655 Alias-Vorlagen für \<type_traits> (decay_t, usw.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3655.pdf)|VS 2013|
|&nbsp;&nbsp;[N3656 make_unique()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3656.htm)|VS 2013|

Eine Gruppe von Dokumenten in einer Liste gibt an, dass eine Funktion in den Standard gewählt wurde, und anschließend wurden auch ein oder mehrere Dokumente zum Verbessern oder Erweitern dieser Funktion gewählt. Diese Funktionen werden zusammen implementiert.

### <a name="supported-values"></a>Unterstützte Werte

__Nein__bedeutet noch nicht implementiert.<br/>
__Partiell__ bedeutet, dass die Implementierung unvollständig ist. Weitere Informationen finden Sie im Abschnitt „Hinweise“<br/>
__VS 2010__ gibt Funktionen an, die in Visual Studio 2010 unterstützt werden.<br/>
__VS 2013__ gibt Funktionen an, die in Visual Studio 2013 unterstützt werden.<br/>
__VS 2015__ gibt Funktionen an, die in Visual Studio 2015 RTW unterstützt werden.<br/>
__VS 2015.2__ und __VS 2015.3__ geben Funktionen an, die in Visual Studio 2015 Update 2 und Visual Studio 2015 Update 3 unterstützt werden.<br/>
__VS 2017 15.0__ gibt Features an, die in Visual Studio 2017 Version 15.0 (RTW) unterstützt werden.<br/>
__VS 2017 15.3__ gibt Features an, die in Visual Studio 2017 15.3 unterstützt werden.<br/>
__VS 2017 15.5__ gibt Features an, die in Visual Studio 2017 Version 15.5 unterstützt werden.<br/>
__VS 2017 15.7__ gibt Features an, die in Visual Studio 2017 Version 15.7 unterstützt werden.<br/>
__VS 2019 16.0__ gibt Features an, die in Visual Studio 2019 Version 16.0 (RTW) unterstützt werden.<br/>
__VS 2019 16.1__ gibt Features an, die in Visual Studio 2019 Version 16.1 unterstützt werden.<br/>

### <a name="notes"></a>Hinweise

<a name="note_A"></a>__A__ Im Modus [/std:c++14](../build/reference/std-specify-language-standard-version.md) werden dynamische Ausnahmespezifikationen nicht implementiert, und `throw()` wird weiterhin als Synonym von `__declspec(nothrow)` behandelt. In C++17 wurden dynamische Ausnahmespezifikationen hauptsächlich durch P0003R5 entfernt. Nur `throw()` wurde noch nicht entfernt, weshalb es nun als veraltet markiert wird und als Synonym von `noexcept` behandelt werden muss. Im Modus [/std:c++17](../build/reference/std-specify-language-standard-version.md) entspricht MSVC nun dem Standard, da `throw()` das gleiche Verhalten wie `noexcept` aufweist (also Erzwingung durch Beenden).

Die Compileroption [/Zc:noexceptTypes](../build/reference/zc-noexcepttypes.md) fordert das alte Verhalten von `__declspec(nothrow)` an. Wahrscheinlich wird `throw()` in C++20 entfernt. Es wurden neue Compilerwarnungen für Probleme mit Ausnahmespezifikationen unter [/std:c++17](../build/reference/std-specify-language-standard-version.md) und [/permissive-](../build/reference/permissive-standards-conformance.md) hinzugefügt, um die Codemigration aufgrund dieser Änderungen im Standard und unserer Implementierung zu erleichtern.

<a name="note_B"></a>__B__ Wird im Modus [/permissive-](../build/reference/permissive-standards-conformance.md) in Visual Studio 2017 Version 15.7 unterstützt. Weitere Informationen finden Sie im Blogbeitrag [Two-phase name lookup support comes to MSVC](https://blogs.msdn.microsoft.com/vcblog/2017/09/11/two-phase-name-lookup-support-comes-to-msvc/) (Unterstützung der Namenssuche in zwei Phasen in MSVC).

<a name="note_C"></a>__C__ Der Support des Compilers für die C99-Präprozessorregeln ist in Visual Studio 2017 unvollständig. Variadic-Makros werden unterstützt, aber es treten viele Fehler im Verhalten des Präprozessors auf. Der Präprozessor wird überarbeitet. Diese Änderungen werden bald experimentell im Modus [/permissive-](../build/reference/permissive-standards-conformance.md) ausgeliefert.

<a name="note_D"></a>__D__ Unterstützt unter [/std:c++14](../build/reference/std-specify-language-standard-version.md), mit einer unterdrückbaren Warnung (C4984).

<a name="note_E"></a>__E__ Dies ist eine neue Implementierung, die nicht mit der vorherigen `std::experimental`-Version kompatibel ist. Sie ist aufgrund von Symlink-Unterstützung, Fehlerbehebungen und Änderungen des erforderlichen Standardverhaltens erforderlich. Wenn \<filesystem> verwendet wird, schließt dies aktuell das neue `std::filesystem`- und das vorherige `std::experimental::filesystem`-Element ein, und wenn \<experimental/filesystem> verwendet wird, schließt dies nur die alte experimentelle Implementierung ein. Die experimentelle Implementierung wird mit dem nächsten ABI unterbrechenden Release der Bibliotheken entfernt.

<a name="note_F"></a>__F__ Features, die in Visual Studio 2015 noch nicht abgeschlossen waren, werden an anderer Stelle in dieser Tabelle aufgeführt.

<a name="note_G"></a>__G__ Unterstützt durch eine intrinsische Compilerfunktion.

<a name="note_14"></a>__14__ Diese C++17/20-Features sind immer aktiviert, auch wenn [/std:c++14](../build/reference/std-specify-language-standard-version.md) (Standard) angegeben ist. Dies kann daran liegen, dass das Feature vor der Einführung der **/std**-Optionen implementiert wurde, oder daran, dass die bedingte Implementierung unerwünscht komplex war.

<a name="note_17"></a>__17__ Diese Features werden durch die Compileroption [/std:c++17](../build/reference/std-specify-language-standard-version.md) (oder [/std:c++latest](../build/reference/std-specify-language-standard-version.md)) aktiviert.

<a name="note_20"></a>__20__ Diese Features werden durch die Compileroption [/std:c++latest](../build/reference/std-specify-language-standard-version.md) aktiviert. Wenn die C ++ 20-Implementierung abgeschlossen ist, wird die neue Compileroption **/std:c++20** hinzugefügt.

<a name="note_byte"></a>__byte__ `std::byte` wird durch [/std:c++17](../build/reference/std-specify-language-standard-version.md) (oder [/std:c++latest](../build/reference/std-specify-language-standard-version.md)) aktiviert, da jedoch in einigen Fällen Konflikte mit den Windows SDK-Headern auftreten können, ist ein differenziertes Makro für die Abwahl vorhanden. Die Deaktivierung erfolgt durch Definieren von `_HAS_STD_BYTE` als `0`.

<a name="note_C11"></a>__C11__ Die Universal CRT implementierte die Teile der C11-Standardbibliothek, die für C++17 erforderlich sind, mit Ausnahme der `strftime()`-Bezeichner in C99 für die alternative E/O-Konvertierung, dem exklusiven `fopen()`-Modus in C11 und der `aligned_alloc()`-Funktion in C11. Die Implementierung der letztgenannten Funktion ist unwahrscheinlich, da C11 `aligned_alloc()` auf eine Weise angibt, die mit der Microsoft-Implementierung von `free()` nicht kompatibel ist. Insbesondere muss `free()` in der Lage sein, hochgradig ausgerichtete Zuweisungen zu verarbeiten.

<a name="note_rem"></a>__rem__ Diese Features wurden entfernt, als die Compileroption [/std:c++17](../build/reference/std-specify-language-standard-version.md) (oder [/std:c++latest](../build/reference/std-specify-language-standard-version.md)) angegeben wurde. Diese Features können erneut aktiviert werden, um die Umstellung auf neuere Sprachmodi zu vereinfachen, indem diese Makros verwendet werden: `_HAS_AUTO_PTR_ETC`, `_HAS_FUNCTION_ALLOCATOR_SUPPORT`, `_HAS_OLD_IOSTREAMS_MEMBERS` und `_HAS_UNEXPECTED`.

<a name="note_charconv"></a>__charconv__ `from_chars()` und `to_chars()` sind für ganze Zahlen verfügbar. Die Zeitachse für `from_chars()` (Gleitkomma) und `to_chars()` (Gleitkomma) lautet wie folgt:
- VS 2017 15.7: `from_chars()` (ganze Zahl) und `to_chars()`.
- VS 2017 15.8: `from_chars()` (Gleitkomma).
- VS 2017 15.9: `to_chars()`-Überladungen (Gleitkomma) für kürzeste Dezimalzahl.
- VS 2019 16.0: `to_chars()`-Überladungen (Gleitkomma) für kürzesten und genauen Hexadezimalwert.
- VS 2019 16.2: `to_chars()`-Überladungen (Gleitkomma) für Genauigkeit (feststehend und wissenschaftlich).
- Noch nicht implementiert: `to_chars()`-Überladung (Gleitkomma) für Genauigkeit (allgemein). 

<a name ="note_parallel"></a> __parallel__ Die Bibliothek mit parallelen Algorithmen von C++17 ist vollständig. Dies bedeutet nicht, dass jeder Algorithmus in jedem Fall parallel ist. Die wichtigsten Algorithmen wurden parallelisiert, und Ausführungsrichtliniensignaturen werden auch dann angegeben, wenn Algorithmen nicht parallelisiert wurden. Der zentrale interne Header der Implementierung (yvals_core.h) enthält folgende Anmerkungen zu parallelen Algorithmen: In C++ kann eine Implementierung parallele Algorithmen aus Aufrufe von seriellen Algorithmen implementieren.  Diese Implementierung parallelisiert einige aber nicht alle gängigen Algorithmusaufrufe.

Die folgenden Algorithmen werden parallelisiert:

- `adjacent_difference`, `adjacent_find`, `all_of`, `any_of`, `count`, `count_if`, `equal`, `exclusive_scan`, `find`, `find_end`, `find_first_of`, `find_if`, `find_if_not`, `for_each`, `for_each_n`, `inclusive_scan`, `is_heap`, `is_heap_until`, `is_partitioned`, `is_sorted`, `is_sorted_until`, `mismatch`, `none_of`, `partition`, `reduce`, `remove`, `remove_if`, `replace`, `replace_if`, `search`, `search_n`, `set_difference`, `set_intersection`, `sort`, `stable_sort`, `transform`, `transform_exclusive_scan`, `transform_inclusive_scan`, `transform_reduce`

Die folgenden Algorithmen werden aktuell nicht parallelisiert:

- Keine sichtbare Verbesserung der Leistung durch Parallelität auf der Zielhardware. Alle Algorithmen, die Elemente ohne Branches nur kopieren oder verschieben, verfügen normalerweise über eine Begrenzung der Arbeitsspeicherbandbreite:
  - `copy`, `copy_n`, `fill`, `fill_n`, `move`, `reverse`, `reverse_copy`, `rotate`, `rotate_copy`, `shift_left`, `shift_right`, `swap_ranges`
- Benutzerparallelitätsanforderungen können unklar sein. Können vermutlich der oben stehenden Kategorie zugeordnet werden:
  - `generate`, `generate_n`
- Effektive Parallelität kann wahrscheinlich nicht erreicht werden:
  - `partial_sort`, `partial_sort_copy`
- Noch nicht ausgewertet. Möglicherweise wird die Parallelität in einem kommenden Release implementiert, vermutlich positive Auswirkungen:
  - `copy_if`, `includes`, `inplace_merge`, `lexicographical_compare`, `max_element`, `merge`, `min_element`, `minmax_element`, `nth_element`, `partition_copy`, `remove_copy`, `remove_copy_if`, `replace_copy`, `replace_copy_if`, `set_symmetric_difference`, `set_union`, `stable_partition`, `unique`, `unique_copy`

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)<br/>
[Verbesserungen der C++-Konformität in Visual Studio](cpp-conformance-improvements.md)<br/>
[Neues bei Visual C++ in Visual Studio 2015](what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Änderungsverlauf von Visual C++ von 2003 bis 2015](../porting/visual-cpp-change-history-2003-2015.md)<br/>
[Visual C++: Neuerungen von 2003 bis 2015](../porting/visual-cpp-what-s-new-2003-through-2015.md)<br/>
[C++-Teamblog](https://devblogs.microsoft.com/cppblog/)

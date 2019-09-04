---
title: Phasen der Übersetzung
ms.date: 08/29/2019
helpviewer_keywords:
- translation phases
- preprocessor, translation
- translation, compiler process
- preprocessor
- file translation [C++], compiler process
- files [C++], translation
ms.assetid: a7f7a8c9-e8ba-4321-9e50-ebfbbdcce9db
ms.openlocfilehash: d072c9aec48d815ba85f8a12576baa6447703f8c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218305"
---
# <a name="phases-of-translation"></a>Phasen der Übersetzung

C- und C++-Programme bestehen aus mindestens einer Quelldatei, von denen jede einen Teil des Texts des Programms enthält. Eine Quelldatei, zusammen mit IhrenIncludedateien, Dateien, die mithilfe der `#include` Präprozessordirektive eingeschlossen werden, aber keine Abschnitte mit Code einschließen, die von bedingten `#if`Kompilierungs Direktiven, wie z. b., entfernt werden, wird als  *Übersetzungseinheit*.

Quelldateien können zu unterschiedlichen Zeitpunkten übersetzt werden. Tatsächlich ist es üblich, nur veraltete Dateien zu übersetzen. Die übersetzten Übersetzungseinheiten können in separate Objektdateien oder in Objektcodebibliotheken verarbeitet werden. Diese separaten, übersetzten Übersetzungseinheiten werden anschließend verknüpft, um ein ausführbares Programm oder eine Dynamic Link Library (DLL) zu bilden. Weitere Informationen zu Dateien, die als Eingabe für den Linker verwendet werden können, finden Sie unter [Verknüpfen von Eingabedateien](../build/reference/link-input-files.md).

Übersetzungseinheiten können mit folgenden Methoden kommunizieren:

- Aufrufe der Funktionen, die über eine externe Bindung verfügen.

- Aufrufe der Klassenmemberfunktionen, die über eine externe Bindung verfügen.

- Direkte Änderung von Objekten, die über eine externe Bindung verfügen.

- Direkte Änderung von Dateien.

- Prozessübergreifende Kommunikation (nur für Microsoft Windows-basierte Anwendungen).

Die folgende Liste beschreibt die Phasen, in denen der Compiler Dateien übersetzt:

*Zeichen Zuordnung*\
Zeichen in Quelldatei werden zur internen Quelldarstellung zugeordnet. Trigraphsequenzen werden in dieser Phase in die interne Einzelzeichendarstellung konvertiert.

*Zeilen Zusammenführen von*\
Alle Zeilen, die mit einem umgekehrten schräg **\\** Strich () enden, gefolgt von einem Zeilen Umleitungs Zeichen, werden mit der nächsten Zeile in der Quelldatei verknüpft und bilden logische Linien aus den physischen Zeilen. Wenn Sie nicht leer ist, muss eine Quelldatei mit einem Zeilen vorzeilenzeichen enden, dem kein umgekehrter Schrägstrich vorangestellt ist.

*Tokenisierung*\
Die Quelldatei wird in Vorverarbeitungstoken und Leerstellenzeichen unterteilt. Kommentare in der Quelldatei werden jeweils durch ein Leerzeichen ersetzt. Zeilenumbruchzeichen werden beibehalten.

*Vorverarbeitung*\
Vorverarbeitungsanweisungen werden ausgeführt, und Makros werden in die Quelldatei erweitert. Die `#include`-Anweisung ruft die Übersetzung auf, die mit den vorherigen drei Übersetzungsschritten für jeden enthaltenen Text beginnt.

*Zeichensatz Zuordnung*\
Alle Quellzeichensatzmember und Escapesequenzen werden in ihre Äquivalente im Ausführungszeichensatz konvertiert. Für Microsoft C und C++ sind sowohl die Quell- als auch Ausführungszeichensätze ASCII.

*Verkettung von Zeichen folgen*\
Alle angrenzenden Zeichenfolgen und breiten Zeichenfolgenliterale werden verkettet. Beispiel: `"String " "concatenation"` wird zu `"String concatenation"`.

*Übersetzt*\
Alle Token werden sowohl syntaktisch als auch semantisch analysiert. Diese Token werden in Objektcode konvertiert.

*Verbindung*\
Alle externen Verweise werden aufgelöst, um ein ausführbares Programm oder eine Dynamic Link Library zu erstellen.

Der Compiler gibt während Phasen der Übersetzung, in denen er auf Syntaxfehler trifft, Warnungen oder Fehler aus.

Der Linker löst alle externen Verweise auf und erstellt ein ausführbares Programm oder eine DLL, indem mindestens eine getrennt verarbeitete Übersetzungseinheit mit Standardbibliotheken kombiniert wird.

## <a name="see-also"></a>Siehe auch

[Präprozessor](../preprocessor/preprocessor.md)

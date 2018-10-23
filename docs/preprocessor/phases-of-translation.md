---
title: Phasen der Übersetzung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- translation phases
- preprocessor, translation
- translation, compiler process
- preprocessor
- file translation [C++], compiler process
- files [C++], translation
ms.assetid: a7f7a8c9-e8ba-4321-9e50-ebfbbdcce9db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b72e861b2639b8cf1e2cdf8293461cb8b1a00813
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808732"
---
# <a name="phases-of-translation"></a>Phasen der Übersetzung

C- und C++-Programme bestehen aus mindestens einer Quelldatei, von denen jede einen Teil des Texts des Programms enthält. Eine Quelldatei wird zusammen mit ihren Includedateien (Dateien, die mithilfe der Präprozessordirektive `#include` eingeschlossen werden), aber ohne die Codeabschnitte, die von bedingten Kompilierungsdirektiven entfernt werden, wie beispielsweise `#if`, als "Übersetzungseinheit" bezeichnet.

Quelldateien können zu unterschiedlichen Zeiten übersetzt werden – tatsächlich werden häufig nur veraltete Dateien übersetzt. Die übersetzten Übersetzungseinheiten können in separate Objektdateien oder in Objektcodebibliotheken verarbeitet werden. Diese separaten, übersetzten Übersetzungseinheiten werden anschließend verknüpft, um ein ausführbares Programm oder eine Dynamic Link Library (DLL) zu bilden.  Weitere Informationen zu Dateien, die als Eingabe für den Linker verwendet werden kann, finden Sie unter [LINK-Eingabedateien](../build/reference/link-input-files.md).

Übersetzungseinheiten können mit folgenden Methoden kommunizieren:

- Aufrufe der Funktionen, die über eine externe Bindung verfügen.

- Aufrufe der Klassenmemberfunktionen, die über eine externe Bindung verfügen.

- Direkte Änderung von Objekten, die über eine externe Bindung verfügen.

- Direkte Änderung von Dateien.

- Prozessübergreifende Kommunikation (nur für Microsoft Windows-basierte Anwendungen).

Die folgende Liste beschreibt die Phasen, in denen der Compiler Dateien übersetzt:

*Zeichenzuordnung*<br/>
Zeichen in Quelldatei werden zur internen Quelldarstellung zugeordnet. Trigraphsequenzen werden in dieser Phase in die interne Einzelzeichendarstellung konvertiert.

*Zusammenführen von Zeilen*<br/>
Alle Zeilen, die in einem umgekehrten Schrägstrich enden (**\\**) und daraufhin ein durch einen Zeilenvorschub Zeichen verknüpft sind, mit der nächsten Zeile in der Quelldatei, die logische Zeilen aus den physischen Zeilen gebildet. Falls eine Quelldatei nicht leer ist, muss sie mit einem Zeilenumbruchzeichen enden, dem kein umgekehrter Schrägstrich vorangestellt ist.

*Tokenisierung*<br/>
Die Quelldatei wird in Vorverarbeitungstoken und Leerstellenzeichen unterteilt. Kommentare in der Quelldatei werden jeweils durch ein Leerzeichen ersetzt. Zeilenumbruchzeichen werden beibehalten.

*Die vorverarbeitung*<br/>
Vorverarbeitungsanweisungen werden ausgeführt, und Makros werden in die Quelldatei erweitert. Die `#include`-Anweisung ruft die Übersetzung auf, die mit den vorherigen drei Übersetzungsschritten für jeden enthaltenen Text beginnt.

*Zeichensatzzuordnung*<br/>
Alle Quellzeichensatzmember und Escapesequenzen werden in ihre Äquivalente im Ausführungszeichensatz konvertiert. Für Microsoft C und C++ sind sowohl die Quell- als auch Ausführungszeichensätze ASCII.

*Verketten von Zeichenfolgen*<br/>
Alle angrenzenden Zeichenfolgen und breiten Zeichenfolgenliterale werden verkettet. Beispiel: `"String " "concatenation"` wird zu `"String concatenation"`.

*Übersetzung*<br/>
Alle Token werden sowohl syntaktisch als auch semantisch analysiert. Diese Token werden in Objektcode konvertiert.

*Verknüpfung*<br/>
Alle externen Verweise werden aufgelöst, um ein ausführbares Programm oder eine Dynamic Link Library zu erstellen.

Der Compiler gibt während Phasen der Übersetzung, in denen er auf Syntaxfehler trifft, Warnungen oder Fehler aus.

Der Linker löst alle externen Verweise auf und erstellt ein ausführbares Programm oder eine DLL, indem mindestens eine getrennt verarbeitete Übersetzungseinheit mit Standardbibliotheken kombiniert wird.

## <a name="see-also"></a>Siehe auch

[Präprozessor](../preprocessor/preprocessor.md)
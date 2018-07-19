---
title: Phasen der Übersetzung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 27e8e3a84d425966908bc1be37268c91cbbd34d8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842767"
---
# <a name="phases-of-translation"></a>Phasen der Übersetzung
C- und C++-Programme bestehen aus mindestens einer Quelldatei, von denen jede einen Teil des Texts des Programms enthält. Eine Quelldatei wird zusammen mit ihren Includedateien (Dateien, die mithilfe der Präprozessordirektive `#include` eingeschlossen werden), aber ohne die Codeabschnitte, die von bedingten Kompilierungsdirektiven entfernt werden, wie beispielsweise `#if`, als "Übersetzungseinheit" bezeichnet.  
  
 Quelldateien können zu unterschiedlichen Zeiten übersetzt werden – tatsächlich werden häufig nur veraltete Dateien übersetzt. Die übersetzten Übersetzungseinheiten können in separate Objektdateien oder in Objektcodebibliotheken verarbeitet werden. Diese separaten, übersetzten Übersetzungseinheiten werden anschließend verknüpft, um ein ausführbares Programm oder eine Dynamic Link Library (DLL) zu bilden.  Weitere Informationen zu Dateien, die als Eingabe an den Linker verwendet werden können, finden Sie unter [LINK-Eingabedateien](../build/reference/link-input-files.md).  
  
 Übersetzungseinheiten können mit folgenden Methoden kommunizieren:  
  
-   Aufrufe der Funktionen, die über eine externe Bindung verfügen.  
  
-   Aufrufe der Klassenmemberfunktionen, die über eine externe Bindung verfügen.  
  
-   Direkte Änderung von Objekten, die über eine externe Bindung verfügen.  
  
-   Direkte Änderung von Dateien.  
  
-   Prozessübergreifende Kommunikation (nur für Microsoft Windows-basierte Anwendungen).  
  
 Die folgende Liste beschreibt die Phasen, in denen der Compiler Dateien übersetzt:  
  
 *Zeichenzuordnung*  
 Zeichen in Quelldatei werden zur internen Quelldarstellung zugeordnet. Trigraphsequenzen werden in dieser Phase in die interne Einzelzeichendarstellung konvertiert.  
  
 *Zusammenführen von Zeilen*  
 Alle Zeilen in einem umgekehrten Schrägstrich enden (**\\**) und folgt unmittelbar ein Zeilenumbruchzeichen werden Zeichen mit der nächsten Zeile in der Quelldatei, die logische Zeilen aus den physischen Zeilen bilden verknüpft. Falls eine Quelldatei nicht leer ist, muss sie mit einem Zeilenumbruchzeichen enden, dem kein umgekehrter Schrägstrich vorangestellt ist.  
  
 *Zerlegung in Token*  
 Die Quelldatei wird in Vorverarbeitungstoken und Leerstellenzeichen unterteilt. Kommentare in der Quelldatei werden jeweils durch ein Leerzeichen ersetzt. Zeilenumbruchzeichen werden beibehalten.  
  
 *Vorverarbeiten*  
 Vorverarbeitungsanweisungen werden ausgeführt, und Makros werden in die Quelldatei erweitert. Die `#include`-Anweisung ruft die Übersetzung auf, die mit den vorherigen drei Übersetzungsschritten für jeden enthaltenen Text beginnt.  
  
 *Zeichensatzzuordnung*  
 Alle Quellzeichensatzmember und Escapesequenzen werden in ihre Äquivalente im Ausführungszeichensatz konvertiert. Für Microsoft C und C++ sind sowohl die Quell- als auch Ausführungszeichensätze ASCII.  
  
 *Verketten von Zeichenfolgen*  
 Alle angrenzenden Zeichenfolgen und breiten Zeichenfolgenliterale werden verkettet. Beispiel: `"String " "concatenation"` wird zu `"String concatenation"`.  
  
 *Übersetzung*  
 Alle Token werden sowohl syntaktisch als auch semantisch analysiert. Diese Token werden in Objektcode konvertiert.  
  
 *Verknüpfung*  
 Alle externen Verweise werden aufgelöst, um ein ausführbares Programm oder eine Dynamic Link Library zu erstellen.  
  
 Der Compiler gibt während Phasen der Übersetzung, in denen er auf Syntaxfehler trifft, Warnungen oder Fehler aus.  
  
 Der Linker löst alle externen Verweise auf und erstellt ein ausführbares Programm oder eine DLL, indem mindestens eine getrennt verarbeitete Übersetzungseinheit mit Standardbibliotheken kombiniert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessor](../preprocessor/preprocessor.md)
---
title: Spezielle Memberfunktionen
ms.date: 12/06/2016
helpviewer_keywords:
- special member functions [C++]
- constructors [C++]
- destructors [C++]
- copy operators [C++]
- move operators [C++]
- assignment operators [C++]
ms.assetid: 017d6817-b012-44f0-b153-f3076c251ea7
ms.openlocfilehash: 3b26628fd18749bd19819fe787888fd3264a79d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535759"
---
# <a name="special-member-functions"></a>Spezielle Memberfunktionen

Die *spezielle Memberfunktionen* -Klasse (oder Struktur) Member-Funktionen auf, dass der Compiler in bestimmten Fällen automatisch für Sie generiert werden. Diese Funktionen sind die [Standardkonstruktor](constructors-cpp.md#default_constructors), [Destruktor](destructors-cpp.md), [Kopierkonstruktor und Kopierzuweisungsoperator](copy-constructors-and-copy-assignment-operators-cpp.md), und die [bewegungskonstruktor und einen bewegungszuweisungsoperator](move-constructors-and-move-assignment-operators-cpp.md). Wenn Ihre Klasse eine oder mehrere der speziellen Memberfunktionen nicht definiert, klicken Sie dann der Compiler kann implizit zu deklarieren und definieren die Funktionen, die verwendet werden. Die vom Compiler generierter Implementierungen heißen die *Standard* spezielle Memberfunktionen. Der Compiler erzeugt Funktionen nicht, wenn sie nicht benötigt werden.

Sie können eine Standard-spezielle Memberfunktion explizit deklarieren, mit der **= Default** Schlüsselwort. Dies bewirkt, dass der Compiler an, definieren Sie die Funktion nur, wenn auf die gleiche Weise benötigt, als ob die Funktion nicht deklariert wurde.

In einigen Fällen kann der Compiler generieren *gelöscht* spezielle Memberfunktionen, die nicht definierte und daher nicht aufgerufen werden. Dies kann in Fällen auftreten, in denen eine bestimmte spezielle Memberfunktion in einer Klasse Sinn, weitere Eigenschaften der Klasse aufrufen nicht. Um die automatische Generierung von eine spezielle Memberfunktion explizit zu vermeiden, deklarieren Sie es wie mithilfe der **= Delete** Schlüsselwort.

Der Compiler generiert eine *Standardkonstruktor*, einen Konstruktor, der keine Argumente akzeptiert nur, wenn Sie nicht auf einen anderen Konstruktor deklariert haben. Wenn Sie nur einen Konstruktor, der Parameter annimmt deklariert haben, Code, der versucht, einen standardmäßigen Konstruktor aufzurufen, generiert der Compiler eine Fehlermeldung zu erzeugen. Der vom Compiler generierten Standardkonstruktor führt einfache member-wise [standardinitialisierung](initializers.md#default_initialization) des Objekts. Standardinitialisierung bewirkt, dass alle Membervariablen in einem unbestimmten Zustand.

Der Standarddestruktor führt jeden Member Zerstörung des Objekts. Es ist virtuell, nur dann, wenn ein Basisklassen-Destruktor virtuell ist.

Für die Standard-Kopie und verschiebungskonstruktion und Zuweisungsvorgängen führen elementweise Bitmuster kopiert oder verschiebt nicht statischen Datenmember. Verschieben Sie, dass Vorgänge nur generiert werden, wenn keine Destruktor oder Verschiebe-oder Kopiervorgänge deklariert werden. Ein Standardkonstruktor für die Kopie wird nur generiert, wenn kein Kopierkonstruktor deklariert wird. Es wird implizit gelöscht, wenn ein Verschiebevorgang deklariert ist. Ein Standard-Kopierzuweisungsoperator wird nur generiert, wenn kein Kopierzuweisungsoperator explizit deklariert wird. Es wird implizit gelöscht, wenn ein Verschiebevorgang deklariert ist.

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](cpp-language-reference.md)
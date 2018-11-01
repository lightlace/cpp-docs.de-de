---
title: 'Wert Kategorien: Lvalues und Rvalues (Visual C++)'
ms.date: 04/06/2018
helpviewer_keywords:
- R-values [C++]
- L-values [C++]
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
ms.openlocfilehash: 261453d5640c122f23491304b71e53e27c06eb7a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546353"
---
# <a name="lvalues-and-rvalues-visual-c"></a>Lvalues und Rvalues (Visual C++)

Jeder C++-Ausdruck weist einen Typ, und gehört zu einer *Wertkategorie*. Die Wert-Kategorien sind die Grundlage für die Regeln, die Compiler befolgen müssen, wenn erstellen, kopieren und verschieben Sie temporäre Objekte beim Auswerten des Ausdrucks.

C ++ 17-standard definiert Ausdruck Wert Kategorien wie folgt aus:

- Ein *Glvalue* ist ein Ausdruck, dessen Auswertung die Identität eines Objekts, die Bit-Feld oder die Funktion bestimmt.
- Ein *Prvalue* ist ein Ausdruck, dessen Auswertung Initialisiert ein Objekt oder ein Bit-Feld oder den Wert des Operanden der Bediener wird berechnet, wie vom Kontext angegeben, in dem sie erscheint.
- Ein *Xvalue* einen Glvalue, die kennzeichnet ein Objekt oder ein Bitfeld, dessen Ressourcen wiederverwendet werden können, (in der Regel, da es am Ende ihrer Lebensdauer ist) ist. [Beispiel: bestimmte Arten von Ausdrücken, die im Zusammenhang mit Rvalue-Referenzen (8.3.2) ergibt "XValues", z. B. einen Aufruf einer Funktion, deren Rückgabetyp ein Rvalue-Verweis ist, oder eine Umwandlung in einen Rvalue-Verweistyp. ]
- Ein *Lvalue* einen Glvalue, die keine Xvalue ist.
- Ein *Rvalue* ist ein Prvalue oder ein Xvalue.

Das folgende Diagramm veranschaulicht die Beziehungen zwischen den Kategorien:

![C++-Ausdruck Wert Kategorien](media/value_categories.png "C++-Ausdruck-Wert-Kategorien")

Ein Lvalue verfügt über eine Adresse, die das Programm zugreifen kann. Beispiele für l-Wert-Ausdrücke sind Namen von Variable, einschließlich **const** Variablen, die Elemente des Arrays, Funktionsaufrufe, die einen Lvalue-Verweis, Bitfelder, Unions und -Klasse, Elemente zurückgeben.

Ein Prvalue Ausdruck hat keine Adresse, die von Ihrem Programm zugänglich ist. Beispiele für Prvalue Ausdrücken sind Literale, Funktionsaufrufe, die einen Typ ohne Verweis zurückgeben und temporäre Objekte, die während der Auswertung des Ausdrucks aber zugegriffen werden kann nur vom Compiler erstellt werden.

Ein Xvalue Ausdruck verfügt über eine Adresse, die nicht mehr zugegriffen werden kann, durch das Programm jedoch um einen Rvalue-Verweis zu initialisieren, dadurch erhalten Sie Zugriff auf den Ausdruck verwendet werden können. Beispiele für sind die Funktionsaufrufe, die zurückgegeben werden Rvalue-Verweis, und der Arrayindex, Member und Zeiger auf Member-Ausdrücke, in dem das Array oder Objekt einen Rvalue-Verweis.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt mehrere korrekte und falsche Verwendungen von lvalues und rvalues:

```cpp
// lvalues_and_rvalues2.cpp
int main()
{
    int i, j, *p;

    // Correct usage: the variable i is an lvalue and the literal 7 is a prvalue.
    i = 7;

    // Incorrect usage: The left operand must be an lvalue (C2106).`j * 4` is a prvalue.
    7 = i; // C2106
    j * 4 = 7; // C2106

    // Correct usage: the dereferenced pointer is an lvalue.
    *p = i;

    const int ci = 7;
    // Incorrect usage: the variable is a non-modifiable lvalue (C3892).
    ci = 9; // C3892

    // Correct usage: the conditional operator returns an lvalue.
    ((i < 3) ? i : j) = 7;
}
```

> [!NOTE]
> Die Beispiele zu diesem Thema veranschaulichen die korrekte und falsche Verwendung, wenn Operatoren nicht überladen werden. Indem Sie Operatoren überladen, können Sie aus einem Ausdruck wie `j * 4` einen lvalue machen.

Die Begriffe *Lvalue* und *Rvalue* werden häufig verwendet werden, wenn Sie auf Objektverweise beziehen. Weitere Informationen über Verweise finden Sie unter [Lvalue-Verweisdeklarator: &](../cpp/lvalue-reference-declarator-amp.md) und [Rvalue-Verweisdeklarator: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>Siehe auch

[Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)<br/>
[Lvalue-Verweisdeklarator: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Rvalue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md)

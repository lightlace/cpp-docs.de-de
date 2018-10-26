---
title: Allgemeine Regeln für Operatorüberladung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operator overloading [C++], rules
ms.assetid: eb2b3754-35f7-4832-b1da-c502893dc0c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a6eb1b97acfe2fa41511433de3990da8923de7d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059544"
---
# <a name="general-rules-for-operator-overloading"></a>Allgemeine Regeln für die Überladung von Operatoren

Die folgenden Regeln schränken die Art und Weise ein, wie überladene Operatoren implementiert werden. Aber sie gelten nicht für die [neue](../cpp/new-operator-cpp.md) und [löschen](../cpp/delete-operator-cpp.md) Operatoren, die separat behandelt werden.

- Sie können keine neue Operatoren, z. B. definieren **.**.

- Sie können die Bedeutung von Operatoren nicht neu definieren, wenn sie auf integrierte Datentypen angewendet werden.

- Überladene Operatoren müssen entweder eine nicht statische Klassenmemberfunktion oder eine globale Funktion sein. Eine globale Funktion, die auf private oder geschützte Klassenmember zugreifen muss, muss als Friend dieser Klasse deklariert sein. Eine globale Funktion muss mindestens ein Argument annehmen, das vom Klassen- oder Aufzählungstyp ist, oder das ein Verweis auf einen Klassen- oder Aufzählungstyp ist. Zum Beispiel:

    ```cpp
    // rules_for_operator_overloading.cpp
    class Point
    {
    public:
        Point operator<( Point & );  // Declare a member operator
                                     //  overload.
        // Declare addition operators.
        friend Point operator+( Point&, int );
        friend Point operator+( int, Point& );
    };

    int main()
    {
    }
    ```

   Das vorhergehende Codebeispiel deklariert den Less Than-Operator als Memberfunktion. Allerdings werden die Additionsoperatoren als globale Funktionen deklariert, die Friend-Zugriff haben. Beachten Sie, dass mehr als eine Implementierung für einen angegebenen Operator bereitgestellt werden kann. Im Fall des vorhergehenden Additionsoperators werden die beiden Implementierungen bereitgestellt, um Kommutativität zu ermöglichen. Es ist ebenso wahrscheinlich, dass Operatoren, die hinzufügen eine `Point` auf eine `Point`, **Int** auf eine `Point`, und so weiter, implementiert werden könnte.

- Operatoren unterliegen der Priorität, Gruppierung und Anzahl von Operanden, die durch ihre typische Verwendung mit integrierten Typen vorgegeben werden. Daher besteht keine Möglichkeit, das Konzept "Hinzufügen von 2 und 3 zu einem Objekt vom Typ `Point`," erwartet 2 hinzugefügt werden die *x* Koordinate und 3, hinzugefügt werden die *y* zu koordinieren.

- Unäre Operatoren, die als Memberfunktionen deklariert werden, akzeptieren keine Argumente. Wenn sie als globale Funktionen deklariert werden, nehmen sie ein Argument an.

- Binäre Operatoren, die als Memberfunktionen deklariert werden, akzeptieren ein Argument. Wenn sie als globale Funktionen deklariert werden, nehmen sie zwei Argumente an.

- Wenn ein Operator entweder als unärer oder binärer Operator verwendet werden kann (__&__, __*__, __+__, und __-__), können Sie jede Verwendung separat überladen.

- Überladene Operatoren können keine Standardargumente haben.

- Alle überladenen Operatoren außer der Zuweisung (**Operator =**) werden von abgeleiteten Klassen geerbt.

- Das erste Argument für mit Memberfunktionen überladene Operatoren weist immer den Klassentyp des Objekts auf, für das der Operator aufgerufen wird (die Klasse, in der der Operator deklariert ist, oder eine Klasse, die von dieser Klasse abgeleitet ist). Es werden keine Konvertierungen für das erste Argument bereitgestellt.

Beachten Sie, dass die Bedeutung aller Operatoren vollständig geändert werden kann. Das schließt die Bedeutung des Address-of (**&**), Zuweisung (**=**), und funktionsaufrufoperatoren. Auch Identitäten, auf denen integrierte Typen basieren können, können mithilfe der Operatorüberladung geändert werden. Beispielsweise sind die folgenden vier Anweisungen normalerweise gleichwertig, wenn sie vollständig ausgewertet werden:

```cpp
var = var + 1;
var += 1;
var++;
++var;
```

Klassentypen, die Operatoren überladen, können nicht auf dieser Identität basieren. Darüber hinaus sind einige der Anforderungen, die für die Verwendung dieser Operatoren für grundlegende Typen gelten, für überladene Operatoren weniger strikt. Z. B. der Additions-/Zuweisungsoperator, **+=**, muss der linke Operand ein l-Wert, wenn auf grundlegende Typen angewendet werden. es ist dies nicht erforderlich, wenn der Operator überladen wird.

> [!NOTE]
> Aus Gründen der Konsistenz ist es oft am besten, beim Definieren überladener Operatoren das Modell der integrierten Typen zu befolgen. Wenn sich die Semantik eines überladenen Operators deutlich von seiner Bedeutung in anderen Kontexten unterscheidet, kann das eher verwirrend als nützlich sein.

## <a name="see-also"></a>Siehe auch

[Operatorüberladung](../cpp/operator-overloading.md)
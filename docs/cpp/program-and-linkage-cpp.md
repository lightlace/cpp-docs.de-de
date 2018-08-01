---
title: Programme und Verknüpfung (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a6493ba0-24e2-4c89-956e-9da1dea660cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9998e7ad9605d6d2e32bcaff6204fb09dcbca2a5
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405557"
---
# <a name="program-and-linkage-c"></a>Programm und Verknüpfung (C++)

In einem C++-Programm eine *Symbol*, z. B. ein Namen Variablen- oder Funktionsname, kann eine beliebige Anzahl von Zeiten innerhalb seines Bereichs deklariert werden kann nur einmal definiert werden. Dies ist eine Definition Regel (ODR). Ein *Deklaration* einen Namen in das Programm führt (oder wieder eingeführt wird). Ein *Definition* führt einen Namen ein, und bei einer Variablen, explizit initialisiert. Ein *Funktion Definition* setzt sich aus der Signatur sowie den Hauptteil der Funktion.

Diese sind Deklarationen:

```cpp
int i;
int f(int x);
```

Dies sind die Definitionen:

```cpp
int i{42};
int f(int x){ return x * i; }
```

Ein Programm besteht aus einer oder mehreren *Übersetzungseinheiten*. Eine Übersetzungseinheit besteht aus einer Implementierungsdatei (.cpp, .cxx usw.) und alle Header (. h, .hpp usw.), die ihn direkt oder indirekt enthält. Jede Übersetzungseinheit einzeln kompiliert wird, durch den Compiler an, nach dem führt der Linker die kompilierten Übersetzungseinheiten in einem einzelnen *Programm*. Verstöße gegen diese Regel ODR angezeigt in der Regel als Linker-Fehler bei den gleichen Namen zwei verschiedene Definitionen in unterschiedlichen Übersetzungseinheiten hat.

Im Allgemeinen ist die beste Möglichkeit, eine Variable in mehreren Dateien sichtbar zu machen, fügen Sie ihn in einer Headerdatei und Hinzufügen einer #include-Direktive in alle cpp-Datei, die die Deklaration erfordert. Durch Hinzufügen von *#include-Schutz* rund um den Inhalt des Headers, Sie stellen Sie sicher, dass die Namen, die es deklariert nur einmal definiert werden.

In einigen Fällen kann es jedoch erforderlich, deklarieren Sie eine globale Variable oder eine Klasse in einer CPP-Datei sein. In diesen Fällen benötigen Sie eine Möglichkeit, um den Compiler und Linker an, ob der Name des Objekts nur um die Datei, oder für alle Dateien gelten.

## <a name="linkage-vs-scope"></a>Die Verknüpfung im Vergleich mit Bereich

Das Konzept der *Verknüpfung* bezieht sich auf die die Sichtbarkeit der globalen Symbole (z. B. Variablen, Typnamen und Funktionsnamen) innerhalb des Programms als Ganzes in Übersetzungseinheiten. Das Konzept der *Bereich* bezieht sich auf die Symbole, die innerhalb eines Blocks wie z. B. einen Namespace, Klasse oder Funktion deklariert werden. Diese Symbole sind sichtbar, nur innerhalb des Bereichs, in dem sie definiert sind; das Konzept der Bindung gilt nicht für sie. 

## <a name="external-vs-internal-linkage"></a>Externe und interne Verknüpfung

Ein *Funktion freigeben* ist eine Funktion, die im globalen definiert ist oder im Namespacebereich. Globale Non-Const-Variablen und freie Funktionen in der Standardeinstellung haben *externe Verknüpfung*; sind sie in jeder Übersetzungseinheit im Programm sichtbar. Aus diesem Grund kann keine anderen globales Objekt (Variable, Klassendefinition, usw.), Namen haben. Ein Symbol mit *interne Verknüpfung* oder *ohne Verknüpfung* ist nur innerhalb der Übersetzungseinheit, die in der sie deklariert ist sichtbar. Wenn Sie ein Namen intern verknüpft ist, kann der gleiche Namen in einer anderen Übersetzungseinheit vorhanden. Variablen, die mit Klassendefinitionen deklariert oder funktionsrümpfe haben keine Bindung. 

Sie können erzwingen, einen globalen Namen internen Verknüpfung verfügen, indem Sie explizit Deklaration als **statische**. Dies schränkt die Sichtbarkeit auf derselben Übersetzungseinheit, die in der sie deklariert ist. Beachten Sie, dass in diesem Kontext **statische** bedeutet etwas unterscheiden, wenn auf lokale Variablen angewendet wird.

Die folgenden Objekte eine interne Bindung haben, wird standardmäßig:
- const-Objekte
- "constexpr"-Objekte
- Typedefs
- statische Objekte im Gültigkeitsbereich des namespace

Um eine const Objekt externe Verknüpfung zu gewähren, deklarieren Sie sie als **"extern"** und ein Wert zugewiesen wird:

```cpp
extern const int value = 42;
```

Finden Sie unter ["extern"](extern-cpp.md) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch
 [Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)
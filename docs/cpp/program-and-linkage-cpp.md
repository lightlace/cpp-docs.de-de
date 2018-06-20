---
title: Programme und Verknüpfung (C++) | Microsoft Docs
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
ms.openlocfilehash: 2dba8698461636e292771fc1e5a4f5ac0a633e73
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238668"
---
# <a name="program-and-linkage-c"></a>Programm und Verknüpfung (C++)

In einem C++-Programm eine *Symbol*, z. B. ein Variable oder Funktion Namen können oft in ihrem Gültigkeitsbereich deklariert werden können nur einmal definiert werden. Hierbei handelt es sich um eine Definition Regel (ODR). Ein *Deklaration* führt einen Namen in das Programm (oder wieder eingeführt wird). Ein *Definition* führt einen Namen und, bei einer Variablen explizit initialisiert. Ein *Funktion Definition* besteht aus der Signatur sowie Hauptteil der Funktion.

Diese sind Deklarationen:

```cpp
int i;
int f(int x);
```

Dies sind Definitionen:

```cpp
int i{42};
int f(int x){ return x * i; }
```

Ein Programm besteht aus einer oder mehreren *Übersetzungseinheiten*. Eine Übersetzungseinheit besteht aus einer Implementierungsdatei (.cpp, .cxx usw.) und alle Header (. h, .hpp usw.), die sie direkt oder indirekt enthält. Jede Übersetzungseinheit wird unabhängig vom Compiler nach dem führt der Linker die kompilierten Übersetzungseinheiten in einem einzelnen kompiliert *Programm*. Verstöße gegen diese Regel ODR angezeigt in der Regel als Linker-Fehler bei den gleichen Namen in verschiedenen Übersetzungseinheiten zwei unterschiedliche Definitionen hat.

Im Allgemeinen ist die beste Möglichkeit, eine Variable in mehreren Dateien sichtbar zu machen, fügen Sie ihn in einer Headerdatei und Hinzufügen einer #include-Direktive in jeder cpp-Datei, die die Deklaration erforderlich sind. Durch Hinzufügen von *#include-Schutz* um den Inhalt des Headers, Sie stellen Sie sicher, dass die Namen, die es deklariert nur einmal definiert werden.

In einigen Fällen kann es erforderlich, deklarieren Sie eine globale Variable oder eine Klasse in einer CPP-Datei sein. In diesen Fällen benötigen Sie eine Möglichkeit, um den Compiler und Linker gibt an, ob der Name des Objekts nur auf eine Datei oder auf alle Dateien angewendet wird.

## <a name="linkage-vs-scope"></a>Die Verknüpfung im Vergleich zu Bereich

Das Konzept der *Verknüpfung* bezieht sich auf die Sichtbarkeit der globalen Symbole (z. B. Variablen, Typnamen und Funktionsnamen) innerhalb des Programms als Ganzes über Übersetzungseinheiten befinden. Das Konzept der *Bereich* bezieht sich auf die Symbole, die innerhalb eines Blocks z. B. Namespace, Klasse oder Funktionsrumpf deklariert werden. Diese Symbole sind nur innerhalb des Bereichs, in dem sie definiert sind. das Konzept der Bindung gilt nicht für sie. 

## <a name="external-vs-internal-linkage"></a>Externe und interne Verknüpfung

Ein *frei Funktion* ist eine Funktion, die im globalen definiert ist oder Namespacebereich. Globale Non-Const-Variablen und free-Funktionen in der Standardeinstellung haben *externe Verknüpfung*; sind sie in jeder Übersetzungseinheit im Programm sichtbar. Aus diesem Grund kann keine anderen globalen Objekt (Variable, Klassendefinition usw.), Namen haben. Ein Symbol mit *interne Verknüpfung* oder *ohne Verknüpfung* ist nur innerhalb der Übersetzungseinheit, die in der sie deklariert ist. Wenn ein internen Verknüpfung aufweist, kann der gleiche Namen in einer anderen Übersetzungseinheit vorhanden. Variablen mit Klassendefinitionen deklariert oder Funktionsrümpfen haben keine Bindung. 

Sie können erzwingen, einen globalen Namen internen Verknüpfung verfügen, indem Sie explizit Deklaration als **statische**. Dies schränkt die Sichtbarkeit auf derselben Übersetzungseinheit, die in der sie deklariert ist. Beachten Sie, dass in diesem Kontext **statische** bedeutet, dass etwas anderes als wenn Sie auf lokale Variablen angewendet.

Die folgenden Objekte eine interne Bindung haben, wird standardmäßig:
- const-Objekte
- Constexpr-Objekte
- Typedefs
- statische Objekte im Gültigkeitsbereich des namespace

Um eine const Objekt externe Verknüpfung zu gewähren, deklarieren Sie es als **"extern"** und ihr einen Wert zuweisen:

```cpp
extern const int value = 42;
```

Finden Sie unter ["extern"](extern-cpp.md) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

 [Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)
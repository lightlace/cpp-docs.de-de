---
title: Bereich (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/08/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], scope
- scope [C++]
- function prototypes [C++], scope
- class scope
- prototype scope
- functions [C++], scope
- scope, C++ names
ms.assetid: 81fecbb0-338b-4325-8332-49f33e716352
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e79ae7f861553ce2bcd7bee6cbb14a3c2965d4ce
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36261058"
---
# <a name="scope-c"></a>Gültigkeitsbereich (C++)

"Wenn Sie ein Programmelement, z. B. eine Klasse, eine Funktion oder eine Variable deklarieren, seinen Namen kann nur werden angezeigt" und in bestimmte Teile des Programms verwendet. Der Kontext, in dem ein Name sichtbar ist, heißt die *Bereich*. Wenn Sie eine Variable deklarieren z. B. `x` innerhalb einer Funktion `x` ist nur innerhalb dieses Texts Funktion sichtbar. Es wurde *lokalen Gültigkeitsbereich*. Andere Variablen Umständen mit dem gleichen Namen im Programm müssen unter; solange sie sich in unterschiedlichen Bereichen befinden, sie die Regeln mit einer Definition nicht verletzt, und kein Fehler ausgelöst.

Für automatische nicht statischen Variablen bestimmt Bereich auch wenn sie erstellt und zerstört in Programmspeicher an. 

Es gibt sechs Arten von Gültigkeitsbereichen:

- **Globalen Gültigkeitsbereich** ein globaler Namen wird außerhalb von jeder Klasse, Funktion oder Namespace deklariert ist. Allerdings sind in C++ mit einem impliziten globalen Namespace auch diese Namen vorhanden. Der Gültigkeitsbereich von globalen Namen erweitert vom Zeitpunkt der Deklaration bis zum Ende der Datei, in der sie deklariert werden. Für globale Namen Sichtbarkeit auch unterliegen den Regeln der [Verknüpfung](program-and-linkage-cpp.md) die bestimmen, ob der Name in anderen Dateien in der Anwendung sichtbar ist.

- **Namespace-Gültigkeitsbereich** einen Namen, die in deklariert ist ein [Namespace](namespaces-cpp.md), außerhalb der Klasse oder eine Enumerationsklasse Definitionen oder Funktionsblocks, von dem Punkt der Deklaration bis zum Ende des Namespace sichtbar ist. Ein Namespace kann in mehreren Blöcken in unterschiedliche Dateien definiert werden.

- **Lokalen Gültigkeitsbereich** ein Namen, die innerhalb einer Funktion oder einem Lambda-Ausdruck, die Parameternamen, einschließlich deklariert haben lokale Gültigkeit. Sie werden häufig als "lokal" bezeichnet. Sie sind nur von dem Zeitpunkt der Deklaration bis zum Ende der Funktion oder einen Lambda-Text angezeigt. Lokaler Bereich ist eine Art von Blockbereich, der weiter unten in diesem Artikel erläutert wird.

- **Klassengültigkeitsbereich** Namen von Klassenmembern haben einen Klassengültigkeitsbereich, die in der Klassendefinition unabhängig von dem Zeitpunkt der Deklaration der gesamten erweitert. Klasse Memberzugriff ist weiteren gesteuert, indem Sie die **öffentlichen**, **private**, und **geschützt** Schlüsselwörter. Öffentlicher oder geschützter Member zugegriffen werden kann, nur mithilfe der memberauswahloperatoren (**.** oder **->**) oder Pointer-to-Member-Operatoren (**.\***  oder **-> \***).

- **Anweisung Bereich** deklarierten Namen im ein **für**, **Wenn**, **während**, oder **wechseln** Anweisung sind sichtbar, bis zum Ende der Anweisungsblock.

- **Funktionsgültigkeitsbereich** ein [Bezeichnung](labeled-statements.md) Gültigkeitsbereich der Funktion, d. h. es ist im gesamten sogar vor dem Punkt der Deklaration eines Funktionsrumpfs sichtbar ist. Gültigkeitsbereich der Funktion ermöglicht das Schreiben von Anweisungen wie `goto cleanup` vor der `cleanup` Bezeichnung wurde deklariert.

## <a name="hiding-names"></a>Ausblenden von Namen

Sie können einen Namen verbergen, indem Sie ihn in einem eingeschlossenen Block deklarieren. In der folgenden Abbildung wird `i` innerhalb des inneren Blocks neu deklariert. Dadurch wird die Variable ausgeblendet, die `i` im äußeren Blockbereich zugeordnet ist.

 ![Block&#45;Bereich Namen](../cpp/media/vc38sf1.png "vc38SF1") Blockbereich und Ausblenden von Namen

 Die in der Abbildung dargestellte Ausgabe des Programms lautet wie folgt:

```cpp
i = 0
i = 7
j = 9
i = 0
```

> [!NOTE]
> Es wird angenommen, dass das `szWhat`-Argument im Funktionsbereich liegt. Daher wird es so behandelt, als wäre es im äußersten Block der Funktion deklariert worden.

## <a name="hiding-class-names"></a>Ausblenden von Klassennamen

 Sie können Klassennamen ausblenden, indem Sie eine Funktion, ein Objekt, eine Variable oder einen Enumerator im gleichen Bereich deklarieren. Der Klassenname kann jedoch weiterhin zugegriffen werden, wenn das Schlüsselwort vorangestellt **Klasse**.

```cpp
// hiding_class_names.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

// Declare class Account at global scope.
class Account
{
public:
    Account( double InitialBalance )
        { balance = InitialBalance; }
    double GetBalance()
        { return balance; }
private:
    double balance;
};

double Account = 15.37;            // Hides class name Account

int main()
{
    class Account Checking( Account ); // Qualifies Account as 
                                       //  class name

    cout << "Opening account with balance of: "
         << Checking.GetBalance() << "\n";
}
//Output: Opening account with balance of: 15.37
```

> [!NOTE]
> Jeden Ort der Klassenname (`Account`) aufgerufen wird, für die Class-Schlüsselwort verwendet werden muss, damit sie aus dem globalen Bereich Variablen Konto unterscheidet. Diese Regel gilt nicht, wenn der Klassenname auf der linken Seite des Bereichsauflösungsoperators (::) auftritt. Namen auf der linken Seite des Bereichsauflösungsoperators gelten immer als Klassennamen.

 Im folgenden Beispiel wird veranschaulicht, wie einen Zeiger auf ein Objekt des Typs deklarieren `Account` mithilfe der **Klasse** Schlüsselwort:

```cpp
class Account *Checking = new class Account( Account );
```

 Die `Account` im Initialisierer (in Klammern) in der vorherigen Anweisung wurde globalen Gültigkeitsbereich; es ist vom Typ **doppelte**.

> [!NOTE]
> Die in diesem Beispiel dargestellte Wiederverwendung von Bezeichnernamen gilt als schlechter Programmierstil.

 Weitere Informationen über Zeiger finden Sie unter [Typen "Derived"](http://msdn.microsoft.com/en-us/aa14183c-02fe-4d81-95fe-beddb0c01c7c). Informationen über die Deklaration und Initialisierung von Klassenobjekten finden Sie unter [Klassen, Strukturen und Unions](../cpp/classes-and-structs-cpp.md). Informationen zum Verwenden der **neue** und **löschen** freien Speicheroperatoren, finden Sie unter [neue "und" delete](new-and-delete-operators.md).

## <a name="hiding-names-with-global-scope"></a>Ausblenden von Namen mit globalem Bereich

 Sie können Namen mit globalem Bereich ausblenden, indem Sie explizit den gleichen Namen im Blockbereich deklarieren. Jedoch globalen Gültigkeitsbereich Namen können zugegriffen werden, verwenden den Bereichsauflösungsoperator (`::`).

```cpp
#include <iostream>

int i = 7;   // i has global scope, outside all blocks
using namespace std;

int main( int argc, char *argv[] ) {
   int i = 5;   // i has block scope, hides i at global scope
   cout << "Block-scoped i has the value: " << i << "\n";
   cout << "Global-scoped i has the value: " << ::i << "\n";
}
```

```Output
Block-scoped i has the value: 5
Global-scoped i has the value: 7
```

## <a name="see-also"></a>Siehe auch

 [Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)
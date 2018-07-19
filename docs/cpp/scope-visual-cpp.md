---
title: Bereich (C++) | Microsoft-Dokumentation
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
ms.openlocfilehash: e8af021120c06465d0fd79ead79e2a18cb593803
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027608"
---
# <a name="scope-c"></a>Gültigkeitsbereich (C++)

Wenn Sie ein Programmelement, z. B. eine Klasse, Funktion oder Variable deklarieren, kann in bestimmten Teilen des Programms dessen Name nur "gesehen" und verwendet werden. Der Kontext, in dem ein Name sichtbar ist, heißt die *Bereich*. Wenn Sie eine Variable deklarieren z. B. `x` innerhalb einer Funktion `x` ist nur sichtbar innerhalb dieser Funktion. Sie verfügt über *lokalen Gültigkeitsbereich*. Sie weist möglicherweise andere Variablen mit dem gleichen Namen in Ihrem Programm auf; solange sie sich in unterschiedlichen Bereichen sind, werden sie nicht die One Definition Rule verletzt und kein Fehler ausgelöst.

Für automatische nicht statische Variablen bestimmt Umfang auch wenn sie erstellt und im Arbeitsspeicher des Programms zerstört werden. 

Es gibt sechs Arten von Gültigkeitsbereichen:

- **Globalen Gültigkeitsbereich** ein globaler Namen wird außerhalb von jeder Klasse, Funktion oder Namespace deklariert wird. Es gibt jedoch in C++, werden diese Namen mit einem impliziten globalen Namespace. Der Bereich der globale Namen erstreckt sich von dem Zeitpunkt der Deklaration an das Ende der Datei, in der sie deklariert werden. Für globale Namen Sichtbarkeit unterliegen außerdem den Regeln der [Verknüpfung](program-and-linkage-cpp.md) die bestimmen, ob der Name in anderen Dateien im Programm sichtbar ist.

- **Namespace-Gültigkeitsbereich** einen Namen, die in deklariert ist eine [Namespace](namespaces-cpp.md), außerhalb jeder Klasse oder Enumeration-Definition oder Funktionsblock, von dem Punkt der Deklaration bis zum Ende des Namespace sichtbar ist. Ein Namespace kann in mehreren Blöcken in verschiedene Dateien definiert werden.

- **Lokalen Gültigkeitsbereich** ein Namen, die innerhalb einer Funktion oder einem Lambda-Ausdrucks die Parameternamen, einschließlich deklariert haben lokale Gültigkeit. Sie werden häufig als "lokal" bezeichnet. Sie sind nur von dem Zeitpunkt der Deklaration bis zum Ende der Funktion oder einem Lambda-Text angezeigt. Lokaler Bereich ist eine Art von Blockbereich, der später in diesem Artikel erläutert wird.

- **Klassengültigkeitsbereich** Namen von Klassenmembern haben einen Klassengültigkeitsbereich, die in der gesamten Definition der Klasse, unabhängig von dem Zeitpunkt der Deklaration erweitert. Klasse Memberzugriff ist daran gesteuert durch die **öffentliche**, **private**, und **geschützt** Schlüsselwörter. Öffentlicher oder geschützter Member zugegriffen werden kann, nur mithilfe der memberauswahloperatoren (**.** oder **->**) oder Pointer-to-Member-Operatoren (**.\***  oder **-> \***).

- **-Anweisungsbereichs** Namen deklariert wird, eine **für**, **Wenn**, **während**, oder **wechseln** Anweisung sind sichtbar, bis zum Ende der Anweisungsblock.

- **Funktionsgültigkeitsbereich** ein [Bezeichnung](labeled-statements.md) Funktionsbereich, das bedeutet, dass es überall in einem Funktionsrumpf, sogar vor dem Punkt der Deklaration. Gültigkeitsbereich der Funktion ermöglicht es, schreiben die Anweisungen wie `goto cleanup` vor der `cleanup` Bezeichnung deklariert wird.

## <a name="hiding-names"></a>Ausblenden von Namen

Sie können einen Namen verbergen, indem Sie ihn in einem eingeschlossenen Block deklarieren. In der folgenden Abbildung wird `i` innerhalb des inneren Blocks neu deklariert. Dadurch wird die Variable ausgeblendet, die `i` im äußeren Blockbereich zugeordnet ist.

 ![Block&#45;Bereich Ausblenden von Namen](../cpp/media/vc38sf1.png "vc38SF1") Blockbereich und Ausblenden von Namen

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

 Sie können Klassennamen ausblenden, indem Sie eine Funktion, ein Objekt, eine Variable oder einen Enumerator im gleichen Bereich deklarieren. Jedoch den Namen der Klasse kann weiterhin zugegriffen werden, wenn das Schlüsselwort vorangestellt **Klasse**.

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
> Alle platzieren Sie den Namen der Klasse (`Account`) wird aufgerufen, für die Class-Schlüsselwort verwendet werden muss, um es aus dem globalen Bereich Variablen Konto zu unterscheiden. Diese Regel gilt nicht, wenn der Klassenname auf der linken Seite des Bereichsauflösungsoperators (::) auftritt. Namen auf der linken Seite des Bereichsauflösungsoperators gelten immer als Klassennamen.

 Im folgende Beispiel wird veranschaulicht, wie einen Zeiger auf ein Objekt des Typs deklarieren `Account` mithilfe der **Klasse** Schlüsselwort:

```cpp
class Account *Checking = new class Account( Account );
```

 Die `Account` im Initialisierer (in Klammern) in der vorherigen Anweisung hat einen globalen Gültigkeitsbereich, sondern vom Typ **doppelte**.

> [!NOTE]
> Die in diesem Beispiel dargestellte Wiederverwendung von Bezeichnernamen gilt als schlechter Programmierstil.

 Weitere Informationen über Zeiger finden Sie unter [abgeleitete Typen](http://msdn.microsoft.com/aa14183c-02fe-4d81-95fe-beddb0c01c7c). Weitere Informationen über die Deklaration und Initialisierung von Klassenobjekten finden Sie unter [Klassen, Strukturen und Unions](../cpp/classes-and-structs-cpp.md). Informationen zur Verwendung der **neue** und **löschen** freien Speicheroperatoren, finden Sie unter [neue "und" delete](new-and-delete-operators.md).

## <a name="hiding-names-with-global-scope"></a>Ausblenden von Namen mit globalem Bereich

 Sie können Namen mit globalem Bereich ausblenden, indem Sie explizit den gleichen Namen im Blockbereich zu deklarieren. Jedoch globale-Bereichsnamen können zugegriffen werden, verwenden den Bereichsauflösungsoperator (`::`).

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
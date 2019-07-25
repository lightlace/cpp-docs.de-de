---
title: Verwenden von C++-Bibliotheksheadern
ms.date: 11/04/2016
helpviewer_keywords:
- headers, naming in C++ include directive
- standard header in C++
- headers
- INCLUDE directive
- headers, C++ Standard Library
- library headers
- C++ Standard Library, headers
ms.assetid: a36e889e-1af2-4cd9-a211-bfc7a3fd8e85
ms.openlocfilehash: 9cc0bb51b159f6668adad05ebd2d386364ae2f81
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450064"
---
# <a name="using-c-library-headers"></a>Verwenden von C++-Bibliotheksheadern

Der Inhalt eines Standardheaders kann durch Benennen in einer include-Direktive eingebunden werden.

```cpp
#include <iostream>// include I/O facilities
```

Die Standardheader können in beliebiger Reihenfolge eingebunden werden. Ein Standardheader kann mehrmals eingebunden werden. Und es können mehrere Standardheader eingebunden werden, die dasselbe Makro oder denselben Typ definieren. Ein Standardheader darf jedoch nicht in eine Deklaration eingebunden werden. Definieren Sie keine Makros, die dieselben Namen wie Schlüsselwörter haben, bevor Sie einen Standardheader einschließen.

Ein C++-Bibliotheksheader enthält alle anderen C++-Bibliotheksheader, die zum Definieren der erforderlichen Typen benötigt werden. (In einer Übersetzungseinheit benötigte C++-Bibliotheksheader müssen immer explizit eingebunden werden, damit keine falschen Annahmen über die tatsächlichen Abhängigkeiten getroffen werden.) Ein C-Standardheader enthält niemals einen anderen Standardheader. Mit einem Standardheader werden lediglich die in diesem Dokument hierfür beschriebenen Entitäten deklariert bzw. definiert.

Alle Funktionen in der Bibliothek werden in einem Standardheader deklariert. Im Gegensatz zu Standard C wird vom Standardheader kein Maskierungsmakro mit demselben Namen wie die Funktion bereitgestellt, das die Funktionsdeklaration maskiert und denselben Effekt erzielt. Weitere Informationen zu Maskierungsmakros finden Sie unter [C++ Library Conventions (C++-Bibliothekskonventionen)](../standard-library/cpp-library-conventions.md).

Alle Namen außer **Operator Delete** und **Operator new** in C++ den Bibliotheks `std` Headern werden im-Namespace oder in einem Namespace definiert, der `std` im-Namespace geschachtelt ist. Auf den Namen `cin` wird beispielsweise mit `std::cin` verwiesen. Makronamen unterliegen nicht der Namespacequalifikation. Daher wird `__STD_COMPLEX` ohne Namespacequalifizierer geschrieben.

In einigen Übersetzungs Umgebungen kann das einschließen C++ eines Bibliotheks Headers externe Namen, die im `std` Namespace deklariert sind, ebenfalls in den globalen Namespace einbinden, wobei individuelle Deklarationen für die einzelnen Namen **verwendet** werden. Ist dies nicht der Fall, werden vom Header *keine* Bibliotheksnamen in den aktuellen Namespace eingeführt.

Der C++ Standard erfordert, dass die C-Standard Header alle externen Namen im Namespace `std`deklarieren und Sie dann in den globalen Namespace mit Einzelpersonen **mithilfe** von Deklarationen für die einzelnen Namen anheben. In einigen Übersetzungsumgebungen enthalten die C-Standardheader jedoch keine Namespacedeklarationen. Stattdessen werden alle Namen direkt im globalen Namespace deklariert. Somit wird das Ergebnis am besten portierbar, wenn im Umgang mit Namespaces zwei Regeln befolgt werden:

- Deklarieren Sie einen externen Namen, der traditionell in \<stdlib.h> deklariert wird, unbedingt in Namespace `std`, indem Sie beispielsweise den Header \<cstdlib> einbinden. Beachten Sie, dass der Name möglicherweise auch im globalen Namespace deklariert wird.

- Deklarieren Sie einen externen, in \<stdlib.h> deklarierten Namen unbedingt im globalen Namespace, indem Sie den Header \<stdlib.h> direkt einbinden. Beachten Sie, dass der Name möglicherweise auch im Namespace `std` deklariert wird.

Wenn Sie also `std::abort` aufrufen möchten, um eine nicht normale Beendigung zu verursachen, binden Sie \<cstdlib> ein. Wenn Sie `abort` aufrufen möchten, binden Sie \<stdlib.h> ein.

Alternativ können Sie folgende Deklaration schreiben:

```cpp
using namespace std;
```

Damit werden alle Bibliotheksnamen in den aktuellen Namespace eingebunden. Wenn Sie diese Deklaration direkt nach den include-Direktiven einfügen, werden die Namen in den globalen Namespace gehoben. Danach müssen Sie sich in der restlichen Übersetzungseinheit um Namespaces keine Gedanken mehr zu machen. Außerdem umgehen Sie damit die meisten Differenzen zwischen unterschiedlichen Übersetzungsumgebungen.

Sofern nicht ausdrücklich anders angegeben, sollten Sie Namen nicht im Namespace `std` oder in einem Namespace angeben, der im Namespace `std` in Ihrem Programm geschachtelt ist.

## <a name="see-also"></a>Siehe auch

[Übersicht über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

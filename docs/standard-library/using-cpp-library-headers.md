---
title: Verwenden von C++-Bibliotheksheadern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- headers, naming in C++ include directive
- standard header in C++
- headers
- INCLUDE directive
- headers, C++ Standard Library
- library headers
- C++ Standard Library, headers
ms.assetid: a36e889e-1af2-4cd9-a211-bfc7a3fd8e85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2283e74c00867e373d2ba117fd5dfbf70f137c75
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966006"
---
# <a name="using-c-library-headers"></a>Verwenden von C++-Bibliotheksheadern

Der Inhalt eines Standardheaders kann durch Benennen in einer include-Direktive eingebunden werden.

```cpp
#include <iostream>// include I/O facilities
```

Die Standardheader können in beliebiger Reihenfolge eingebunden werden. Ein Standardheader kann mehrmals eingebunden werden. Und es können mehrere Standardheader eingebunden werden, die dasselbe Makro oder denselben Typ definieren. Ein Standardheader darf jedoch nicht in eine Deklaration eingebunden werden. Definieren Sie keine Makros, die dieselben Namen wie Schlüsselwörter haben, bevor Sie einen Standardheader einschließen.

Ein C++-Bibliotheksheader enthält alle anderen C++-Bibliotheksheader, die zum Definieren der erforderlichen Typen benötigt werden. (In einer Übersetzungseinheit benötigte C++-Bibliotheksheader müssen immer explizit eingebunden werden, damit keine falschen Annahmen über die tatsächlichen Abhängigkeiten getroffen werden.) Ein C-Standardheader enthält niemals einen anderen Standardheader. Mit einem Standardheader werden lediglich die in diesem Dokument hierfür beschriebenen Entitäten deklariert bzw. definiert.

Alle Funktionen in der Bibliothek werden in einem Standardheader deklariert. Im Gegensatz zu Standard C wird vom Standardheader kein Maskierungsmakro mit demselben Namen wie die Funktion bereitgestellt, das die Funktionsdeklaration maskiert und denselben Effekt erzielt. Weitere Informationen zu Maskierungsmakros finden Sie unter [C++ Library Conventions (C++-Bibliothekskonventionen)](../standard-library/cpp-library-conventions.md).

Alle Namen außer **Delete-Operator** und **new-Operator** in der C++-Standardbibliothek definiert sind die `std` -Namespace oder in einem Namespace geschachtelt die `std` Namespace. Auf den Namen `cin` wird beispielsweise mit `std::cin` verwiesen. Makronamen unterliegen nicht der Namespacequalifikation. Daher wird `__STD_COMPLEX` ohne Namespacequalifizierer geschrieben.

In einigen übersetzungsumgebungen, einschließlich einer C++-bibliotheksheader externe in deklarierte Namen auszudehnen kann die `std` Namespace in den globalen Namespace auch mit individuellen **mit** Deklarationen für die einzelnen Namen. Ist dies nicht der Fall, werden vom Header *keine* Bibliotheksnamen in den aktuellen Namespace eingeführt.

Die C++-Standard erfordert, dass die C-Standardheader alle externe Namen in Namespaces deklarieren `std`, klicken Sie dann in den globalen Namespace mit individuellen heben **mit** Deklarationen für die einzelnen Namen. In einigen Übersetzungsumgebungen enthalten die C-Standardheader jedoch keine Namespacedeklarationen. Stattdessen werden alle Namen direkt im globalen Namespace deklariert. Somit wird das Ergebnis am besten portierbar, wenn im Umgang mit Namespaces zwei Regeln befolgt werden:

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

[Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

---
title: '&lt;Ausführung&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: 3bce34019f9ed4880d72a9d16c3c8b78dde0e0e3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268422"
---
# <a name="ltexecutiongt"></a>&lt;Ausführung&gt;

Beschreibt die Ausführungsrichtlinien für parallele Algorithmen.

## <a name="syntax"></a>Syntax

```
namespace std {
    template<class T> inline constexpr bool is_execution_policy_v = is_execution_policy<T>::value;
}
namespace std::execution {
    inline constexpr sequenced_policy seq { unspecified };
    inline constexpr parallel_policy par { unspecified };
    inline constexpr parallel_unsequenced_policy par_unseq { unspecified };
}
```
### <a name="classes-and-structs"></a>Klassen und Strukturen

|||
|-|-|
|[Is_execution_policy-Struktur](is-execution-policy-struct.md)|Erkennt die Ausführungsrichtlinien für die Funktionssignaturen aus der Beteiligung von andernfalls mehrdeutige Überladung Auflösung ausschließen.|
|[Parallel_policy-Klasse](parallel-policy-class.md)|Als verwendet ein eindeutiger Typ zu unterscheiden, parallelen Algorithmus überladen und anzugeben, dass die Ausführung eines parallelen Algorithmus parallelisiert werden kann.|
|[Parallel_unsequenced_policy-Klasse](parallel-unsequenced-policy-class.md)|Als verwendet ein eindeutiger Typ zu unterscheiden, parallelen Algorithmus überladen und anzugeben, dass die Ausführung eines parallelen Algorithmus parallelisiert und vektorisiert werden kann.|
|[Sequenced_policy-Klasse](sequenced-policy-class.md)|Als verwendet ein eindeutiger Typ zu unterscheiden, parallelen Algorithmus überladen und erfordern, dass die Ausführung eines parallelen Algorithmus nicht parallelisiert werden kann.|

## <a name="requirements"></a>Anforderungen

**Header:** \<Ausführung >

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](cpp-standard-library-reference.md)

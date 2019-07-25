---
title: '&lt;Niederlage&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: 3b0ccd540c56500c2f265aa6192a12fc2d5078b0
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457967"
---
# <a name="ltexecutiongt"></a>&lt;Niederlage&gt;

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
|[is_execution_policy-Struktur](is-execution-policy-struct.md)|Erkennt Ausführungsrichtlinien, um Funktions Signaturen von der ansonsten mehrdeutigen Überladungs Auflösungs Beteiligung auszuschließen.|
|[parallel_policy-Klasse](parallel-policy-class.md)|Wird als eindeutiger Typ verwendet, um das überladen paralleler Algorithmen eindeutig zu machen und anzugeben, dass die Ausführung eines parallelen Algorithmus parallelisiert werden kann.|
|[parallel_unsequenced_policy-Klasse](parallel-unsequenced-policy-class.md)|Wird als eindeutiger Typ verwendet, um das überladen paralleler Algorithmen eindeutig zu machen und anzugeben, dass die Ausführung eines parallelen Algorithmus parallelisiert und vektorisiert werden kann.|
|[sequenced_policy-Klasse](sequenced-policy-class.md)|Wird als eindeutiger Typ verwendet, um das überladen paralleler Algorithmen zu unterscheiden, und erfordert, dass die Ausführung eines parallelen Algorithmus möglicherweise nicht parallelisiert wird.|

## <a name="requirements"></a>Anforderungen

**Header:** \<Ausführungs >

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](cpp-standard-library-reference.md)

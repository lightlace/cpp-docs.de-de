---
title: '&lt;cstdalign wurden&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdalign>
- cstdalign
- __alignas_is_defined
- __alignof_is_defined
helpviewer_keywords:
- cstdalign header
- __alignas_is_defined
- __alignof_is_defined
ms.assetid: 9d570924-d299-4225-9a58-8c4c820f5903
ms.openlocfilehash: 603a590190c50495aa80f1b41a574149eb8f760a
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2019
ms.locfileid: "68342839"
---
# <a name="ltcstdaligngt"></a>&lt;cstdalign wurden&gt;

In einigen C++ Implementierungen der Standardbibliothek schließt dieser Header den C-Standard Bibliotheks \<Header stdalign. h > ein und fügt die `std` verknüpften Namen zum-Namespace hinzu. Da dieser Header nicht in MSVC implementiert ist, \<definiert der cstdalign-> Header `__alignas_is_defined` die `__alignof_is_defined`Kompatibilitäts Makros und.

> [!NOTE]
> Da der \<stdalign. h->-Header Makros definiert, bei C++denen es sich um Schlüsselwörter in handelt, enthält die Datei keine Auswirkung. Der \<stdalign. h-> Header ist in C++veraltet. Der \<cstdalign-> Header ist in c++ 17 veraltet und wurde im Draft c++ 20-Standard entfernt.

## <a name="requirements"></a>Anforderungen

**Header:** \<cstdalign->

**Namespace:** std

## <a name="macros"></a>Makros

| Makro | Beschreibung |
| - | - |
| `__alignas_is_defined` | Ein C-Kompatibilitäts Makro, das auf die ganzzahlige Konstante 1 erweitert wird. |
| `__alignof_is_defined` | Ein C-Kompatibilitäts Makro, das auf die ganzzahlige Konstante 1 erweitert wird. |

## <a name="see-also"></a>Siehe auch

[Header Dateireferenz](cpp-standard-library-header-files.md)\
[C++Übersicht über die Standardbibliothek](cpp-standard-library-overview.md)\
[Thread Sicherheit in der C++ Standardbibliothek](thread-safety-in-the-cpp-standard-library.md)

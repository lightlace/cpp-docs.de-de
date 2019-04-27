---
title: Compilerfehler C2286
ms.date: 11/04/2016
f1_keywords:
- C2286
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
ms.openlocfilehash: 7d3b8297c5f5da29b99abe78999396e8c44df0fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182768"
---
# <a name="compiler-error-c2286"></a>Compilerfehler C2286

Zeiger auf Member der Darstellung von 'Bezeichner' ist bereits auf "Vererbung" - Deklaration ignoriert festgelegt

Zwei unterschiedliche Darstellungen der Zeiger auf Member, die für die Klasse vorhanden sein.

Weitere Informationen finden Sie unter [Vererbungsschlüsselwörter](../../cpp/inheritance-keywords.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2286 generiert:

```
// C2286.cpp
// compile with: /c
class __single_inheritance X;
class __multiple_inheritance X;   // C2286
class  __multiple_inheritance Y;   // OK
```
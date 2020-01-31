---
title: pointers_to_members-Pragma
ms.date: 08/29/2019
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
helpviewer_keywords:
- class members, pointers to
- pragmas, pointers_to_members
- members, pointers to
- pointers_to_members pragma
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
ms.openlocfilehash: 6058e3e4855eb745a01410e31eb9f454ef131ab1
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821407"
---
# <a name="pointers_to_members-pragma"></a>pointers_to_members-Pragma

**C++Zugeschnitten**

Gibt an, ob ein Zeiger auf einen Klassenmember vor der zugeordneten Klassendefinition deklariert werden kann. Wird zum Steuern der Zeiger Größe und des Codes verwendet, der zum Interpretieren des Zeigers erforderlich ist.

## <a name="syntax"></a>Syntax

> **#pragma pointers_to_members (** *Pointer-Declaration* [ **,** *Most-General-Repräsentation* ])

## <a name="remarks"></a>Hinweise

Sie können ein **pointers_to_members** -Pragma in der Quelldatei als Alternative zur Verwendung der [/vmb-oder/VMG](../build/reference/vmb-vmg-representation-method.md) -Compileroptionen oder der [Vererbungs Schlüsselwörter](../cpp/inheritance-keywords.md)platzieren.

Das *Pointer-Declaration-* Argument gibt an, ob Sie vor oder nach der zugeordneten Funktionsdefinition einen Zeiger auf einen Member deklariert haben. Das *Pointer-Declaration-* Argument ist eines der beiden folgenden Symbole:

| Argument | Comments |
|--------------|--------------|
| **full_generality** | Generiert sicheren, manchmal nicht optimalen Code. Sie verwenden **full_generality** , wenn ein Zeiger auf einen Member vor der zugeordneten Klassendefinition deklariert wird. Dieses Argument verwendet immer die durch das Argument der *allgemeinsten Darstellung* angegebene Zeiger Darstellung. Entspricht "/vmg". |
| **best_case** | Generiert sicheren, optimalen Code unter Verwendung von Best-Case-Darstellung für alle Zeiger auf Member. Erfordert die Definierung der Klasse vor dem Deklarieren eines Zeigers auf einen Member der Klasse. Der Standardwert ist **best_case**. |

Das Argument der *allgemeinsten Darstellung* gibt die kleinste Zeiger Darstellung an, die der Compiler sicher verwenden kann, um auf einen beliebigen Zeiger auf einen Member einer Klasse in einer Übersetzungseinheit zu verweisen. Das Argument kann einen der folgenden Werte aufweisen:

| Argument | Comments |
|--------------|--------------|
| **single_inheritance** | Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit einfacher Vererbung. Löst einen Fehler aus, wenn das Vererbungsmodell einer Klassendefinition, für die ein Zeiger auf ein Member deklariert wird, entweder mehrfach oder virtuell ist. |
| **multiple_inheritance** | Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit Mehrfachvererbung. Löst einen Fehler aus, wenn das Vererbungsmodell einer Klassendefinition, für die ein Zeiger auf ein Member deklariert wird, virtuell ist. |
| **virtual_inheritance** | Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit virtueller Vererbung. Löst nie einen Fehler aus. **virtual_inheritance** ist das Standardargument, wenn `#pragma pointers_to_members(full_generality)` verwendet wird. |

> [!CAUTION]
> Wir empfehlen Ihnen, das **pointers_to_members** -Pragma nur in der Quell Code Datei zu platzieren, die Sie beeinflussen möchten, und nur nach allen `#include` Direktiven. Diese Vorgehensweise verringert das Risiko, dass sich das Pragma auf andere Dateien auswirkt, und dass Sie versehentlich mehrere Definitionen für dieselbe Variable, Funktion oder denselben Klassennamen angeben.

## <a name="example"></a>Beispiel

```cpp
//   Specify single-inheritance only
#pragma pointers_to_members( full_generality, single_inheritance )
```

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

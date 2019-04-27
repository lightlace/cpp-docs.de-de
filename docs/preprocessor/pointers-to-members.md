---
title: pointers_to_members
ms.date: 11/04/2016
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
helpviewer_keywords:
- class members, pointers to
- pragmas, pointers_to_members
- members, pointers to
- pointers_to_members pragma
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
ms.openlocfilehash: 5ee45a77a7094fb1ef9ba536bae391aaad00e812
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180003"
---
# <a name="pointerstomembers"></a>pointers_to_members

**C++-spezifisch**

Gibt an, ob ein Zeiger auf einen Klassenmember vor der zugeordneten Klassendefinition deklariert werden kann und verwendet wird, um die Zeigergröße und den Code zu steuern, die zum Interpretieren des Zeigers erforderlich sind.

## <a name="syntax"></a>Syntax

```
#pragma pointers_to_members( pointer-declaration, [most-general-representation] )
```

## <a name="remarks"></a>Hinweise

Sie platzieren einen **Pointers_to_members** Pragma in der Quelldatei als Alternative zur Verwendung der [/vmx](../build/reference/vmb-vmg-representation-method.md) Compileroptionen oder [vererbungs-Schlüsselwörter](../cpp/inheritance-keywords.md).

Die *Zeigerdeklaration* Argument gibt an, ob einen Zeiger auf ein Element vor oder nach der zugeordneten Funktionsdefinition deklariert wurden. Die *Zeigerdeklaration* Argument ist eine der folgenden zwei Symbole:

|Argument|Kommentare|
|--------------|--------------|
|*full_generality*|Generiert sicheren, manchmal nicht optimalen Code. Verwenden Sie *Full_generality* , wenn ein Zeiger auf ein Element vor der zugeordneten Klassendefinition deklariert wird. Dieses Argument verwendet immer die zeigerdarstellung, die gemäß der *Most-General-Representation* Argument. Entspricht "/vmg".|
|*best_case*|Generiert sicheren, optimalen Code unter Verwendung von Best-Case-Darstellung für alle Zeiger auf Member. Erfordert die Definierung der Klasse vor dem Deklarieren eines Zeigers auf einen Member der Klasse. Der Standardwert ist *Best_case*.|

Die *Most-General-Representation* -Argument gibt die kleinste zeigerdarstellung, die der Compiler sicher verwenden können, auf einem Zeiger auf einen Member einer Klasse in einer Übersetzungseinheit zu verweisen. Das Argument kann eines der folgenden sein:

|Argument|Kommentare|
|--------------|--------------|
|*single_inheritance*|Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit einfacher Vererbung. Löst einen Fehler aus, wenn das Vererbungsmodell einer Klassendefinition, für die ein Zeiger auf ein Member deklariert wird, entweder mehrfach oder virtuell ist.|
|*multiple_inheritance*|Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit Mehrfachvererbung. Löst einen Fehler aus, wenn das Vererbungsmodell einer Klassendefinition, für die ein Zeiger auf ein Member deklariert wird, virtuell ist.|
|*virtual_inheritance*|Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit virtueller Vererbung. Löst nie einen Fehler aus. Dies ist das Standardargument beim `#pragma pointers_to_members(full_generality)` verwendet wird.|

> [!CAUTION]
> Empfehlen wir Ihnen, Sie fügen die **Pointers_to_members** Pragma nur in der Quellcodedatei, die Sie ändern möchten, und nur nach allen `#include` Anweisungen. Diese Vorgehensweise verringert das Risiko, dass sich das Pragma auf andere Dateien auswirkt, und dass Sie versehentlich mehrere Definitionen für dieselbe Variable oder Funktion oder denselben Klassennamen angeben.

## <a name="example"></a>Beispiel

```
//   Specify single-inheritance only
#pragma pointers_to_members( full_generality, single_inheritance )
```

## <a name="end-c-specific"></a>Ende C++-spezifisch

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
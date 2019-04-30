---
title: naked (C++)
ms.date: 11/04/2016
f1_keywords:
- naked_cpp
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
ms.openlocfilehash: 951760d7f9566c084bbe3d5a574d006020576c61
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345011"
---
# <a name="naked-c"></a>naked (C++)

**Microsoft-spezifisch**

Für die deklarierten Funktionen mit den **naked** -Attribut, der Compiler generiert Code ohne Prolog-und Epilogcode. Sie können diese Funktion verwenden, um eigene Prolog-/Epilogcodesequenzen mithilfe von Inlineassemblercode zu schreiben. Naked-Funktionen sind vor allem beim Schreiben von virtuellen Gerätetreibern hilfreich.  Beachten Sie, dass die **naked** Attribut ist nur für X86- und ARM gültig und ist auf X64 nicht verfügbar.

## <a name="syntax"></a>Syntax

```
__declspec(naked) declarator
```

## <a name="remarks"></a>Hinweise

Da die **naked** Attribut nur für die Definition einer Funktion relevant ist und kein Typmodifizierer, naked-Funktionen die erweiterte Attributsyntax verwenden müssen und die [__declspec](../cpp/declspec.md) Schlüsselwort.

Generiert der Compiler kann keine Inlinefunktion für eine Funktion mit dem naked-Attribut, selbst wenn die Funktion auch markiert ist, mit der ["__forceinline"](inline-functions-cpp.md) Schlüsselwort.

Der Compiler gibt einen Fehler aus, wenn die **naked** -Attribut auf etwas anderes als die Definition einer nicht-Member-Methode angewendet wird.

## <a name="examples"></a>Beispiele

Dieser Code definiert eine Funktion mit dem **naked** Attribut:

```
__declspec( naked ) int func( formal_parameters ) {}
```

Oder auch:

```
#define Naked __declspec( naked )
Naked int func( formal_parameters ) {}
```

Die **naked** Attribut wirkt sich auf nur die Art der codegenerierung des Compilers, für die Prolog- und epilogsequenzen der Funktion-Sequenzen. Es hat keine Auswirkungen auf den Code, der zum Aufrufen solcher Funktionen generiert wird. Daher die **naked** -Attribut nicht als Teil des Typs der Funktion und Funktionszeiger können keine der **naked** Attribut. Darüber hinaus die **naked** Attribut kann nicht auf eine Datendefinition angewendet werden. Beispielsweise wird mit diesem Codebeispiel ein Fehler generiert:

```
__declspec( naked ) int i;
// Error--naked attribute not permitted on data declarations.
```

Die **naked** -Attribut ist nur für die Definition der Funktion relevant und kann nicht im Funktionsprototyp angegeben werden. Beispielsweise wird mit dieser Deklaration ein Compilerfehler generiert:

```
__declspec( naked ) int func();  // Error--naked attribute not permitted on function declarations
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Naked-Funktionsaufrufe](../cpp/naked-function-calls.md)
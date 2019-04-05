---
title: Compilerwarnung (Stufe 4) C4985
ms.date: 11/04/2016
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
ms.openlocfilehash: 73abb166910cc421f042d22d67efc122e416bceb
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024438"
---
# <a name="compiler-warning-level-4-c4985"></a>Compilerwarnung (Stufe 4) C4985

"Symbolname": Attribute sind in vorheriger Deklaration nicht vorhanden.

Die Microsoft SAL-Anmerkungen (Source Code Annotation Language, Quellcodeanmerkungssprache) zur aktuellen Methodendeklaration oder -definition unterscheiden sich von den Anmerkungen zu einer früheren Deklaration. In der Definition und den Deklarationen einer Methode müssen dieselben SAL-Anmerkungen verwendet werden.

Die SAL stellt einen Satz Anmerkungen bereit, mit denen Sie beschreiben können, wie eine Funktion ihre Parameter verwendet, welche Annahmen sie über diese Parameter trifft, und wie ihr garantierte Ergebnis aussieht, wenn sie abgeschlossen wird. Die Anmerkungen sind in der Headerdatei „sal.h“ definiert.

Beachten Sie, dass die SAL-Makros nicht erweitert werden, es sei denn, für das Projekt ist das Kennzeichen [/ analyze](../../build/reference/analyze-code-analysis.md) angegeben. Wenn Sie **/analyze**angeben, kann der Compiler C4985 auslösen, selbst wenn ohne **/analyze**keine Warnungen oder Fehler angezeigt würden.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Verwenden Sie für die Definition einer Methode und deren Deklarationen dieselben SAL-Anmerkungen.

## <a name="see-also"></a>Siehe auch

[SAL-Anmerkungen](../../c-runtime-library/sal-annotations.md)
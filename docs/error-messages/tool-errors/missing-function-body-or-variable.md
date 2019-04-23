---
title: Fehlender Funktionsrumpf oder fehlende Variable
ms.date: 11/04/2016
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
ms.openlocfilehash: c287d804df3222475d7cf32c6eb025f642dfb913
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031854"
---
# <a name="missing-function-body-or-variable"></a>Fehlender Funktionsrumpf oder fehlende Variable

Klicken Sie mit nur einem Funktionsprototyp der Compiler kann ohne Fehler weiterhin, aber der Linker kann keinen Aufruf an eine Adresse nicht aufgelöst werden, da keine Funktionscode variablenspeicher reserviert oder. Dieser Fehler wird nicht angezeigt werden, bis Sie einen Aufruf der Funktion erstellen, die der Linker auflösen müssen.

## <a name="example"></a>Beispiel

Der Funktionsaufruf in Main wird Fehler LNK2019 führen, da der Prototyp dem Compiler ermöglicht, die Ihrer Meinung nach die Funktion vorhanden ist.  Der Linker sucht nach, dass dies nicht der Fall.

```
// LNK2019_MFBV.cpp
// LNK2019 expected
void DoSomething(void);
int main() {
   DoSomething();
}
```

## <a name="example"></a>Beispiel

C++ stellen Sie sicher, dass Sie die Implementierung einer bestimmten Funktion für eine Klasse und nicht nur einen Prototyp in der Klassendefinition einschließen. Wenn Sie die Klasse außerhalb der Header-Datei definieren, müssen Sie den Namen der Klasse, bevor die Funktion enthalten (`Classname::memberfunction`).

```
// LNK2019_MFBV_2.cpp
// LNK2019 expected
struct A {
   static void Test();
};

// Should be void A::Test() {}
void Test() {}

int main() {
   A AObject;
   AObject.Test();
}
```

## <a name="see-also"></a>Siehe auch

[Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: 1d78e8f5116eabf9073205b938156197bf1001a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611860"
---
# <a name="noreturn"></a>noreturn

## <a name="microsoft-specific"></a>Microsoft-spezifisch

Dies **__declspec** Attribut weist den Compiler, dass keine Funktion zurückgegeben wird. Infolgedessen wird der Compiler weiß, dass der Code nach einem Aufruf einer **__declspec(noreturn)** Funktion ist nicht erreichbar.

Wenn der Compiler eine Funktion mit einem Kontrollpfad findet, die keinen Wert zurückgibt, wird eine Warnung (C4715) oder Fehlermeldung (C2202) generiert. Wenn der Kontrollpfad wegen einer Funktion nicht, die nie zurückgegeben erreichbar ist, können Sie **__declspec(noreturn)** um diese Warnung oder Fehler zu vermeiden.

> [!NOTE]
>  Hinzufügen von **__declspec(noreturn)** an eine Funktion, die erwartet wird, zurückgeben können zu nicht definiertem Verhalten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die **else** -Klausel keine return-Anweisung.  Deklarieren von `fatal` als **__declspec(noreturn)** vermeidet einen Fehler oder eine Warnmeldung angezeigt.

```cpp
// noreturn2.cpp
__declspec(noreturn) extern void fatal () {}

int main() {
   if(1)
     return 1;
   else if(0)
     return 0;
   else
     fatal();
}
```

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)
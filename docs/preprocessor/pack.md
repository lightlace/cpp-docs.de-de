---
title: pack
ms.date: 12/17/2018
f1_keywords:
- pack_CPP
- vc-pragma.pack
helpviewer_keywords:
- pragmas, pack
- pack pragma
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
ms.openlocfilehash: bf1ae81184d53dd271f63c26e8f9a52a6410b232
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038446"
---
# <a name="pack"></a>pack
Gibt die Komprimierungsausrichtung für Struktur, Union und Klassenmember an.

## <a name="syntax"></a>Syntax

```
#pragma pack( [ show ] | [ push | pop ] [, identifier ] , n  )
```

### <a name="parameters"></a>Parameter

**show**<br/>
(Optional) Zeigt den aktuellen Bytewert für die verpackungsausrichtung an. Der Wert wird von einer Warnmeldung angezeigt.

**push**<br/>
(Optional) Schiebt den aktuellen verpackungsausrichtungswert auf dem internen compilerstapel ab und legt den aktuellen verpackungsausrichtungswert auf *n*. Wenn *n* nicht angegeben ist, den aktuellen verpackungsausrichtungswert wird mithilfe von Push übertragen.

**pop**<br/>
(Optional) Entfernt den Datensatz von der obersten Position des internen Compilerstapels. Wenn *n* nicht mit angegeben **pop**, dann ist der Paketwert, der mit dem resultierenden Datensatz oben auf dem Stapel verknüpft ist die neue verpackungsausrichtungswert. Wenn *n* angegeben ist, z. B. `#pragma pack(pop, 16)`, *n* der neue verpackungsausrichtungswert. Wenn Sie per POP auslesen *Bezeichner*, z. B. `#pragma pack(pop, r1)`, und klicken Sie dann alle Datensätze auf dem Stapel per POP bis zu dem Datensatz ausgelesen werden, die *Bezeichner* gefunden wird. Dieser Datensatz wird per pop ausgelesen, und der Paketwert, der mit dem resultierenden Datensatz oben auf dem Stapel verknüpft ist, ist der neue Verpackungsausrichtungswert. Wenn Sie per POP auslesen ein *Bezeichner* , die in keinem Datensatz auf dem Stapel nicht gefunden wird und dann die **pop** wird ignoriert.

*identifier*<br/>
(Optional) Bei Verwendung mit *Push*, den Datensatz im internen compilerstapel ein Name zugewiesen. Bei Verwendung mit **pop**, Datensätze vom internen Stapel bis *Bezeichner* wird entfernt; Wenn *Bezeichner* wurde nicht gefunden im internen Stapel, nichts per pop ausgelesen wird.

*n*<br/>
(Optional) Gibt den Wert in Bytes, die für die Komprimierung verwendet werden. Wenn die Compileroption [/Zp](../build/reference/zp-struct-member-alignment.md) ist nicht festgelegt, für das Modul, der Standardwert für *n* ist 8. Gültige Werte sind 1, 2, 4, 8 und 16. Die Ausrichtung eines Elements werden an einer Grenze, die entweder ein Vielfaches von *n* oder ein Vielfaches der Größe des Members, welcher Wert kleiner ist.

`#pragma pack(pop, identifier, n)` ist nicht definiert.

## <a name="remarks"></a>Hinweise

Das Packen einer Klasse entspricht dem Platzieren ihrer Member direkt nacheinander im Arbeitsspeicher, was bedeutet kann, dass einige oder alle Member an einer Grenze, die kleiner als die standardmäßige Ausrichtung der Zielarchitektur ist, ausgerichtet werden können. **Pack** Steuerung auf der datendeklarationsebene. Dies unterscheidet sich von der Compileroption [/Zp](../build/reference/zp-struct-member-alignment.md), die nur modulebenensteuerung bereitstellt. **Pack** wirksam bei der ersten **Struktur**, **Union**, oder **Klasse** Deklaration, nachdem das Pragma angezeigt wird. **Pack** hat keine Auswirkungen auf Definitionen. Aufrufen von **Pack** ohne Argumente legt *n* den Wert in der Compileroption `/Zp`. Wenn die Compileroption nicht festgelegt ist, ist der Standardwert 8.

Wenn Sie die Ausrichtung einer Struktur ändern, belegt sie vielleicht nicht so viel Platz im Arbeitsspeicher, aber Sie werden eine Abnahme der Leistung feststellen oder sogar eine von der Hardware generierte Ausnahme für einen nicht ausgerichteten Zugriff erhalten.  Sie können dieses Ausnahmeverhalten mithilfe ändern [SetErrorMode](https://msdn.microsoft.com/library/windows/desktop/ms680621).

Weitere Informationen zur Änderung der Ausrichtung finden Sie unter folgenden Themen:

- [__alignof](../cpp/alignof-operator.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [Beispiele für die Strukturausrichtung](../build/x64-software-conventions.md#examples-of-structure-alignment) (X64 bestimmte)

   > [!WARNING]
   > Beachten Sie, dass Sie in Visual Studio 2015 und höher die standardmäßigen „alignas“- und „alignof“-Operatoren verwenden können, die im Gegensatz zu `__alignof` und `declspec( align )` über Compiler portiert werden. Der C++-Standard behandelt nicht packen, sodass Sie weiterhin verwenden müssen **Pack** (oder die entsprechende Erweiterung auf anderen Compilern) um Ausrichtungen, die kleiner als die Wortgröße der Zielarchitektur anzugeben.

## <a name="examples"></a>Beispiele

Das folgende Beispiel zeigt, wie Sie mit der **Pack** Pragma, um die Ausrichtung einer Struktur zu ändern.

```cpp
// pragma_directives_pack.cpp
#include <stddef.h>
#include <stdio.h>

struct S {
   int i;   // size 4
   short j;   // size 2
   double k;   // size 8
};

#pragma pack(2)
struct T {
   int i;
   short j;
   double k;
};

int main() {
   printf("%zu ", offsetof(S, i));
   printf("%zu ", offsetof(S, j));
   printf("%zu\n", offsetof(S, k));

   printf("%zu ", offsetof(T, i));
   printf("%zu ", offsetof(T, j));
   printf("%zu\n", offsetof(T, k));
}
```

```Output
0 4 8
0 4 6
```

Das folgende Beispiel zeigt, wie Sie mit der *Push*, *pop*, und *anzeigen* Syntax.

```cpp
// pragma_directives_pack_2.cpp
// compile with: /W1 /c
#pragma pack()   // n defaults to 8; equivalent to /Zp8
#pragma pack(show)   // C4810
#pragma pack(4)   // n = 4
#pragma pack(show)   // C4810
#pragma pack(push, r1, 16)   // n = 16, pushed to stack
#pragma pack(show)   // C4810
#pragma pack(pop, r1, 2)   // n = 2 , stack popped
#pragma pack(show)   // C4810
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
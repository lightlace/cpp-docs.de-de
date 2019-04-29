---
title: Linkertoolwarnung LNK4049
ms.date: 04/15/2019
f1_keywords:
- LNK4049
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
ms.openlocfilehash: b527d15310dba70c1bae21e601db17db2900e219
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410238"
---
# <a name="linker-tools-warning-lnk4049"></a>Linkertoolwarnung LNK4049

> Symbol "*Symbol*"definiert "*filename.obj*" wird importiert

[von "__declspec(dllimport)" "](../../cpp/dllexport-dllimport.md) wurde angegeben, für die *Symbol* , obwohl das Symbol, in der Objektdatei definiert ist *filename.obj* im gleichen Abbild. Entfernen Sie die `__declspec(dllimport)` Modifizierer, um diese Warnung zu beheben.

## <a name="remarks"></a>Hinweise

Diese Warnung wird vom Linker generiert, wenn Sie ein Symbol in ein Objekt definieren und sie mithilfe verweisen der `__declspec(dllimport)` deklarationsmodifizierer in einem anderen.

Warnung LNK4049 ist eine allgemeine Version der [Linker Tools Warning LNK4217](linker-tools-warning-lnk4217.md). Der Linker generiert LNK4049 Warnung, wenn sie nicht bestimmen kann, welche Datei Funktion oder das Objekt, das importierte Symbol verwiesen.

Die vorkommenden Fälle, in denen LNK4049 statt LNK4217 generiert, werden:

- Bei Verwendung der [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) Option.

- Bei Verwendung der ["/ LTCG"](../../build/reference/ltcg-link-time-code-generation.md) Option.

Um LNK4049 zu beheben, verwenden Sie eines der folgenden Verfahren aus:

- Entfernen Sie die `__declspec(dllimport)` Modifizierer aus der Vorwärtsdeklaration des Symbols, das LNK4049 ausgelöst hat. Sie können nach Symbolen in einem binären Bild suchen, mit der **DUMPBIN** Hilfsprogramm. Die **DUMPBIN/Symbols** Schalter zeigt die COFF-Symboltabelle des Bilds an. Weitere Informationen zu den **DUMPBIN** Hilfsprogramm finden Sie unter [DUMPBIN-Referenz](../../build/reference/dumpbin-reference.md).

- Inkrementelles Verknüpfen und die Optimierung des ganzen Programms, vorübergehend zu deaktivieren. Wenn erneut kompiliert, generiert die Anwendung den Namen der Funktion enthält, die die importierten Symbole verweist auf die Warnung LNK4217 an. Entfernen Sie die `__declspec(dllimport)` deklarationsmodifizierer aus der importierten Symbole und das inkrementelle Verknüpfung erneut zu aktivieren oder die Optimierung des ganzen Programms nach Bedarf.

Der letzte generierte Code ordnungsgemäß verhält sich, zwar ist der Code zum Aufrufen der importierten Funktion weniger effizient als direkter Aufruf der Funktion. Diese Warnung nicht angezeigt, wenn Sie bei der Kompilierung der ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) Option.

Weitere Informationen zum Importieren und Exportieren von Datendeklarationen, finden Sie unter [Dllexport, Dllimport](../../cpp/dllexport-dllimport.md).

## <a name="example"></a>Beispiel

Verknüpfen die folgenden zwei Module wird LNK4049 generiert. Das erste Modul generiert eine Objektdatei, die eine exportierte Funktion enthält.

```cpp
// LNK4049a.cpp
// compile with: /c

__declspec(dllexport) int func()
{
   return 3;
}
```

Das zweite Modul generiert eine Objektdatei, die eine Vorwärtsdeklaration für die im ersten Modul zusammen mit einem Aufruf dieser Funktion in exportierten Funktion enthält die `main` Funktion. Verknüpfen dieses Modul mit dem ersten Modul wird LNK4049 generiert. Entfernen Sie die `__declspec(dllimport)` Modifizierer aus der Deklaration auf die Warnung aufzulösen.

```cpp
// LNK4049b.cpp
// compile with: /link /WX /LTCG LNK4049a.obj
// LNK4049 expected

__declspec(dllimport) int func();
// try the following line instead
// int func();

int main()
{
   return func();
}
```

## <a name="see-also"></a>Siehe auch

[Linkertoolwarnung Lnk4217](linker-tools-warning-lnk4217.md) \
[Linkertoolwarnung LNK4286 Warnung](linker-tools-warning-lnk4286.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)
---
title: Linkertoolwarnung LNK4049
ms.date: 11/04/2016
f1_keywords:
- LNK4049
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
ms.openlocfilehash: f9e5f1d9d5628a0da49300f541a4d5d4ce321c5f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024490"
---
# <a name="linker-tools-warning-lnk4049"></a>Linkertoolwarnung LNK4049

Lokal definiertes Symbol 'Symbol' nicht importiert

Das Symbol wurde sowohl aus exportiert und in das Programm importiert.

Diese Warnung wird vom Linker generiert, wenn Sie ein Symbol mit deklarieren die `__declspec(dllexport)` Storage-Class-Attribut in der Datei für ein Objekt, und verweisen sie mithilfe der `__declspec(dllimport)` Attribut in einer anderen.

Warnung LNK4049 ist eine allgemeine Version der [Linker Tools Warning LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md). Der Linker generiert Warnung LNK4049 aus, wenn nicht bestimmt werden kann von der Funktion der importierte Symbol verwiesen wurde.

Die vorkommenden Fälle, in denen LNK4049 statt LNK4217 generiert, werden:

- Inkrementelles Verknüpfen mit der [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) Option.

- Optimierung des ganzen Programms anhand der ["/ LTCG"](../../build/reference/ltcg-link-time-code-generation.md) Option.

Um LNK4049 zu beheben, verwenden Sie eine der folgenden aus:

- Entfernen Sie die `__declspec(dllimport)` benennen Sie die Deklaration von der Vorwärtsdeklaration des Symbols, das LNK4049 ausgelöst hat. Sie können nach Symbolen in einem binären Bild suchen, mit der **DUMPBIN** Hilfsprogramm. Die **DUMPBIN/SYMBOLS** Schalter zeigt die COFF-Symboltabelle des Bilds an. Weitere Informationen zu den **DUMPBIN** Hilfsprogramm finden Sie unter [DUMPBIN-Referenz](../../build/reference/dumpbin-reference.md).

- Inkrementelles Verknüpfen und die Optimierung des ganzen Programms, vorübergehend zu deaktivieren. Erneutes Kompilieren der Anwendung generiert Warnung LNK4217, darunter den Namen der Funktion wird von dem das importierte Symbol verwiesen wurde. Entfernen Sie die `__declspec(dllimport)` Deklaration aus dem importierten Symbole und aktiviert inkrementelles Verknüpfen oder Optimierung des ganzen Programms nach Bedarf.

Auch wenn der letzte generierte Code ordnungsgemäß verhält, ist der Code zum Aufrufen der importierten Funktion weniger effizient als direkter Aufruf der Funktion. Diese Warnung wird nicht angezeigt, wenn Sie Kompilieren mit der Option ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md).

Weitere Informationen zum Importieren und Exportieren von Datendeklarationen, finden Sie unter [Dllexport, Dllimport](../../cpp/dllexport-dllimport.md).

## <a name="example"></a>Beispiel

Verknüpfen die folgenden zwei Module wird LNK4049 generiert. Das erste Modul generiert eine Objektdatei, die eine exportierte Funktion enthält.

```
// LNK4049a.cpp
// compile with: /c

__declspec(dllexport) int func()
{
   return 3;
}
```

## <a name="example"></a>Beispiel

Das zweite Modul generiert eine Objektdatei, die eine Vorwärtsdeklaration für die im ersten Modul zusammen mit einem Aufruf dieser Funktion in exportierten Funktion enthält die `main` Funktion. Verknüpfen dieses Modul mit dem ersten Modul wird LNK4049 generiert. Entfernen der `__declspec(dllimport)` Deklaration die Warnung aufgelöst wird.

```
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

[Linkertoolwarnung LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)
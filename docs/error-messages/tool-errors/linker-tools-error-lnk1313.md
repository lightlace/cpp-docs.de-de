---
title: Linkertoolfehler LNK1313
ms.date: 11/04/2016
f1_keywords:
- LNK1313
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
ms.openlocfilehash: 380df2bff305acc47e423d69ea702d77c4eafdfd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604229"
---
# <a name="linker-tools-error-lnk1313"></a>Linkertoolfehler LNK1313

> IJW/Native-Modul gefunden; kann mit reinen Modulen nicht verknüpft werden

## <a name="remarks"></a>Hinweise

Die aktuelle Version von Visual C++ unterstützt nicht das Verknüpfen von systemeigenen oder gemischten verwalteten/systemeigenen .obj-Dateien mit .objdateien mit kompiliert **/CLR: pure**.

Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

## <a name="example"></a>Beispiel

```cpp
// LNK1313.cpp
// compile with: /c /clr:pure
// a pure module
int main() {}
```

## <a name="example"></a>Beispiel

```cpp
// LNK1313_b.cpp
// compile with: /c /clr
// an IJW module
void test(){}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird LNK1313 generiert.

```cpp
// LNK1313_c.cpp
// compile with: /link LNK1313.obj LNK1313_b.obj
// LNK1313 warning expected
```
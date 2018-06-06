---
title: Linkertoolfehler Lnk1313 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1313
dev_langs:
- C++
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6a896c8ba012c69755c5292475b2d155ad92066
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705087"
---
# <a name="linker-tools-error-lnk1313"></a>Linkertoolfehler LNK1313

> IJW/Native-Modul gefunden; kann mit reinen Modulen nicht verknüpft werden

## <a name="remarks"></a>Hinweise

Die aktuelle Version von Visual C++ unterstützt nicht das Verknüpfen von systemeigenen oder gemischten verwalteten/systemeigenen .obj-Dateien mit OBJ-Dateien kompiliert mit **/CLR: pure**.

Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt wird.

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
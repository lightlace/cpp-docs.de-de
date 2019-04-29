---
title: Compilerwarnung (Stufe 3) C4278
ms.date: 08/27/2018
f1_keywords:
- C4278
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
ms.openlocfilehash: 8c5c15105581602566116d3ed82b89a6337435c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402163"
---
# <a name="compiler-warning-level-3-c4278"></a>Compilerwarnung (Stufe 3) C4278

> "*Bezeichner*": Bezeichner in der Typbibliothek "*Tlb*' ist bereits ein Makro; benutzen Sie den"Rename"-Qualifizierer

Bei Verwendung [#import](../../preprocessor/hash-import-directive-cpp.md), ein Bezeichner in der Typbibliothek, die Sie importieren versucht, einen Bezeichner zu deklarieren *Bezeichner*. Dies ist jedoch bereits ein gültiges Symbol.

Verwenden der `#import` **umbenennen** Attribut, auf das Symbol in der Typbibliothek einen Alias zuzuweisen.
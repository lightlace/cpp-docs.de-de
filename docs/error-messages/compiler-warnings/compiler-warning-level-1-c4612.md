---
title: Compilerwarnung (Stufe 1) C4612
ms.date: 08/27/2018
f1_keywords:
- C4612
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
ms.openlocfilehash: ed5458fc52c1c9c9f12187095e4658204613d1a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406365"
---
# <a name="compiler-warning-level-1-c4612"></a>Compilerwarnung (Stufe 1) C4612

> Fehler im Namen der Includedatei

## <a name="remarks"></a>Hinweise

Diese Warnung tritt bei **#pragma include_alias** auf, wenn ein Dateiname falsch ist oder fehlt.

Die Argumente für die **#pragma Include_alias** -Anweisung kann das Angebotsformular verwenden ("*Filename*") oder spitze Klammern (\<*Filename*>), aber beide müssen Verwenden Sie die gleiche Form.

## <a name="example"></a>Beispiel

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```
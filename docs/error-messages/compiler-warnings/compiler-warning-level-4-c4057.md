---
title: Compilerwarnung (Stufe 4) C4057
ms.date: 11/04/2016
f1_keywords:
- C4057
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
ms.openlocfilehash: 234223ee7b6a031dd9e2c0fc88ccbbdba05beb3c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401435"
---
# <a name="compiler-warning-level-4-c4057"></a>Compilerwarnung (Stufe 4) C4057

'Operator': 'Bezeichner1' Dereferenzierung in leicht unterschiedliche Basistypen von 'Bezeichner2'

Zwei Zeigerausdrücke verweisen auf unterschiedliche Basistypen. Die Ausdrücke werden ohne Konvertierung verwendet.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Typen mit und ohne Vorzeichen werden gemischt verwendet.

1. **short** - und **long** -Typen werden gemischt verwendet.
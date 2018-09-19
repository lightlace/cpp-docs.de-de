---
title: Compilerwarnung (Stufe 4) C4214 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4214
dev_langs:
- C++
helpviewer_keywords:
- C4214
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 879c959bfe851b56dbc60b4eeb714db8d7f9dfaf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027426"
---
# <a name="compiler-warning-level-4-c4214"></a>Compilerwarnung (Stufe 4) C4214

nicht dem Standard entsprechende Erweiterung: Bitfeld Int

Mit den Standard-Microsoft-Erweiterungen (/ Ze) können die Strukturmember Bitfeld der ein beliebiger ganzzahliger Typ sein.

## <a name="example"></a>Beispiel

```
// C4214.c
// compile with: /W4
struct bitfields
{
   unsigned short j:4;  // C4214
};

int main()
{
}
```

Solche Bitfelder sind ungültig, ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).
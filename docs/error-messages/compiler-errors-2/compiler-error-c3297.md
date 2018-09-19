---
title: Compilerfehler C3297 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3297
dev_langs:
- C++
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7aa23cebc7ad7019c375c351f723b7ad1573ab86
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069832"
---
# <a name="compiler-error-c3297"></a>Compilerfehler C3297

'Einschränkung_2': 'Einschränkung_1' kann nicht als Einschränkung verwendet werden, da 'Einschränkung_1' die Werteinschränkung aufweist.

Wertklassen sind versiegelt. Wenn eine Einschränkung eine Wertklasse ist, kann von ihr keine andere Einschränkung abgeleitet werden.

Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3297 generiert:

```
// C3297.cpp
// compile with: /clr /c
generic<class T, class U>
where T : value class
where U : T   // C3297
public ref struct R {};
```
---
title: Compilerfehler C3161 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11396ccad33489b41d18759ba4d2f00b445e94a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136074"
---
# <a name="compiler-error-c3161"></a>Compilerfehler C3161

'Schnittstelle': Schachteln von Klasse, Struktur, Union oder Schnittstelle in einer Schnittstelle ist nicht zulässig. Schachteln einer Schnittstelle in einer Klasse, Struktur oder Union ist nicht zulässig

Ein [__interface](../../cpp/interface.md) darf nur im globalen Gültigkeitsbereich oder in einem Namespace. Eine Klasse, Struktur oder Union kann nicht in einer Schnittstelle angezeigt.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3161 generiert.

```
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```
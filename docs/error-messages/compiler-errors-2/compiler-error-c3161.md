---
title: Compilerfehler C3161
ms.date: 11/04/2016
f1_keywords:
- C3161
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
ms.openlocfilehash: 7315dad7959cdd3b950ed814b13be3867399d332
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761815"
---
# <a name="compiler-error-c3161"></a>Compilerfehler C3161

' Schnittstelle ': die Schachtelungs Klasse, Struktur, Union oder Schnittstelle in einer Schnittstelle ist unzulässig. Schachtelungs Schnittstelle in einer Klasse, Struktur oder Union ist unzulässig

Eine [__interface](../../cpp/interface.md) kann nur im globalen Gültigkeitsbereich oder innerhalb eines Namespace angezeigt werden. Eine Klasse, Struktur oder Union kann nicht in einer Schnittstelle angezeigt werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3161 generiert.

```cpp
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```

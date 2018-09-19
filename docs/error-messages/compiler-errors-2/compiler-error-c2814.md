---
title: Compilerfehler C2814 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2814
dev_langs:
- C++
helpviewer_keywords:
- C2814
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef85e143b13ea5184235676179e33b387f751aa8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046575"
---
# <a name="compiler-error-c2814"></a>Compilerfehler C2814

„Member“: Ein systemeigener Typ kann innerhalb eines verwalteten oder WinRT-Typs „Typ“ nicht geschachtelt werden.

## <a name="example"></a>Beispiel

Ein systemeigener Typ kann nicht in einem CLR- oder WinRT-Typ geschachtelt werden. Im folgenden Beispiel wird C2814 generiert und gezeigt, wie Sie diesen Fehler beheben.

```
// C2814.cpp
// compile with: /clr /c
ref class A {
   class B {};   // C2814
   ref class C {};   // OK
};
```

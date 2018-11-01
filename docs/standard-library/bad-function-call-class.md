---
title: bad_function_call-Klasse
ms.date: 11/04/2016
f1_keywords:
- functional/std::bad_function_call
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
ms.openlocfilehash: 6d0a3f5f5b6ac48d23b937b04b4521799ba31502
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523824"
---
# <a name="badfunctioncall-class"></a>bad_function_call-Klasse

Meldet einen ungültigen Funktionsaufruf.

## <a name="syntax"></a>Syntax

```cpp
class bad_function_call : public std::exception {};
```

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt eine Ausnahme, die ausgelöst wurde, um anzugeben, dass ein Aufruf von `operator()` in einer [function-Klasse](../standard-library/function-class.md) durchgeführt wurde.

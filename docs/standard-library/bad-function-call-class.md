---
title: bad_function_call-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::bad_function_call
dev_langs:
- C++
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e00dd485478a5a6fb7ff029afdad7bf7212fd56
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="badfunctioncall-class"></a>bad_function_call-Klasse

Meldet einen ungültigen Funktionsaufruf.

## <a name="syntax"></a>Syntax

```cpp
class bad_function_call
 : public std::exception {
 };
```

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt eine Ausnahme, die ausgelöst wurde, um anzugeben, dass ein Aufruf von `operator()` in einer [function-Klasse](../standard-library/function-class.md) durchgeführt wurde.

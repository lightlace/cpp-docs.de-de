---
title: Jitintrinsic | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 888ec19eaedf881fed97a14a7f3f8b5ee673ce7a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056286"
---
# <a name="jitintrinsic"></a>jitintrinsic

Markiert die Funktion als signifikant bei der 64-Bit-Common Language Runtime. Dies wird in bestimmten Funktionen in von Microsoft bereitgestellten Bibliotheken verwendet.

## <a name="syntax"></a>Syntax

```
__declspec(jitintrinsic)
```

## <a name="remarks"></a>Hinweise

**Jitintrinsic** Fügt ein MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) zu einer Funktionssignatur.

Benutzer sind nicht empfehlenswert, von der Verwendung dieses **__declspec** Modifizierer verwenden, da unerwartete Ergebnisse möglich.

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)
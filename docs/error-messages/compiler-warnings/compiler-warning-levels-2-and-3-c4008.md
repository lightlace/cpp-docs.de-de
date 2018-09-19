---
title: Compilerwarnung (Ebenen 2 und 3) C4008 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4008
dev_langs:
- C++
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd052b8dd6a0b70dd90ca076d0085675b33dc621
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091178"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Compilerwarnung (Stufen 2 und 3) C4008

'Bezeichner': 'Attribut'-Attribut wird ignoriert

Der Compiler ignoriert die Attribute `__fastcall`, **static**oder **inline** für eine Funktion (Warnstufe 3) oder für Daten (Warnstufe 2).

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. `__fastcall` -Attribute werden mit Daten.

1. Attribute**static** oder **inline** mit **main** -Funktion.
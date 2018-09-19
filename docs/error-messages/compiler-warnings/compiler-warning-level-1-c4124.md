---
title: Compilerwarnung (Stufe 1) C4124 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a69190487c22987ead2d00ec102785ed42ea93c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090925"
---
# <a name="compiler-warning-level-1-c4124"></a>Compilerwarnung (Stufe 1) C4124

__fastcall mit stapelüberprüfung ist ineffizient

Die `__fastcall` Schlüsselwort wurde verwendet, mit stapelüberprüfung aktiviert.

Die `__fastcall` Konvention generiert schnelleren Code, aber die stapelüberprüfung verursacht langsamere Code. Bei Verwendung `__fastcall`, deaktivieren Sie die stapelüberprüfung mit der **Check_stack** Pragma oder/GS.

Diese Warnung wird nur für die erste Funktion deklariert, die unter diesen Bedingungen ausgegeben.
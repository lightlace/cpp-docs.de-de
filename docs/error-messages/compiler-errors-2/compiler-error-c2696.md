---
title: Compilerfehler C2696 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2696
dev_langs:
- C++
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6e76b0c11d329c734b0609c540aca4315c7ed9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108741"
---
# <a name="compiler-error-c2696"></a>Compilerfehler C2696

Ein temporäres Objekt von einem verwalteten Typ 'Typ' kann nicht erstellt werden.

Verweise auf `const` in einem nicht verwalteten Programm dazu führen, dass den Compiler rufen Sie den Konstruktor und ein temporäres Objekt erstellt, auf dem Stapel. Eine verwaltete Klasse kann jedoch nie auf dem Stapel erstellt werden.

C2696 ist nur über die veraltete Compileroption erreichbar **oldSyntax**.

---
title: Compilerfehler C2307 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2307
dev_langs:
- C++
helpviewer_keywords:
- C2307
ms.assetid: ce6c8033-a673-4679-9883-bedec36ae385
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26373ac75c4e6724ce01e24dbd46066f2ef534b8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049393"
---
# <a name="compiler-error-c2307"></a>Compilerfehler C2307

"Pragma"-Pragma muss außerhalb der Funktion, wenn inkrementelle Kompilierung aktiviert ist

Sie müssen Platzieren der `data_seg` Pragma zwischen Funktionen auf, wenn Sie inkrementelle Kompilierung verwenden.
---
title: Compilerfehler C3715 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3715
dev_langs:
- C++
helpviewer_keywords:
- C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63ae3486b4db21a3aa241d5ebdbbfa0cdc6806f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026555"
---
# <a name="compiler-error-c3715"></a>Compilerfehler C3715

"Zeiger": muss ein Zeiger auf "Klasse"

Angabe ein Zeigers in [__hook](../../cpp/hook.md) oder [__unhook](../../cpp/unhook.md) zeigen, die Sie nicht auf eine gültige Klasse. Um diesen Fehler zu beheben, stellen sicher, dass Ihre `__hook` und `__unhook` Aufrufe geben Zeiger zu den gültigen Klassen.
---
title: Compilerwarnung (Stufe 1) C4025 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4025
dev_langs:
- C++
helpviewer_keywords:
- C4025
ms.assetid: c4f6a651-0641-4446-973e-8290065e49ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 109f1694f63488c167e51c7c2c89675411b6d269
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045574"
---
# <a name="compiler-warning-level-1-c4025"></a>Compilerwarnung (Stufe 1) C4025

"Anzahl": Zeiger auf ein separates Segment an Funktion mit variablen Argumenten übergeben: Parameteranzahl

Die Übergabe eines basierten Zeigers an eine Funktion mit variablen Argumenten bewirkt, dass der Zeiger normalisiert wird. Dies kann unvorhersehbare Folgen haben. Übergeben Sie keine basierten Zeiger an Funktionen mit variablen Argumenten.
---
title: Compilerwarnung (Stufe 4) C4718 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4718
dev_langs:
- C++
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8736902f4c3a1cfac7313806fde65d1b253716b3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054232"
---
# <a name="compiler-warning-level-4-c4718"></a>Compilerwarnung (Stufe 4) C4718

'Funktionsaufruf': Rekursiver Aufruf besitzt keine Nebeneffekte, wird gelöscht

Eine Funktion enthält einen rekursiven Aufruf, hat aber ansonsten keine Nebeneffekte. Ein Aufruf dieser Funktion wird gelöscht. Die Richtigkeit des Programms ist nicht betroffen, aber die Verhaltensweise. Wenn der Aufruf beibehalten wird, kann dies zu einer Stapelüberlaufausnahme zur Laufzeit führen. Das Löschen des Aufrufs beseitigt diese Möglichkeit.
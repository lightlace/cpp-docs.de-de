---
title: Compilerfehler C2708 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2708
dev_langs:
- C++
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0accd68881cccad5e34530a6c157a4e8179b283
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111094"
---
# <a name="compiler-error-c2708"></a>Compilerfehler C2708

'Bezeichner': aktuelle Parameterlänge in Bytes unterscheidet sich vom vorherigen Aufruf oder Verweis

Ein [__stdcall](../../cpp/stdcall.md) Funktion muss einen Prototyp vorangestellt werden. Andernfalls interpretiert der Compiler den ersten Aufruf der Funktion als Prototyp, und dieser Fehler tritt auf, wenn der Compiler einen Aufruf findet, der nicht übereinstimmen.

Klicken Sie zum Beheben dieses Fehlers einen Funktionsprototyp hinzufügen.
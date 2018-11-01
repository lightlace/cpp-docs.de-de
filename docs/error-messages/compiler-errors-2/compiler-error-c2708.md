---
title: Compilerfehler C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: a128613cabb201142c29b833959924dbf8a6e0ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460072"
---
# <a name="compiler-error-c2708"></a>Compilerfehler C2708

'Bezeichner': aktuelle Parameterlänge in Bytes unterscheidet sich vom vorherigen Aufruf oder Verweis

Ein [__stdcall](../../cpp/stdcall.md) Funktion muss einen Prototyp vorangestellt werden. Andernfalls interpretiert der Compiler den ersten Aufruf der Funktion als Prototyp, und dieser Fehler tritt auf, wenn der Compiler einen Aufruf findet, der nicht übereinstimmen.

Klicken Sie zum Beheben dieses Fehlers einen Funktionsprototyp hinzufügen.
---
title: Compilerwarnung (Stufe 1) C4445
ms.date: 11/04/2016
f1_keywords:
- C4445
helpviewer_keywords:
- C4445
ms.assetid: 535e92a0-ba08-4dfc-89b2-af2dcdd7caeb
ms.openlocfilehash: 6c1b4f4ae4f60d0c4281e0bbcfc9ca2b58d81851
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611284"
---
# <a name="compiler-warning-level-1-c4445"></a>Compilerwarnung (Stufe 1) C4445

'Funktion' : Eine virtuelle Methode kann in einem WinRT- oder verwalteten Typ nicht privat sein.

Wenn eine virtuelle Funktion privat ist, kann über einen abgeleiteten Typ nicht auf diese zugegriffen werden. Um diesen Fehler zu beheben, ändern Sie den Zugriff auf die virtuelle Memberfunktion in „Protected“ oder „Public“.
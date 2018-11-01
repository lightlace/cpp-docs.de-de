---
title: Compilerwarnung (Stufe 1) C4276
ms.date: 11/04/2016
f1_keywords:
- C4276
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
ms.openlocfilehash: 87f13f7da12a3f7e40aaad180e2a3bc83e121771
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586913"
---
# <a name="compiler-warning-level-1-c4276"></a>Compilerwarnung (Stufe 1) C4276

'Funktion': kein Prototyp gegeben; davon ausgegangen, dass keine Parameter

Wenn Sie die Adresse einer Funktion mit übernehmen die [__stdcall](../../cpp/stdcall.md) Aufrufkonvention, Sie müssen einen Prototyp, damit der Compiler die ergänzten Namen der Funktion erstellen kann. Da *Funktion* ohne Prototyp, den Compiler hat, wenn Sie den ergänzten Namen zu erstellen, wird davon ausgegangen, die Funktion hat keine Parameter.
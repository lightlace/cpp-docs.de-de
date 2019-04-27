---
title: Compilerwarnung (Stufe 1) C4276
ms.date: 11/04/2016
f1_keywords:
- C4276
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
ms.openlocfilehash: 87f13f7da12a3f7e40aaad180e2a3bc83e121771
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207138"
---
# <a name="compiler-warning-level-1-c4276"></a>Compilerwarnung (Stufe 1) C4276

'Funktion': kein Prototyp gegeben; davon ausgegangen, dass keine Parameter

Wenn Sie die Adresse einer Funktion mit übernehmen die [__stdcall](../../cpp/stdcall.md) Aufrufkonvention, Sie müssen einen Prototyp, damit der Compiler die ergänzten Namen der Funktion erstellen kann. Da *Funktion* ohne Prototyp, den Compiler hat, wenn Sie den ergänzten Namen zu erstellen, wird davon ausgegangen, die Funktion hat keine Parameter.
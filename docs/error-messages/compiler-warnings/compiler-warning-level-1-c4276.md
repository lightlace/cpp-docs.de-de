---
title: Compilerwarnung (Stufe 1) C4276 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4276
dev_langs:
- C++
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40a6c85b460e9718a8816598afb016e9c7a493b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116021"
---
# <a name="compiler-warning-level-1-c4276"></a>Compilerwarnung (Stufe 1) C4276

'Funktion': kein Prototyp gegeben; davon ausgegangen, dass keine Parameter

Wenn Sie die Adresse einer Funktion mit übernehmen die [__stdcall](../../cpp/stdcall.md) Aufrufkonvention, Sie müssen einen Prototyp, damit der Compiler die ergänzten Namen der Funktion erstellen kann. Da *Funktion* ohne Prototyp, den Compiler hat, wenn Sie den ergänzten Namen zu erstellen, wird davon ausgegangen, die Funktion hat keine Parameter.
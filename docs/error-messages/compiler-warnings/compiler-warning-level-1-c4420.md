---
title: Compilerwarnung (Stufe 1) C4420 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4420
dev_langs:
- C++
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1ba4ef4c4fc006e1a5950d0d16dc530ccc06a1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049747"
---
# <a name="compiler-warning-level-1-c4420"></a>Compilerwarnung (Stufe 1) C4420

'Operator': Operator nicht verfügbar ist, verwenden stattdessen "Operator" laufzeitüberprüfung beeinträchtigt werden

Diese Warnung wird generiert, wenn Sie verwenden die [damit/RTCv](../../build/reference/rtc-run-time-error-checks.md) (Vektor prüfen neuer/löschen) und wenn keine Vektorform gefunden wird. In diesem Fall wird der nicht-Vektor-Formular verwendet.

In der Reihenfolge, damit/RTCv ordnungsgemäß funktioniert, sollte der Compiler immer Vektorform Aufrufen [neue](../../cpp/new-operator-cpp.md)/[löschen](../../cpp/delete-operator-cpp.md) , wenn die Vektorsyntax verwendet wurde.
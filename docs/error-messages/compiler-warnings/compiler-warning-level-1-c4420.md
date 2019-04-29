---
title: Compilerwarnung (Stufe 1) C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: a4a7e91e7845cc0fc25d5a6fad16ae7b7e327952
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408172"
---
# <a name="compiler-warning-level-1-c4420"></a>Compilerwarnung (Stufe 1) C4420

'Operator': Operator nicht verfügbar ist, verwenden stattdessen "Operator" laufzeitüberprüfung beeinträchtigt werden

Diese Warnung wird generiert, wenn Sie verwenden die [damit/RTCv](../../build/reference/rtc-run-time-error-checks.md) (Vektor prüfen neuer/löschen) und wenn keine Vektorform gefunden wird. In diesem Fall wird der nicht-Vektor-Formular verwendet.

In der Reihenfolge, damit/RTCv ordnungsgemäß funktioniert, sollte der Compiler immer Vektorform Aufrufen [neue](../../cpp/new-operator-cpp.md)/[löschen](../../cpp/delete-operator-cpp.md) , wenn die Vektorsyntax verwendet wurde.
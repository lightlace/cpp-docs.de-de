---
title: Compilerwarnung (Stufe 1) C4420 | Microsoft Docs
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
ms.openlocfilehash: 98336a30e7174b62df48e93a04ba9ee7ddcc919a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279109"
---
# <a name="compiler-warning-level-1-c4420"></a>Compilerwarnung (Stufe 1) C4420
'Operator': Operator nicht verfügbar ist, verwenden Sie stattdessen; "Operator" Überprüfen zur Laufzeit möglicherweise gefährdet  
  
 Diese Warnung wird generiert, wenn Sie mithilfe der [damit/RTCv](../../build/reference/rtc-run-time-error-checks.md) (Vektor prüfen neu/löschen) und wenn kein Vektor Formular gefunden wird. In diesem Fall wird das Formular nicht Vektor verwendet.  
  
 In Reihenfolge damit/RTCv ordnungsgemäß funktioniert, sollte der Compiler immer Vektorform Aufrufen [neue](../../cpp/new-operator-cpp.md)/[löschen](../../cpp/delete-operator-cpp.md) Wenn die Vektorsyntax verwendet wurde.
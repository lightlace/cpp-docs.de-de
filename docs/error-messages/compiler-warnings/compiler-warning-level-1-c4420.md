---
title: Compilerwarnung (Stufe 1) C4420 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4420
dev_langs:
- C++
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a57803cb584f5ee54ad5533366e6aadc85d1acf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4420"></a>Compilerwarnung (Stufe 1) C4420
'Operator': Operator nicht verfügbar ist, verwenden Sie stattdessen; "Operator" Überprüfen zur Laufzeit möglicherweise gefährdet  
  
 Diese Warnung wird generiert, wenn Sie mithilfe der [damit/RTCv](../../build/reference/rtc-run-time-error-checks.md) (Vektor prüfen neu/löschen) und wenn kein Vektor Formular gefunden wird. In diesem Fall wird das Formular nicht Vektor verwendet.  
  
 In Reihenfolge damit/RTCv ordnungsgemäß funktioniert, sollte der Compiler immer Vektorform Aufrufen [neue](../../cpp/new-operator-cpp.md)/[löschen](../../cpp/delete-operator-cpp.md) Wenn die Vektorsyntax verwendet wurde.
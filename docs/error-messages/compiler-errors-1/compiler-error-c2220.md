---
title: Compilerfehler C2220 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2220
dev_langs:
- C++
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d23476de35e0af45b46a775683ba8673b4959346
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171492"
---
# <a name="compiler-error-c2220"></a>Compilerfehler C2220
Warnung als Fehler behandelt - keine Objektdatei generiert  
  
 [/ WX](../../build/reference/compiler-option-warning-level.md) teilt dem Compiler mit, alle Warnungen als Fehler behandelt werden sollen. Da ein Fehler aufgetreten ist, wurde kein Objekt und keine ausführbare Datei generiert.  
  
 Dieser Fehler wird nur angezeigt, wenn die **/WX** Flag festgelegt ist und eine Warnung auftritt, während der Kompilierung. Um diesen Fehler zu beheben, müssen Sie jede Warnung im Projekt ausschließen.  
  
### <a name="to-fix-use-one-of-the-following-techniques"></a>So beheben Sie den Fehler mit einer der folgenden Methoden  
  
-   Korrigieren Sie die Probleme, die Warnungen im Projekt verursachen.  
  
-   Kompilieren Sie auf einer niedrigeren Warnungsebene – verwenden Sie z. B. **/W3** anstelle von **/W4**.  
  
-   Verwenden einer [Warnung](../../preprocessor/warning.md) Pragma deaktivieren oder eine bestimmte Warnung zu unterdrücken.  
  
-   Verwenden Sie keine **/WX** kompiliert.
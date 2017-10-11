---
title: Compilerfehler C2220 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2220
dev_langs:
- C++
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: dc31519b2153c66ea9bab42f536ba7c6be5b2a10
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

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

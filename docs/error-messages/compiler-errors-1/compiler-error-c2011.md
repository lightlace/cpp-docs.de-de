---
title: Compilerfehler Fehler C2011 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2011
dev_langs:
- C++
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0f32048e0de21e5af2d4d52a0c703813b1a1ff8b
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2011"></a>Compilerfehler Fehler C2011
"Bezeichner": "Typ" Typneudefinition  
  
 Der Bezeichner wurde bereits als `type` definiert. Überprüfen Sie, ob Neudefinitionen des Bezeichners vorliegen.  
  
 Beim Import tritt möglicherweise auch der Fehler C2011 auf, wenn Sie eine Headerdatei oder Typbibliothek mehrfach in dieselbe Datei importieren. Um mehrfache einbindungen von in einer Headerdatei definierten Typen zu verhindern, verwenden Sie include-Schutz oder eine `#pragma` [nach](../../preprocessor/once.md) Richtlinie in der Headerdatei.  
  
 Wenn Sie die ursprüngliche Deklaration eines neu definierten Typs suchen möchten, können Sie die [/p](../../build/reference/p-preprocess-to-a-file.md) Compilerflag die vorverarbeitete Ausgabe zu generieren, die an den Compiler übergeben. Mit Textsuchtools können Sie nach Instanzen der neu definierten Bezeichner in der Ausgabedatei suchen.  
  
 Im folgenden Beispiel wird C2011 generiert und eine Möglichkeit gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2011.cpp  
// compile with: /c  
struct S;  
union S;   // C2011  
union S2;   // OK  
```

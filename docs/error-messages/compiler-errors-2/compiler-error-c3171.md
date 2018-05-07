---
title: Compilerfehler Fehler C3171 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3171
dev_langs:
- C++
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ee6ee02511242e2af87024c741a3c97f3f3724d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3171"></a>Compilerfehler Fehler C3171
"Module": Geben Sie andere Modulattribute kann nicht in einem Projekt  
  
 [Modul](../../windows/module-cpp.md) Attribute mit unterschiedlichen Parameterlisten in zwei Dateien in einer Kompilierung gefunden wurden. Nur eine eindeutige `module` Attribut pro Kompilierung angegeben werden kann.  
  
 Identische `module` Attribute können in mehr als eine Quellcodedatei angegeben werden.  
  
 Beispielsweise, wenn die folgenden `module` Attribute gefunden wurden:  
  
```  
// C3171.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];  
int main() {}  
```  
  
 und anschließend  
  
```  
// C3171b.cpp  
// compile with: C3171.cpp  
// C3171 expected  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];  
```  
  
 der Compiler den Fehler C3171 (Beachten Sie die Werte der anderen Version).
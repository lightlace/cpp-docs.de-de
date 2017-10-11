---
title: Compilerfehler Fehler C3171 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3171
dev_langs:
- C++
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ebd64aa2c80f6e21b1e5c1829d8e165d46207718
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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

---
title: Compilerfehler Fehler C3170 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3170
dev_langs:
- C++
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bb077bcad95de0be17e630803b5d4ea9825be61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33255912"
---
# <a name="compiler-error-c3170"></a>Compilerfehler Fehler C3170
keine anderen Modulbezeichner in einem Projekt  
  
 [Modul](../../windows/module-cpp.md) Attribute mit unterschiedlichen Namen in zwei der Dateien in einer Kompilierung gefunden wurden. Nur eine eindeutige `module` Attribut pro Kompilierung angegeben werden kann.  
  
 Identische `module` Attribute können in mehr als eine Quellcodedatei angegeben werden.  
  
 Wenn beispielsweise die folgenden Modulattribute gefunden wurden:  
  
```  
// C3170.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
int main() {}  
```  
  
 und anschließend  
  
```  
// C3170b.cpp  
// compile with: C3170.cpp  
// C3170 expected  
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
```  
  
 der Compiler den Fehler C3170 (Beachten Sie die verschiedenen Namen).
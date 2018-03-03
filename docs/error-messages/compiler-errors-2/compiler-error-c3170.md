---
title: Compilerfehler Fehler C3170 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3170
dev_langs:
- C++
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 150f543ec2f75e8d21e40f822f342adef6be06c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
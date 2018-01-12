---
title: Compilerfehler Fehler C3172 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3172
dev_langs: C++
helpviewer_keywords: C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3390c0f1f566e28bc6a000b2ff570c781c93bc98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3172"></a>Compilerfehler Fehler C3172
"Modulname": Geben Sie unterschiedliche Idl_module-Attribute können nicht in einem Projekt  
  
 [Idl_module](../../windows/idl-module.md) Attribute mit demselben Namen, aber unterschiedliche `dllname` oder `version` Parameter in zwei Dateien in einer Kompilierung gefunden wurden. Nur eine eindeutige `idl_module` Attribut pro Kompilierung angegeben werden kann.  
  
 Identische `idl_module` Attribute können in mehr als eine Quellcodedatei angegeben werden.  
  
 Beispielsweise, wenn die folgenden `idl_module` Attribute gefunden wurden:  
  
```  
// C3172.cpp  
[module(name="MyMod")];  
[ idl_module(name="x", dllname="file.dll", version="1.1") ];  
int main() {}  
```  
  
 und anschließend  
  
```  
// C3172b.cpp  
// compile with: C3172.cpp  
// C3172 expected  
[ idl_module(name="x", dllname="file.dll", version="1.0") ];  
```  
  
 der Compiler den Fehler C3172 (Beachten Sie die Werte der anderen Version).
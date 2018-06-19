---
title: Compiler-Fehler C3189 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3189
dev_langs:
- C++
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acf0e49ecf9c8003d8dcfe035b14c8f5c5067dbc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251012"
---
# <a name="compiler-error-c3189"></a>Compiler-Fehler C3189 generiert
"Typeid\<abstrakten Deklarator geben >": Diese Syntax ist nicht mehr unterstützt, verwenden Sie:: Typeid stattdessen  
  
 Ein veraltetes [Typeid](../../windows/typeid-cpp-component-extensions.md) wurde verwendet, verwenden Sie das neue Format.  
  
 Im folgende Beispiel wird C3189 generiert:  
  
```  
// C3189.cpp  
// compile with: /clr  
int main() {  
   System::Type^ t  = typeid<System::Object>;   // C3189  
   System::Type^ t2  = System::Object::typeid;   // OK  
}  
```
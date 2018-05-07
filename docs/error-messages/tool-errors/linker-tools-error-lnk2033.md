---
title: Linkertoolfehler Lnk2033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2033
dev_langs:
- C++
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d03e8d2e0502d6e3664bff05c75fffb4f4ebd5da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2033"></a>Linkertoolfehler LNK2033
nicht aufgelöste Typeref-Token (Token) für "Type"  
  
 Ein Typ aufweisen keine Definition in MSIL-Metadaten.  
  
 LNK2033 kann auftreten, bei der Kompilierung mit **/CLR: safe** und bei denen es nur eine Vorwärtsdeklaration für einen Typ in einem MSIL-Modul, in dem der Typ wird im MSIL-Modul verwiesen wird.  
  
 Der Typ muss definiert werden, unter **/CLR: safe**.  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird LNK2033 generiert.  
  
```  
// LNK2033.cpp  
// compile with: /clr:safe  
// LNK2033 expected  
ref class A;  
ref class B {};  
  
int main() {  
   A ^ aa = nullptr;  
   B ^ bb = nullptr;   // OK  
};  
```
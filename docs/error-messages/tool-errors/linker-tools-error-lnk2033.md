---
title: Linkertoolfehler Lnk2033 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2033
dev_langs: C++
helpviewer_keywords: LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bac0d88d8e1ba06c358a6a1dd410b861dc582cdc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
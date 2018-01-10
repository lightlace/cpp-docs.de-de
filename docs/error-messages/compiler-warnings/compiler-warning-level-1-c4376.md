---
title: Compilerwarnung (Stufe 1) C4376 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4376
dev_langs: C++
helpviewer_keywords: C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5a0bb98149ca800fd7cfde7b85ec52e1133bd894
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4376"></a>Compilerwarnung (Stufe 1) C4376
Zugriffsspezifizierer 'old_specifier:' wird nicht mehr unterstützt: Verwenden Sie stattdessen 'new_specifier:'  
  
 Weitere Informationen zum Angeben von Typen und Member in Metadaten finden Sie unter [geben Sichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) und [membersichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) in [wie: definieren und Verarbeiten von Klassen und Strukturen (C + c++ / CLI) ](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4376 generiert.  
  
```  
// C4376.cpp  
// compile with: /clr /W1 /c  
public ref class G {  
public public:   // C4376  
   void m2();  
};  
  
public ref class H {  
public:   // OK  
   void m2();  
};  
```
---
title: Compilerwarnung (Stufe 3) C4641 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4641
dev_langs: C++
helpviewer_keywords: C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c140bb3664f72646e74ab9f47909dade76a50ca8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4641"></a>Compilerwarnung (Stufe 3) C4641
XML-Dokument-Kommentar enthält einen mehrdeutigen Querverweis  
  
 Der Compiler konnte einen Verweis eindeutig zu beheben. Um diese Warnung zu beheben, geben Sie die Parameterinformationen erforderlich, um den Verweis eindeutig zu machen.  
  
 Weitere Informationen finden Sie unter [XML Documentation](../../ide/xml-documentation-visual-cpp.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4641 generiert.  
  
```  
// C4641.cpp  
// compile with: /W3 /doc /clr /c  
  
/// <see cref="f" />   // C4641  
// try the following line instead  
// /// <see cref="f(int)" />  
public ref class GR {  
public:  
   void f( int ) {}  
   void f( char ) {}  
};  
```
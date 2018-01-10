---
title: Compilerfehler C3462 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3462
dev_langs: C++
helpviewer_keywords: C3462
ms.assetid: 56b75f35-9fad-42d9-a969-eeca5d709bec
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 35a799e8521637d7754e651fbf1e52bf47760808
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3462"></a>Compilerfehler C3462
"Typ": Nur ein importierter Typ kann weitergeleitet werden.  
  
 Das TypeForwardedTo-Attribut muss auf einen Typ in den Metadaten angewendet werden, auf die verwiesen wird.  
  
 Weitere Informationen finden Sie unter [Typweiterleitung (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Komponente erstellt:  
  
```  
// C3462.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3462 generiert:  
  
```  
// C3462b.cpp  
// compile with: /clr /c  
#using "C3462.dll"  
ref class N {};  
[assembly:TypeForwardedTo(N::typeid)];   // C3462  
[assembly:TypeForwardedTo(R::typeid)];  
```
---
title: Compilerfehler C3455 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3455
dev_langs:
- C++
helpviewer_keywords:
- C3455
ms.assetid: 218e5cfe-5391-4eeb-81c2-85c47e3a6cd2
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 98cdc956f93f7c0cdc2ae00fa1a0b6e5e26af75c
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3455"></a>Compilerfehler C3455
'attribut': Keiner der Attributkonstruktoren stimmte mit den Argumenten überein.  
  
 Ein ungültiger Wert wurde verwendet, um ein Attribut zu deklarieren.  Weitere Informationen finden Sie unter [attribute](../../windows/attribute.md) .  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3455 generiert:  
  
```  
// C3455.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute("MyAt")]   // C3455  
// try the following line instead  
// [attribute(All)]  
ref struct MyAttr {  
   MyAttr() {}  
};  
```

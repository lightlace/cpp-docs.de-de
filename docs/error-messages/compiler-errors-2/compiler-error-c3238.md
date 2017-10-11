---
title: Compilerfehler C3238 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3238
dev_langs:
- C++
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 51af2859cec319678f6b13caf7231a8f62a6177c
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3238"></a>Compilerfehler C3238
"Typ": Ein Typ mit diesem Namen wurde bereits an die Assembly "Assembly" weitergeleitet.  
  
 In einer Clientanwendung wurde ein Typ definiert, der über Syntax zur Typweiterleitung auch in einer referenzierten Assembly definiert ist. Es ist nicht zulässig, beide Typen im Gültigkeitsbereich der Anwendung zu definieren.  
  
 Finden Sie unter [Typweiterleitung (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Assembly erstellt, die einen Typ enthält, der von einer anderen Assembly weitergeleitet wurde.  
  
```  
// C3238.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine Assembly erstellt, die die Typdefinition enthält, aber nicht nur Typweiterleitungssyntax enthält.  
  
```  
// C3238_b.cpp  
// compile with: /clr /LD  
#using "C3238.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3238 generiert:  
  
```  
// C3238_c.cpp  
// compile with: /clr /c  
// C3238 expected  
// Delete the following line to resolve.  
#using "C3238_b.dll"  
public ref class R {};  
```

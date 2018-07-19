---
title: Compilerfehler C3238 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3238
dev_langs:
- C++
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33252d094847869fda07ad55563b085853681793
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249887"
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
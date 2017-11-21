---
title: Compilerfehler C3373 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3373
dev_langs: C++
helpviewer_keywords: C3373
ms.assetid: 6e7586c3-1a15-4773-ad20-f90090a400dc
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 641842664228bdbf9442c50cf5233332e05534c8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3373"></a>Compilerfehler C3373
Das Attribut "Attribut" hat keine Argumente, außer bei einer Co-Klasse  
  
 Einige Attribute können auf mehr als ein C++-Konstrukt angewendet werden, Argumente für das Attribut sind jedoch möglicherweise nur bei einigen Konstrukten zulässig.  
  
 Im folgenden Beispiel wird C3373 generiert:  
  
```  
// C3373.cpp  
#include <windows.h>  
  
[module(name="MyModule")];  
  
[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface  
{  
   // arguments to source and restricted are not allowed when  
   // these attributes are applied to an interface  
   [source(IMyIface)] HRESULT f1();  
   [restricted(IMyIface)] HRESULT f2(); // C3373  
};  
  
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f) ]  
class CMyClass : public IMyIface {  
};  
  
int main() {  
}  
```
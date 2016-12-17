---
title: "Compilerfehler C3373"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3373"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3373"
ms.assetid: 6e7586c3-1a15-4773-ad20-f90090a400dc
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3373
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Attribut "Attribut" hat keine Argumente, außer bei einer Co\-Klasse  
  
 Einige Attribute können auf mehr als ein C\+\+\-Konstrukt angewendet werden, Argumente für das Attribut sind jedoch möglicherweise nur bei einigen Konstrukten zulässig.  
  
 Im folgenden Beispiel wird C3373 generiert:  
  
```  
// C3373.cpp #include <windows.h> [module(name="MyModule")]; [ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ] __interface IMyIface { // arguments to source and restricted are not allowed when // these attributes are applied to an interface [source(IMyIface)] HRESULT f1(); [restricted(IMyIface)] HRESULT f2(); // C3373 }; [ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f) ] class CMyClass : public IMyIface { }; int main() { }  
```
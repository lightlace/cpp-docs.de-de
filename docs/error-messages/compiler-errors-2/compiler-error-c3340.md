---
title: "Compilerfehler C3340"
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
  - "C3340"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3340"
ms.assetid: 23b12298-b92a-4717-8380-f165c998cb8a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3340
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schnittstelle': Die Schnittstelle kann in der Co\-Klasse 'Klasse' nicht zugleich 'restricted' und 'default' sein.  
  
 Das [restricted](../../windows/restricted.md)\-Attribut und das [default](../../windows/default-cpp.md)\-Attribut schließen sich gegenseitig aus.  
  
 Im folgenden Beispiel wird C3340 generiert:  
  
```  
// C3340.cpp #include <windows.h> [module(name="MyModule")]; [ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ] __interface IMyIface { HRESULT f1(); }; [ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f), default(IMyIface), source(IMyIface),restricted(IMyIface) ] class CmyClass // C3340 { }; int main() { }  
```
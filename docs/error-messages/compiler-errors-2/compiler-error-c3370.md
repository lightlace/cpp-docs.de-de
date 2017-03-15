---
title: "Compilerfehler C3370 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3370"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3370"
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3370
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'IDL\_Modulname': 'idl\_module' ist noch nicht definiert.  
  
 Bevor Sie [idl\_module](../../windows/idl-module.md) zum Angeben eines Einstiegpunkts in einer DLL verwenden können, müssen Sie zunächst den Namen der DLL\-Datei mithilfe von `idl_module` angeben.  
  
 Im folgenden Beispiel wird C3370 generiert:  
  
```  
// C3370.cpp [module(name=MyLibrary)]; // uncomment the following line to resolve the error // [idl_module(name="name1", dllname=x.dll)]; [idl_module(name="name1"), entry(100)] // C3370 int f1(); int main() { }  
```
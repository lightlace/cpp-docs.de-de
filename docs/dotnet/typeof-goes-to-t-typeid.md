---
title: "typeof wird zu T::typeid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__typeof-Schlüsselwort"
  - "typeid-Schlüsselwort [C++]"
  - "typeid-Operator"
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# typeof wird zu T::typeid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der in Managed Extensions for C\+\+ verwendete Operator `typeof` wurde in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] durch das `typeid`\-Schlüsselwort ersetzt.  
  
 In Managed Extensions gibt der Operator `__typeof()` das zugeordnete `Type*`\-Objekt zurück, wenn der Name eines systemeigenen Typs übergeben wird.  Beispiel:  
  
```  
// Creates and initializes a new Array instance.  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 In der neuen Syntax wurde `__typeof` durch eine zusätzliche Form von `typeid` ersetzt, die einen `Type^` zurückgibt, wenn ein verwalteter Typ angegeben wird.  
  
```  
// Creates and initializes a new Array instance.  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
## Siehe auch  
 [Allgemeine Sprachänderung](../dotnet/general-language-changes-cpp-cli.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)
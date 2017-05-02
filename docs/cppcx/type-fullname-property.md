---
title: "Type::FullName-Eigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type::get_FullName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Type::get_FullName-Eigenschaft"
ms.assetid: b5a12d8f-4404-4659-b4af-e7d23a1e44b7
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Type::FullName-Eigenschaft
Ruft den vollqualifizierten Namen des aktuellen Typs im Formular "Namespace.Type" ab.  
  
## Syntax  
  
```cpp  
String^ FullName();  
```  
  
## Rückgabewert  
 Der Name des Typs.  
  
## Beispiel  
  
```  
  
//  namespace is TestApp MainPage::MainPage() { InitializeComponent(); Type^ t = this->GetType(); auto s = t->FullName; // returns “TestApp.MainPage” auto s2 = t->ToString(); //also returns “TestApp.MainPage” }  
```  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Platform::ValueType\-Klasse](../cppcx/platform-valuetype-class.md)
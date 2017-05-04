---
title: "Exception::Message-Eigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::Message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::Message-Eigenschaft"
ms.assetid: ad1199cd-0889-4803-ad0d-a3a7b3c51891
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::Message-Eigenschaft
Die Meldung, in der der Fehler beschrieben wird.  
  
## Syntax  
  
```cpp  
public:property String^ Message;  
```  
  
## Eigenschaftswert  
 In den Ausnahmen, die aus der Windows Runtime stammen, ist dieses eine vom System bereitgestellte Beschreibung des Fehlers.  
  
## Hinweise  
 In [!INCLUDE[win8](../cppcx/includes/win8-md.md)] ist diese Eigenschaft schreibgeschützt, da Ausnahmen in dieser Version von Windows Runtime über die ABI nur als HRESULTS transportiert werden. Bei [!INCLUDE[win81](../cppcx/includes/win81-md.md)] werden umfangreichere Ausnahmeinformationen über die ABI transportiert, und Sie können eine benutzerdefinierte Meldung bereitstellen, auf die andere Komponenten programmgesteuert zugreifen können. Weitere Informationen finden Sie unter [Ausnahmen \(C\+\+\/CX\)](../cppcx/exceptions-c-cx.md).  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Platform::Exception\-Klasse](../cppcx/platform-exception-class.md)
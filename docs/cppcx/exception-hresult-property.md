---
title: "Exception::HResult-Eigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::HResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::HResult-Eigenschaft"
ms.assetid: 24ef008d-6884-4b8b-9556-41bfa6e1edf1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::HResult-Eigenschaft
Das HRESULT, das der Ausnahme entspricht.  
  
## Syntax  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## Eigenschaftswert  
 Der HRESULT\-Wert.  
  
## Hinweise  
 Die meisten Ausnahmen fangen als COM\-Fehler an, die als HRESULT\-Werte zurückgegeben werden. C\+\+\/CX konvertiert diese Werte in Platform::Exception^\-Objekte, und diese Eigenschaft speichert den Wert des ursprünglichen Fehlercodes.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Platform::Exception\-Klasse](../cppcx/platform-exception-class.md)
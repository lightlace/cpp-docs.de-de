---
title: "COMException::HResult-Eigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::COMException::HResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMException::HResult-Eigenschaft"
ms.assetid: 53762ab5-ce71-4397-b7b4-8175741c838f
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# COMException::HResult-Eigenschaft
Das HRESULT, das der Ausnahme entspricht.  
  
## Syntax  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## Eigenschaftswert  
 Ein HRESULT\-Wert, der den Fehler angibt.  
  
## Hinweise  
 Weitere Informationen zur Interpretation des HRESULT\-Werts finden Sie unter [Struktur von COM\-Fehlercodes](http://go.microsoft.com/fwlink/p/?LinkId=262045).  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Überschrift für Unterabschnitt  
  
## Siehe auch  
 [Platform::COMException\-Klasse](../cppcx/platform-comexception-class.md)
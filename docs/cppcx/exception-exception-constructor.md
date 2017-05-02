---
title: "Exception::Exception-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::Exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::Exception-Konstruktor"
ms.assetid: 173b434e-e3a8-41f5-904e-0e8fc0f21950
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::Exception-Konstruktor
Initialisiert eine neue Instanz der Exception\-Klasse.  
  
## Syntax  
  
```cpp  
  
Exception(int32 hresult)  
Exception(int32 hresult, ::Platform::String^ message)  
```  
  
#### Parameter  
 `hresult`  
 Der Fehler HRESULT, der durch die Ausnahme repräsentiert wird.  
  
 `message`  
 Eine vom Benutzer angegebene Meldung, beispielsweise vorschreibender Text, der der Ausnahme zugeordnet ist. Im Allgemeinen sollten Sie die zweite Überladung verwenden, um eine beschreibende Meldung bereitzustellen, die möglichst spezifisch erläutert, wie und warum der Fehler aufgetreten ist.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)
---
title: "Platform::Delegate-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Delegate-Klasse"
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::Delegate-Klasse
Darstellen eines Funktionsobjekts.  
  
## Syntax  
  
```cpp  
public delegate void delegate_name();  
```  
  
## Mitglieder  
 Die Delegate\-Klasse umfasst die Methoden Equals\(\), GetHashCode\(\) und ToString\(\), die von der [Platform::Object\-Klasse](../cppcx/platform-object-class.md) abgeleitet werden.  
  
## Hinweise  
 Verwenden Sie das Schlüsselwort [delegate](~/windows/delegate-cpp-component-extensions.md), um Delegaten zu erstellen. Verwenden Sie nicht explizit „Platform::Delegate“. Weitere Informationen finden Sie unter [Delegaten](../cppcx/delegates-c-cx.md). Ein Beispiel zum Erstellen und Verwenden eines Delegaten finden Sie unter [Erstellen von Windows\-Runtime\-Komponenten in C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf).  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)
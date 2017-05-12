---
title: "Platform::Guid-Wertklasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Guid-Struktur"
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Guid-Wertklasse
Stellt einen [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx)\-Typ im Windows Runtime\-Typsystem dar.  
  
## Syntax  
  
```cpp  
public value struct Guid  
```  
  
## Mitglieder  
 GUID enthält die Methoden Equals\(\), GetHashCode\(\) und ToString\(\), die von der [Platform::Object\-Klasse](../cppcx/platform-object-class.md), und die GetTypeCode\(\)\-Methode, die von der [Platform::Type\-Klasse](../cppcx/platform-type-class.md). Der Guid verfügt auch über die folgenden Member.  
  
|Member|Beschreibung|  
|------------|------------------|  
|Guid|Initialisiert eine neue Instanz der Guid\-Struktur.|  
|operator\=\=|Entspricht Operator.|  
|Operator\!\=|Entspricht nicht Operator.|  
|Operator\(\)|Konvertiert ein GUID in ein GUID.|  
  
## Hinweise  
 Ein Beispiel für das Generieren einer neuen Platform::Guid mithilfe der Windows\-Funktion [CoCreateGuid](http://msdn.microsoft.com/library/windows/desktop/ms688568\(v=vs.85\).aspx) finden Sie unter [WinRT\-Komponente: Wie generiert man eine GUID?](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)
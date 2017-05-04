---
title: "Platform::IDisposable-Schnittstelle | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IDisposable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IDisposable-Schnittstelle"
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 2
---
# Platform::IDisposable-Schnittstelle
Wird verwendet, um nicht verwaltete Ressourcen freizugeben.  
  
## Syntax  
  
```cpp  
public interface class IDisposable  
```  
  
## Attribute  
 **GuidAttribute**\("de0cbaea\-8065\-4a45\-b196\-c9d443f9bab3"\)  
  
 **VersionAttribute**\(NTDDI\_WIN8\)  
  
## Mitglieder  
 Die IDisposable\-Schnittstelle erbt von der IUnknown\-Schnittstelle. IDisposable verfügt auch über die folgenden Membertypen:  
  
 **Methoden**  
  
 Die IDisposable\-Schnittstelle verfügt über die folgenden Methoden.  
  
|Methode|Beschreibung|  
|-------------|------------------|  
|HYPERLINK "http:\/\/msdnpreview.redmond.corp.microsoft.com\/en\-us\/library\/windows\/apps\/platform.idisposable.dispose.aspx" Dispose|Wird verwendet, um nicht verwaltete Ressourcen freizugeben.|  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform
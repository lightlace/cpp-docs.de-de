---
title: "String::Data-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Data"
ms.assetid: 9be4e015-dfb8-431e-a252-8498bd833f03
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Data-Methode
Gibt einen Zeiger zum Anfang des Datenpuffers des Objekts als ein Array im C\-Format mit `char16`\-Elementen \(`wchar_t`\) zurück.  
  
## Syntax  
  
```  
const char16* Data()  
```  
  
## Rückgabewert  
 Ein Zeiger zum Anfang eines `const` `char16`\-Arrays von Unicode\-Zeichen \(`char16` ist Typedef für `wchar_t`\).  
  
## Hinweise  
 Verwenden Sie diese Methode zum Konvertieren von `Platform::String^` zu `wchar_t*`. Wenn das `String`\-Objekt den Gültigkeitsbereich verlässt, ist die Gültigkeit des Datenzeigers nicht mehr sichergestellt. Um die Daten über die ursprünglichen Lebensdauer des `String`\-Objekts hinaus zu speichern, verwenden Sie [wcscpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) zum Kopieren des Arrays in den von Ihnen zugeordneten Arbeitsspeicher.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** vccorlib.h  
  
## Siehe auch  
 [Platform::String\-Klasse](../cppcx/platform-string-class.md)   
 [String::Begin\-Methode](../cppcx/string-begin-method.md)
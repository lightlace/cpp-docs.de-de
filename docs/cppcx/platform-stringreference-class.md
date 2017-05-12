---
title: "Platform::StringReference-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::StringReference"
dev_langs: 
  - "C++"
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::StringReference-Klasse
Ein Optimierungstyp, den Sie verwenden können, um Zeichenfolgendaten in `Platform::String^` Eingabeparametern mit minimalem Kopiervorgängen weitere Methoden zu übergeben.  
  
## Syntax  
  
```cpp  
class StringReference  
```  
  
## Hinweise  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[StringReference::StringReference\-Konstruktor](../cppcx/stringreference-stringreference-constructor.md)|Zwei Konstruktoren für das Erstellen von Instanzen von `StringReference`.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[StringReference::Data\-Methode](../cppcx/stringreference-data-method.md)|Gibt die Zeichenfolgendaten als char16\-Wertearray zurück.|  
|[StringReference::Length\-Methode](../cppcx/stringreference-length-method.md)|Gibt die Anzahl der Zeichen in der Zeichenfolge zurück.|  
|[StringReference::GetHSTRING\-Methode](../cppcx/stringreference-gethstring-method.md)|Gibt die Zeichenfolgendaten als HSTRING zurück.|  
|[StringReference::GetString\-Methode](../cppcx/stringreference-getstring-method.md)|Gibt die Zeichenfolgendaten als `Platform::String^` zurück.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|`StringReference::operator=`|Weist ein `StringReference`\-Element einer neuen `StringReference`\-Instanz zu.|  
|`StringReference::operator()`|Konvertiert ein `StringReference`\-Element in ein `Platform::String^`\-Element.|  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::StringReference Class](../cppcx/platform-stringreference-class.md)
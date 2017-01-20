---
title: "space_info-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::space_info"
dev_langs: 
  - "C++"
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
caps.latest.revision: 13
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# space_info-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Enthält Informationen zu einem Volume.  
  
## Syntax  
  
```  
struct space_info;  
```  
  
## Mitglieder  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|`unsigned long long available`|Gibt die Anzahl der Bytes an, die zum Darstellen der Daten auf dem Volume verfügbar sind.|  
|`unsigned long long capacity`|Gibt die Gesamtanzahl der Bytes an, die vom Volume dargestellt werden können.|  
|`unsigned long long free`|Gibt die Anzahl der Bytes an, die nicht zum Darstellen der Daten auf dem Volume verwendet werden.|  
  
## Anforderungen  
 **Header:** Dateisystem  
  
 **Namespace:** std::tr2::sys  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../standard-library/filesystem.md)   
 [space\-Funktion](assetId:///7fce0b0e-523b-4598-b218-47245d0204ca)   
 [Dateisystemnavigation \(C\+\+\)](../standard-library/file-system-navigation.md)
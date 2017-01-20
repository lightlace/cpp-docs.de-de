---
title: "HSE_VERSION_INFO-Struktur"
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
  - "HSE_VERSION_INFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HSE_VERSION_INFO-Struktur"
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# HSE_VERSION_INFO-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Struktur ist für `pVer` durch den Parameter in der Memberfunktion `CHttpServer::GetExtensionVersion` gezeigt.  Sie stellt die ISA\-Versionsnummer und eine Textbeschreibung des ISA.  
  
## Syntax  
  
```  
  
      typedef struct _HSE_VERSION_INFO {  
   DWORD dwExtensionVersion;  
   CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### Parameter  
 *dwExtensionVersion*  
 Die Versionsnummer der ISA.  
  
 *lpszExtensionDesc*  
 Die Textbeschreibung des ISA.  Die Standardimplementierung stellt Platzhaltertext; `CHttpServer::GetExtensionVersion` überschreiben, um Ihre eigenen Beschreibung bereitzustellen.  
  
## Anforderungen  
 **Header:** httpext.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
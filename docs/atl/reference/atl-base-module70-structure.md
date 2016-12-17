---
title: "_ATL_BASE_MODULE70 Structure"
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
  - "ATL::_ATL_BASE_MODULE70"
  - "ATL._ATL_BASE_MODULE70"
  - "_ATL_BASE_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_BASE_MODULE70 structure"
  - "ATL_BASE_MODULE70 structure"
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
caps.latest.revision: 15
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_BASE_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird von einem Projekt, das ATL verwendet.  
  
## Syntax  
  
```  
  
      struct _ATL_BASE_MODULE70{  
   UINT cbSize;  
   HINSTANCE m_hInst;  
   HINSTANCE m_hInstResource;  
   bool m_bNT5orWin98;  
   DWORD dwAtlBuildVer;  
   GUID* pguidVer;  
   CRITICAL_SECTION m_csResource;  
   CSimpleArray<HINSTANCE> m_rgResourceInstance;  
};  
```  
  
## Mitglieder  
 `cbSize`  
 Die Größe der Struktur, verwendet für die Versionsverwaltung.  
  
 `m_hInst`  
 **hInstance** für dieses Modul \(entweder EXE oder DLL\).  
  
 `m_hInstResource`  
 Standardinstanzressourcenhandle.  
  
 **m\_bNT5orWin98**  
 Informationen zur Version des Betriebssystems.  Intern verwendet von ATL.  
  
 **dwAtlBuildVer**  
 Speichert die Version von ATL.  Derzeit 0x0700.  
  
 **pguidVer**  
 Internes GUID ATL.  
  
 **m\_csResource**  
 Wird verwendet, um den Zugriff auf das **m\_rgResourceInstance** Array zu synchronisieren.  Intern verwendet von ATL.  
  
 **m\_rgResourceInstance**  
 Kleiden Sie verwendet, um für Ressourcen in allen Ressourceninstanzen zu suchen, die ATL berücksichtigt.  Intern verwendet von ATL.  
  
## Hinweise  
 [\_ATL\_BASE\_MODULE](../Topic/_ATL_BASE_MODULE.md) wird als Typedef von `_ATL_BASE_MODULE70` definiert.  
  
## Anforderungen  
 **Header:** atlcore.h  
  
## Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)
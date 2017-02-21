---
title: "_ATL_WIN_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_WIN_MODULE70"
  - "ATL::_ATL_WIN_MODULE70"
  - "ATL._ATL_WIN_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_WIN_MODULE70 structure"
  - "ATL_WIN_MODULE70 structure"
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# _ATL_WIN_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird von Fenstercode in ATL.  
  
## Syntax  
  
```  
  
      struct _ATL_WIN_MODULE70{  
   UNIT cbSize;  
   CRITICAL_SECTION m_csWindowCreate;  
   _AtlCreateWndData* m_pCreateWndList;  
   CSimpleArray<ATOM> m_rgWindowClassAtoms;  
};  
```  
  
## Mitglieder  
 `cbSize`  
 Die Größe der Struktur, verwendet für die Versionsverwaltung.  
  
 `m_csWindowCreate`  
 Wird verwendet, um den Zugriff auf das Fensterregistrierungscode zu serialisieren.  Intern verwendet von ATL.  
  
 **m\_pCreateWndList**  
 Wird verwendet, um Fenster auf ihre Objekte binden.  Intern verwendet von ATL.  
  
 **m\_rgWindowClassAtoms**  
 Wird verwendet, um Fensterklassenregistrierungen nachzuverfolgen, damit sie in der Beendigung ordnungsgemäß Registrierung aufgehoben werden können.  Intern verwendet von ATL.  
  
## Hinweise  
 [\_ATL\_WIN\_MODULE](../Topic/_ATL_WIN_MODULE.md) wird als Typedef von `_ATL_WIN_MODULE70` definiert.  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)
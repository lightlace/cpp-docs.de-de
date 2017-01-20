---
title: "_ATL_WIN_MODULE70 Structure"
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
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
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
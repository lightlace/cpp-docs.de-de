---
title: "_ATL_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_MODULE70"
  - "ATL::_ATL_MODULE70"
  - "ATL._ATL_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_MODULE70 structure"
  - "ATL_MODULE70 structure"
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# _ATL_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Enthält die Daten, die in jedes ATL\-Modul verwendet werden.  
  
## Syntax  
  
```  
  
      struct _ATL_MODULE70{  
   UINT cbSize;  
   LONG m_nLockCnt;  
   _ATL_TERMFUNC_ELEM* m_pTermFuncs;  
   CComCriticalSection m_csStaticDataInitAndTypeInfo;  
};  
```  
  
## Mitglieder  
 `cbSize`  
 Die Größe der Struktur, verwendet für die Versionsverwaltung.  
  
 `m_nLockCnt`  
 Verweiszähler, zu bestimmen, wie lange das Modul aktiv bleiben soll.  
  
 **m\_pTermFuncs**  
 Verfolgt Funktionen, die registriert wurden aufgerufen werden, als ATL heruntergefahren wird.  
  
 **m\_csStaticDataInitAndTypeInfo**  
 Wird verwendet, um den Zugriff auf interne Daten in den sechs Situationen zu koordinieren.  
  
## Hinweise  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md) wird als Typedef von `_ATL_MODULE70` definiert.  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)
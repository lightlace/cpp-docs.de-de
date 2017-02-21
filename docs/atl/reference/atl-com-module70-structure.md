---
title: "_ATL_COM_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::_ATL_COM_MODULE70"
  - "ATL._ATL_COM_MODULE70"
  - "_ATL_COM_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_COM_MODULE70 structure"
  - "ATL_COM_MODULE70 structure"
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# _ATL_COM_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird vom Code nämlich in ATL.  
  
## Syntax  
  
```  
  
      struct _ATL_COM_MODULE70{  
   UINT cbSize;  
   HINSTANCE m_hInstTypeLib;  
   _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;  
   _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;  
   CRITICAL_SECTION m_csObjMap;  
};  
```  
  
## Mitglieder  
 `cbSize`  
 Die Größe der Struktur, verwendet für die Versionsverwaltung.  
  
 `m_hInstTypeLib`  
 Die Handleinstanz die Typbibliothek für dieses Modul.  
  
 **m\_ppAutoObjMapFirst**  
 Adresse des Arrayelements, das den Anfang der Objektzuordnungseinträge für dieses Modul angibt.  
  
 **m\_ppAutoObjMapLast**  
 Adresse des Arrayelements, das das Ende der Objektzuordnungseinträge für dieses Modul angibt.  
  
 `m_csObjMap`  
 Kritischer Abschnitt, um den Zugriff auf den Objektzuordnungseinträgen zu serialisieren.  Intern verwendet von ATL.  
  
## Hinweise  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md) wird als Typedef von `_ATL_COM_MODULE70` definiert.  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)
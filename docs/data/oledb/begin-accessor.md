---
title: "BEGIN_ACCESSOR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BEGIN_ACCESSOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_ACCESSOR-Makro"
  - "BEGIN_ACCESSOR-Makro, Syntax"
ms.assetid: 59d0ff3e-7cfd-4ce8-9a1c-d664c0892a52
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# BEGIN_ACCESSOR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Markiert den Beginn eines Accessoreintrags.  
  
## Syntax  
  
```  
  
BEGIN_ACCESSOR(  
num  
,   
bAuto  
 )  
  
```  
  
#### Parameter  
 *num*  
 \[in\] Die NullOffsetzahl für den Accessor in dieser Accessorzuordnung.  
  
 *bAuto*  
 \[in\] gibt an, wenn dieser Accessor ein automatischer ein Accessor oder manuellen Accessor ist.  Wenn **true**, der Accessor automatisch ist; wenn **false**, der Accessor manuell ist.  Automatischen Accessormitteldaten werden für Sie auf Verschiebungsvorgängen abgerufen.  
  
## Hinweise  
 Im Falle mehrerer Accessoren für ein Rowset, müssen Sie `BEGIN_ACCESSOR_MAP` angeben und das Makro `BEGIN_ACCESSOR` für jeden einzelnen Accessor verwenden.  Das Makro `BEGIN_ACCESSOR` wird mit dem Makro `END_ACCESSOR` abgeschlossen.  Das Makro `BEGIN_ACCESSOR_MAP` wird mit dem Makro `END_ACCESSOR_MAP` abgeschlossen.  
  
## Beispiel  
 Siehe [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)
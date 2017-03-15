---
title: "IConvertTypeImpl::CanConvert | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IConvertTypeImpl.CanConvert"
  - "CanConvert"
  - "IConvertTypeImpl::CanConvert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanConvert-Methode"
ms.assetid: bdad6e95-bc0b-4427-9b5e-eea51f09f392
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IConvertTypeImpl::CanConvert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt Informationen zur Verfügbarkeit von Typkonvertierungen auf einen Befehl oder auf einem Rowset.  
  
## Syntax  
  
```  
  
      STDMETHOD(CanConvert)(   
   DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags    
);  
```  
  
#### Parameter  
 Siehe [IConvertType::CanConvert](https://msdn.microsoft.com/en-us/library/ms711224.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Verwendung OLE DB\-Datenkonvertierung in `MSADC.DLL`.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IConvertTypeImpl\-Klasse](../../data/oledb/iconverttypeimpl-class.md)
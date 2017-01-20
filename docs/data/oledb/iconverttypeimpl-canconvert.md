---
title: "IConvertTypeImpl::CanConvert"
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
  - "IConvertTypeImpl.CanConvert"
  - "CanConvert"
  - "IConvertTypeImpl::CanConvert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanConvert-Methode"
ms.assetid: bdad6e95-bc0b-4427-9b5e-eea51f09f392
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
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
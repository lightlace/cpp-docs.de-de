---
title: "CUtlProps::IsValidValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CUtlProps::IsValidValue"
  - "CUtlProps.IsValidValue"
  - "IsValidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsValidValue-Methode"
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CUtlProps::IsValidValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird verwendet, um einen Wert zu prüfen, bevor eine Eigenschaft festgelegt wird.  
  
## Syntax  
  
```  
  
      virtual HRESULT CUtlPropsBase::IsValidValue(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
```  
  
#### Parameter  
 `iCurSet`  
 Der Index im Eigenschaftensatzarray; null wenn nur einen Eigenschaftensatz gibt.  
  
 `pDBProp`  
 Die Eigenschaften\-ID und der neue Wert in [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) eine Struktur.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  Der Standardrückgabewert ist `S_OK`.  
  
## Hinweise  
 Wenn Sie irgendeine Validierungsroutinen haben, die Sie für einen Wert ausgeführt werden soll, der im Begriff sind zu verwenden, um eine Eigenschaft festzulegen, können Sie diese Funktion beibehalten.  Beispielsweise können Sie **DBPROP\_AUTH\_PASSWORD** für eine Kennworttabelle überprüfen, einen gültigen Wert zu ermitteln.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [CUtlProps\-Klasse](../../data/oledb/cutlprops-class.md)
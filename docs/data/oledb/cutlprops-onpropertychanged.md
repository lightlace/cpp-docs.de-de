---
title: "CUtlProps::OnPropertyChanged | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnPropertyChanged"
  - "CUtlProps.OnPropertyChanged"
  - "CUtlProps::OnPropertyChanged"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnPropertyChanged-Methode"
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CUtlProps::OnPropertyChanged
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird aufgerufen, nachdem dem Festlegen einer Eigenschaft, um zu behandeln, verketteten Eigenschaften.  
  
## Syntax  
  
```  
  
      virtual HRESULT OnPropertyChanged(  
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
 Wenn Sie Eigenschaften verkettete behandeln, wie Lesezeichen oder aktualisiert, deren Werte aus einem anderen Eigenschaft abhängig sind, sollten Sie diese Funktion beibehalten.  
  
## Beispiel  
 In dieser Funktion ruft der Benutzer die vom `DBPROP*`\-Parameter mehrmals ab.  Jetzt ist es möglich, die ID für eine Eigenschaft zu vergleichen, um zu verketten.  Wenn die Eigenschaft gefunden wird, wird `SetProperties` mit der Eigenschaft aufgerufen, die jetzt in Verbindung mit der anderen Eigenschaft festgelegt wird.  In diesem Fall wird `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS` oder `DBPROP_ORDEREDBOOKMARKS`\-Eigenschaft abruft, kann der `DBPROP_BOOKMARKS`\-Eigenschaft festlegen.  
  
 [!CODE [NVC_OLEDB_Provider#2](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Provider#2)]  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [CUtlProps\-Klasse](../../data/oledb/cutlprops-class.md)
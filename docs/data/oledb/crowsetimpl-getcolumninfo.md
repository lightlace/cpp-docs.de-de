---
title: "CRowsetImpl::GetColumnInfo"
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
  - "GetColumnInfo"
  - "CRowsetImpl.GetColumnInfo"
  - "CRowsetImpl::GetColumnInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnInfo-Methode"
ms.assetid: 9ef76525-f996-4c6f-81b9-68eb260350ef
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::GetColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft Spalteninformationen für eine bestimmte Clientanforderung ab.  
  
## Syntax  
  
```  
  
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(  
   T* pv,  
   ULONG* pcCols   
);  
```  
  
#### Parameter  
 `pv`  
 \[in\] Ein Zeiger auf die `CRowsetImpl` abgeleiteten Klasse des Benutzers.  
  
 `pcCols`  
 \[in\] Ein Zeiger \(Ausgabe\) zur Anzahl zurückgegeben.  
  
## Rückgabewert  
 Ein Zeiger auf eine statische **ATLCOLUMNINFO**\-Struktur.  
  
## Hinweise  
 Diese Methode stellt eine fortgeschrittene Überschreibung.  
  
 Diese Methode wird von mehreren Basisimplementierungsklassen aufgerufen, um Spalteninformationen für eine bestimmte Clientanforderung abzurufen.  Normalerweise würde diese Methode von `IColumnsInfoImpl` aufgerufen.  Wenn Sie diese Methode überschreiben, müssen Sie eine Version der Methode in der von `CRowsetImpl` abgeleiteten Klasse platzieren.  Da die Methode kann einer nicht\-aufVorlagen basierenden Klasse zugeordnet ist, müssen Sie `pv` in `CRowsetImpl` ändern entsprechenden abgeleiteten Klasse.  
  
 Im folgenden Beispiel wird **GetColumnInfo's** verwendet.  In diesem Beispiel wurde **CMyRowset**`CRowsetImpl` abgeleiteten Klasse.  Um `GetColumnInfo` für alle Instanzen dieser Klasse zu überschreiben, fügen Sie die folgende Methode in der Klassendefinition **CMyRowset**:  
  
 [!CODE [NVC_OLEDB_Provider#1](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Provider#1)]  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [CRowsetImpl\-Klasse](../../data/oledb/crowsetimpl-class.md)
---
title: "CDynamicAccessor::SetBlobSizeLimit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor::SetBlobSizeLimit"
  - "SetBlobSizeLimit"
  - "CDynamicAccessor.SetBlobSizeLimit"
  - "ATL.CDynamicAccessor.SetBlobSizeLimit"
  - "ATL::CDynamicAccessor::SetBlobSizeLimit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBlobSizeLimit-Methode"
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::SetBlobSizeLimit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die maximale BLOBgröße in Bytes fest.  
  
## Syntax  
  
```  
  
      void SetBlobSizeLimit(  
   DBLENGTH nBlobSize   
);  
```  
  
#### Parameter  
 `nBlobSize`  
 Gibt die BLOBgrößengrenze an.  
  
## Hinweise  
 Legt die maximale BLOBgröße in Bytes fest; die Spaltendaten, die größer als dieser Wert sind, werden als BLOB behandelt.  Einige Anbieter geben extrem große Größen für Spalten \(z 2 GB\).  Anstatt beim Versuch, eine Spalte diese Größe Speicher zu belegen, wird normalerweise versuchen, diese Spalten als Blobs zu binden.  Auf diese Weise müssen Sie nicht den gesamten belegten Arbeitsspeicher zuordnen, Sie können jedoch alle Daten ohne Angst vor Kürzung ausgelesen werden.  Es gibt jedoch einige Situationen, in denen Sie `CDynamicAccessor` erzwingen sollten, um große Spalten in ihren systemeigenen Datentypen zu binden.  Hierzu rufen `SetBlobSizeLimit` auf, bevor Sie **Öffnen** aufrufen.  
  
 Die Konstruktormethode [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) legt die maximale BLOBgröße auf den Standardwert 8.000 Bytes fest.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)
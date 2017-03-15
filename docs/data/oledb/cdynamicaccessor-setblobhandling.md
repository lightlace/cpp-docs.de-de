---
title: "CDynamicAccessor::SetBlobHandling | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor::SetBlobHandling"
  - "CDynamicAccessor.SetBlobHandling"
  - "ATL::CDynamicAccessor::SetBlobHandling"
  - "SetBlobHandling"
  - "ATL.CDynamicAccessor.SetBlobHandling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBlobHandling-Methode"
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::SetBlobHandling
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt den BLOBbehandlungswert für die aktuelle Zeile fest.  
  
## Syntax  
  
```  
  
      bool SetBlobHandling(  
   DBBLOBHANDLINGENUM eBlobHandling   
);  
```  
  
#### Parameter  
 `eBlobHandling`  
 Gibt an, wie die Verarbeitungsmöglichkeiten behandelt werden sollen.  Sie kann folgende Werte annehmen:  
  
-   **DBBLOBHANDLING\_DEFAULT**: Bearbeiten Sie die Daten anderer Spalten, die größer sind als `nBlobSize` \(z legen Sie durch `SetBlobSizeLimit`\) als Verarbeitungsmöglichkeiten und rufen Sie es durch ein `ISequentialStream` oder `IStream`\-Objekt ab.  Diese Option wird versucht, jede Spalte zu binden, die die Daten enthält, die größer als `nBlobSize` oder als **DBTYPE\_IUNKNOWN** als Verarbeitungsmöglichkeiten aufgeführt sind.  
  
-   **DBBLOBHANDLING\_NOSTREAMS**: Bearbeiten Sie die Daten anderer Spalten, die größer sind als `nBlobSize` \(z legen Sie durch `SetBlobSizeLimit`\) als Verarbeitungsmöglichkeiten und rufen Sie es als Verweis in Anbieter\-zugeordnetem, Consumer\-Besitzem Speicher.  Diese Option ist für Tabellen an, die mehr als eine BLOBspalte haben, und der Anbieter unterstützt nur ein `ISequentialStream`\-Objekt pro Accessor.  
  
-   **DBBLOBHANDLING\_SKIP**: Überspringen Sie \(nicht gilt\) Bindung, die Spalten, die als Zeichenfolge mit Blobs sich qualifizieren \(der Accessor bindet nicht oder ruft den Spaltenwert ab, aber er ruft weiterhin den Spaltenstatus und \-Länge\) ab.  
  
## Hinweise  
 Sie sollten `SetBlobHandling` aufrufen, bevor Sie **Öffnen** aufrufen.  
  
 Die Konstruktormethode [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) legt den BLOBbehandlungswert auf **DBBLOBHANDLING\_DEFAULT** fest.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)
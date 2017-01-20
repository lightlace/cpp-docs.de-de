---
title: "CDynamicAccessor::CDynamicAccessor"
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
  - "CDynamicAccessor::CDynamicAccessor"
  - "ATL::CDynamicAccessor::CDynamicAccessor"
  - "ATL.CDynamicAccessor.CDynamicAccessor"
  - "CDynamicAccessor.CDynamicAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicAccessor-Klasse, Konstruktor"
ms.assetid: bf40fe81-2c85-473e-9075-51ad9b060b39
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::CDynamicAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Instanziiert und initialisiert das `CDynamicAccessor`\-Objekt.  
  
## Syntax  
  
```  
  
      CDynamicAccessor(   
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000   
);  
```  
  
#### Parameter  
 `eBlobHandling`  
 Gibt an, wie die Binary Large Object\-Daten \(BLOB\) behandelt werden sollen.  Der Standardwert ist **DBBLOBHANDLING\_DEFAULT**.  [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) finden Sie eine Beschreibung der **DBBLOBHANDLINGENUM**\-Werte.  
  
 `nBlobSize`  
 Die maximale BLOBgröße in Bytes; Spaltendaten über diesen Wert werden als BLOB behandelt.  Der Standardwert ist 8,000.  Ausführliche Informationen finden Sie unter [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md).  
  
## Hinweise  
 Wenn Sie den Konstruktor verwenden, um das `CDynamicAccessor`\-Objekt zu initialisieren, können Sie angeben, wie es Blobs bindet.  Blobs können Binärdaten wie Grafiken, Sound oder kompilierte Code enthalten.  Das Standardverhalten ist, Spalten mehr als 8.000 Bytes als Blobs zu behandeln und versuchen, sie mit einem `ISequentialStream`\-Objekt zu binden.  Sie können jedoch einen anderen Wert angeben, um die BLOBgröße zu sein.  
  
 Sie können auch angeben, wie `CDynamicAccessor` Spaltendaten behandelt, die als sicher Verarbeitungsmöglichkeiten qualifiziert: Verarbeitungsmöglichkeiten es kann mit dem Standardverfahren behandeln; kann \(nicht mögen Bindung\), Verarbeitungsmöglichkeiten überspringen; oder es kann in Anbieter\-zugeordnetem Verarbeitungsmöglichkeiten Arbeitsspeicher binden.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)
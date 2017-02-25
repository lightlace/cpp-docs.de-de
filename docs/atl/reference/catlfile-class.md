---
title: "CAtlFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlFile"
  - "ATL::CAtlFile"
  - "ATL.CAtlFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFile class"
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CAtlFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt einen dünnen Wrapper um die Windows\-DateiBehandlung API bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CAtlFile : public CHandle  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlFile::CAtlFile](../Topic/CAtlFile::CAtlFile.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlFile::Create](../Topic/CAtlFile::Create.md)|Rufen Sie diese Methode auf, um eine Datei zu erstellen oder zu öffnen.|  
|[CAtlFile::Flush](../Topic/CAtlFile::Flush.md)|Rufen Sie diese Methode auf, um die Puffer für die Datei zu löschen und alle gepufferten Daten wird, in die Datei geschrieben werden.|  
|[CAtlFile::GetOverlappedResult](../Topic/CAtlFile::GetOverlappedResult.md)|Rufen Sie diese Methode auf, um die Ergebnisse eines überlappende Vorgangs für die Datei abzurufen.|  
|[CAtlFile::GetPosition](../Topic/CAtlFile::GetPosition.md)|Rufen Sie diese Methode auf, um die Zeigerposition der aktuellen Datei aus der Datei abzurufen.|  
|[CAtlFile::GetSize](../Topic/CAtlFile::GetSize.md)|Rufen Sie diese Methode auf, um die Größe in Bytes der Datei abzurufen.|  
|[CAtlFile::LockRange](../Topic/CAtlFile::LockRange.md)|Rufen Sie diese Methode auf, um einen Bereich in der Datei zu sperren, um andere Prozesse nicht auf auf sie zu verhindern.|  
|[CAtlFile::Read](../Topic/CAtlFile::Read.md)|Rufen Sie diese Methode auf, um Daten aus einer Datei zu lesen, die in der Position beginnt, die vom Dateizeiger angegeben wird.|  
|[CAtlFile::Seek](../Topic/CAtlFile::Seek.md)|Rufen Sie diese Methode auf, um den Dateizeiger der Datei zu verschieben.|  
|[CAtlFile::SetSize](../Topic/CAtlFile::SetSize.md)|Rufen Sie diese Methode auf, um die Größe der Datei festzulegen.|  
|[CAtlFile::UnlockRange](../Topic/CAtlFile::UnlockRange.md)|Rufen Sie diese Methode auf, um einen Bereich der Datei bei.|  
|[CAtlFile::Write](../Topic/CAtlFile::Write.md)|Rufen Sie diese Methode auf, um Daten in die Datei schreiben, die in der Position beginnt, die vom Dateizeiger angegeben wird.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlFile::m\_pTM](../Topic/CAtlFile::m_pTM.md)|Zeiger auf `CAtlTransactionManager`\-Objekt|  
  
## Hinweise  
 Verwenden Sie diese Klasse, wenn DateiBehandlung Anforderungen relativ einfach sind, jedoch höhere Abstraktion, als Windows\-API sind erforderlich bereitstellen, ohne MFC\-Abhängigkeiten einzuschließen.  
  
## Vererbungshierarchie  
 [CHandle](../../atl/reference/chandle-class.md)  
  
 `CAtlFile`  
  
## Anforderungen  
 **Header:** atlfile.h  
  
## Siehe auch  
 [Marquee\-Beispiel](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CHandle Class](../../atl/reference/chandle-class.md)
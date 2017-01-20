---
title: "CAtlTemporaryFile Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CAtlTemporaryFile"
  - "ATL.CAtlTemporaryFile"
  - "ATL::CAtlTemporaryFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlTemporaryFile class"
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
caps.latest.revision: 18
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlTemporaryFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden für die Erstellung und Verwendung einer temporären Datei.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CAtlTemporaryFile  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlTemporaryFile::CAtlTemporaryFile](../Topic/CAtlTemporaryFile::CAtlTemporaryFile.md)|Der \-Konstruktor.|  
|[CAtlTemporaryFile::~CAtlTemporaryFile](../Topic/CAtlTemporaryFile::~CAtlTemporaryFile.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlTemporaryFile::Close](../Topic/CAtlTemporaryFile::Close.md)|Rufen Sie diese Methode auf, um eine temporäre Datei zu schließen und entweder, dessen Inhalt zu löschen oder mit dem angegebenen Dateinamen zu speichern.|  
|[CAtlTemporaryFile::Create](../Topic/CAtlTemporaryFile::Create.md)|Rufen Sie diese Methode auf, um eine temporäre Datei erstellen.|  
|[CAtlTemporaryFile::Flush](../Topic/CAtlTemporaryFile::Flush.md)|Rufen Sie diese Methode auf, um alle Daten zu erzwingen, die im weiterhin auf temporären Datei geschrieben werden Dateipuffer.|  
|[CAtlTemporaryFile::GetPosition](../Topic/CAtlTemporaryFile::GetPosition.md)|Rufen Sie diese Methode auf, um die Zeigerposition der aktuellen Datei abzurufen.|  
|[CAtlTemporaryFile::GetSize](../Topic/CAtlTemporaryFile::GetSize.md)|Rufen Sie diese Methode auf, um die Größe in Bytes der temporären Datei abzurufen.|  
|[CAtlTemporaryFile::HandsOff](../Topic/CAtlTemporaryFile::HandsOff.md)|Rufen Sie diese Methode auf, um die Datei aus dem `CAtlTemporaryFile`\-Objekt aufzuheben.|  
|[CAtlTemporaryFile::HandsOn](../Topic/CAtlTemporaryFile::HandsOn.md)|Rufen Sie diese Methode auf, um eine vorhandene temporäre Datei zu öffnen und den Zeiger am Ende der Datei zu positionieren.|  
|[CAtlTemporaryFile::LockRange](../Topic/CAtlTemporaryFile::LockRange.md)|Rufen Sie diese Methode auf, um einen Bereich in der Datei zu sperren, um andere Prozesse nicht auf auf sie zu verhindern.|  
|[CAtlTemporaryFile::Read](../Topic/CAtlTemporaryFile::Read.md)|Rufen Sie diese Methode auf, um Daten aus der temporären Datei zu lesen, die in der Position beginnt, die vom Dateizeiger angegeben wird.|  
|[CAtlTemporaryFile::Seek](../Topic/CAtlTemporaryFile::Seek.md)|Rufen Sie diese Methode auf, um den Dateizeiger der temporären Datei zu verschieben.|  
|[CAtlTemporaryFile::SetSize](../Topic/CAtlTemporaryFile::SetSize.md)|Rufen Sie diese Methode auf, um die Größe der temporären Datei festzulegen.|  
|[CAtlTemporaryFile::TempFileName](../Topic/CAtlTemporaryFile::TempFileName.md)|Rufen Sie diese Methode auf, um den Namen der temporären Datei zurückzugeben.|  
|[CAtlTemporaryFile::UnlockRange](../Topic/CAtlTemporaryFile::UnlockRange.md)|Rufen Sie diese Methode auf, um einen Bereich der temporären Datei zu entsperren.|  
|[CAtlTemporaryFile::Write](../Topic/CAtlTemporaryFile::Write.md)|Rufen Sie diese Methode auf, um Daten in temporären Datei schreiben, die in der Position beginnt, die vom Dateizeiger angegeben wird.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlTemporaryFile::operator HANDLE](../Topic/CAtlTemporaryFile::operator%20HANDLE.md)|Gibt ein Handle zur temporären Datei zurück.|  
  
## Hinweise  
 `CAtlTemporaryFile` erleichtert es, eine temporäre Datei zu erstellen und zu verwenden.  Die Datei ist automatisch benannt, geöffnet, geschlossen und gelöscht.  Wenn der Dateiinhalt erforderlich ist, nachdem die Datei geschlossen ist, können sie in einer neuen Datei mit einem angegebenen Namen gespeichert sind.  
  
## Anforderungen  
 **Header:** atlfile.h  
  
## Beispiel  
 Im Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](../Topic/CAtlTemporaryFile::CAtlTemporaryFile.md).  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CAtlFile Class](../../atl/reference/catlfile-class.md)
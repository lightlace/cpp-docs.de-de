---
title: "CFileException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFileException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFile class, exceptions of"
  - "CFileException class"
  - "Ausnahmen, file type"
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CFileException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine dateibezogene Ausnahmebedingung dar.  
  
## Syntax  
  
```  
class CFileException : public CException  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFileException::CFileException](../Topic/CFileException::CFileException.md)|Erstellt ein `CFileException`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFileException::ErrnoToException](../Topic/CFileException::ErrnoToException.md)|EINGABETASTEursachencode entsprechend einer Laufzeitfehlernummer an.|  
|[CFileException::GetErrorMessage](../Topic/CFileException::GetErrorMessage.md)|Ruft die Meldung ab, die eine Ausnahme beschreibt.|  
|[CFileException::OsErrorToException](../Topic/CFileException::OsErrorToException.md)|Gibt einen Ursachencode entsprechend einem Betriebssystemfehlercode zurück.|  
|[CFileException::ThrowErrno](../Topic/CFileException::ThrowErrno.md)|Löst eine Dateiausnahme auf Grundlage einer Ablauffehlernummer aus.|  
|[CFileException::ThrowOsError](../Topic/CFileException::ThrowOsError.md)|Löst eine Dateiausnahme auf Grundlage einer Betriebssystemfehlernummer aus.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CFileException::m\_cause](../Topic/CFileException::m_cause.md)|Enthält portablen Code entsprechend der Ausnahmeursache.|  
|[CFileException::m\_lOsError](../Topic/CFileException::m_lOsError.md)|Enthält die zugehörige Betriebssystemfehlernummer.|  
|[CFileException::m\_strFileName](../Topic/CFileException::m_strFileName.md)|Enthält den Namen der Datei für diese Ausnahme.|  
  
## Hinweise  
 Die Klasse enthält `CFileException` öffentliche Datenmember, die den portablen Ursachencode und die betriebssystemspezifische Fehlernummer enthalten.  Die Klasse stellt auch statische Memberfunktionen zum Auslösen von Dateiausnahmen und für die Rückgabe von Ursachencodes für Betriebssystemfehler und C\-Laufzeit\-Fehler bereit.  
  
 `CFileException`\-Objekte werden in `CFile`\-Memberfunktionen und in Memberfunktionen von abgeleiteten Klassen erstellt und ausgelöst.  Sie können auf diese Objekte im Rahmen eines Ausdrucks **CATCH** zugreifen.  Für Portabilität verwenden Sie nur den Ursachencode, um den Grund für eine Ausnahme abrufen.  Weitere Informationen zu Ausnahmen, finden Sie im Artikel [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Ausnahmeverarbeitung](../../mfc/reference/exception-processing.md)
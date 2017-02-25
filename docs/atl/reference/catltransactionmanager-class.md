---
title: "CAtlTransactionManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlTransactionManager"
  - "atltransactionmanager/ATL::CAtlTransactionManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlTransactionManager class"
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CAtlTransactionManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CAtlTransactionManager\-Klasse stellt einen Wrapper zu den Funktionen des Kernel\-Transaktions\-Managers \(KTM\) bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
class CAtlTransactionManager;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlTransactionManager::~CAtlTransactionManager](../Topic/CAtlTransactionManager::~CAtlTransactionManager.md)|CAtlTransactionManager\-Destruktor.|  
|[CAtlTransactionManager::CAtlTransactionManager](../Topic/CAtlTransactionManager::CAtlTransactionManager.md)|CAtlTransactionManager\-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlTransactionManager::Close](../Topic/CAtlTransactionManager::Close.md)|Schließt ein das Transaktionshandle.|  
|[CAtlTransactionManager::Commit](../Topic/CAtlTransactionManager::Commit.md)|Die diese Anforderungen die Transaktion ein Commit durchgeführt.|  
|[CAtlTransactionManager::Create](../Topic/CAtlTransactionManager::Create.md)|Stellt das Transaktionshandle erstellt.|  
|[CAtlTransactionManager::CreateFile](../Topic/CAtlTransactionManager::CreateFile.md)|Erstellt oder öffnet eine Datei, einen Dateistream oder ein Verzeichnis als transaktiver Vorgang.|  
|[CAtlTransactionManager::DeleteFile](../Topic/CAtlTransactionManager::DeleteFile.md)|Löscht eine vorhandene Datei als transaktiver Vorgang.|  
|[CAtlTransactionManager::FindFirstFile](../Topic/CAtlTransactionManager::FindFirstFile.md)|Sucht in einem Verzeichnis für eine Datei oder ein Unterverzeichnis als transaktiver Vorgang.|  
|[CAtlTransactionManager::GetFileAttributes](../Topic/CAtlTransactionManager::GetFileAttributes.md)|Ruft Dateisystemattribute für eine bestimmte Datei oder ein Verzeichnis als transaktiver Vorgang ab.|  
|[CAtlTransactionManager::GetFileAttributesEx](../Topic/CAtlTransactionManager::GetFileAttributesEx.md)|Ruft Dateisystemattribute für eine bestimmte Datei oder ein Verzeichnis als transaktiver Vorgang ab.|  
|[CAtlTransactionManager::GetHandle](../Topic/CAtlTransactionManager::GetHandle.md)|Gibt das Transaktionshandle zurück.|  
|[CAtlTransactionManager::IsFallback](../Topic/CAtlTransactionManager::IsFallback.md)|Bestimmt, ob die Fallbackaufrufe aktiviert werden.|  
|[CAtlTransactionManager::MoveFile](../Topic/CAtlTransactionManager::MoveFile.md)|Verschiebt eine vorhandene Datei oder ein Verzeichnis, einschließlich seiner untergeordneten Elemente, als transaktiver Vorgang.|  
|[CAtlTransactionManager::RegCreateKeyEx](../Topic/CAtlTransactionManager::RegCreateKeyEx.md)|Erstellt den angegebenen Registrierungsschlüssel und ordnet ihn einer Transaktion zu.  Wenn der Schlüssel bereits vorhanden ist, wird die Funktion diese.|  
|[CAtlTransactionManager::RegDeleteKey](../Topic/CAtlTransactionManager::RegDeleteKey.md)|Löscht einen Unterschlüssel und die Werte von der angegebenen plattformspezifischen Ansicht der Registrierung als transaktiver Vorgang.|  
|[CAtlTransactionManager::RegOpenKeyEx](../Topic/CAtlTransactionManager::RegOpenKeyEx.md)|Öffnet den angegebenen Registrierungsschlüssel und ordnet ihn einer Transaktion zu.|  
|[CAtlTransactionManager::Rollback](../Topic/CAtlTransactionManager::Rollback.md)|Anforderungen, die die Transaktion ein Rollback.|  
|[CAtlTransactionManager::SetFileAttributes](../Topic/CAtlTransactionManager::SetFileAttributes.md)|Legt die Attribute für eine Datei oder ein Verzeichnis als transaktiver Operation fest.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlTransactionManager::m\_bFallback](../Topic/CAtlTransactionManager::m_bFallback.md)|`TRUE`, wenn das Fallback unterstützt wird; `FALSE` andernfalls.|  
|[CAtlTransactionManager::m\_hTransaction](../Topic/CAtlTransactionManager::m_hTransaction.md)|Das Transaktionshandle.|  
  
## Hinweise  
  
## Vererbungshierarchie  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## Anforderungen  
 **Header:**  atltransactionmanager.h  
  
## Siehe auch  
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)
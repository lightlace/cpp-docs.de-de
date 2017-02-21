---
title: "CAsyncMonikerFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAsyncMonikerFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], Asynchron"
  - "asynchronous controls [C++]"
  - "CAsyncMonikerFile class"
  - "IMoniker interface, Bindung"
  - "monikers [C++], MFC"
  - "OLE-Steuerelemente [C++], Asynchron"
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAsyncMonikerFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt Funktionalität für die Verwendung von asynchronen Monikern in ActiveX\-Steuerelementen \(früher OLE\-Steuerelemente\).  
  
## Syntax  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](../Topic/CAsyncMonikerFile::CAsyncMonikerFile.md)|Erstellt ein `CAsyncMonikerFile`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAsyncMonikerFile::Close](../Topic/CAsyncMonikerFile::Close.md)|Schließt und gibt alle Ressourcen frei.|  
|[CAsyncMonikerFile::GetBinding](../Topic/CAsyncMonikerFile::GetBinding.md)|Ruft einen Zeiger auf die asynchrone Übergangsbindung ab.|  
|[CAsyncMonikerFile::GetFormatEtc](../Topic/CAsyncMonikerFile::GetFormatEtc.md)|Ruft das Format der Daten im Stream ab.|  
|[CAsyncMonikerFile::Open](../Topic/CAsyncMonikerFile::Open.md)|Öffnet eine Datei asynchron.|  
  
### Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](../Topic/CAsyncMonikerFile::CreateBindStatusCallback.md)|Erstellt ein COM\-Objekt, das `IBindStatusCallback` implementiert.|  
|[CAsyncMonikerFile::GetBindInfo](../Topic/CAsyncMonikerFile::GetBindInfo.md)|Aufgerufen durch die OLE\-Systembibliothek, um Informationen über den Typ der zu erstellenden Bindung anzufordern.|  
|[CAsyncMonikerFile::GetPriority](../Topic/CAsyncMonikerFile::GetPriority.md)|Aufgerufen durch die OLE\-Systembibliothek, um die Priorität der Bindung abzurufen.|  
|[CAsyncMonikerFile::OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md)|Aufgerufen, um Daten bereitzustellen, wie sie zum Client während asynchroner Bindevorgänge verfügbar ist.|  
|[CAsyncMonikerFile::OnLowResource](../Topic/CAsyncMonikerFile::OnLowResource.md)|Aufgerufen, wenn Ressourcen niedrig.|  
|[CAsyncMonikerFile::OnProgress](../Topic/CAsyncMonikerFile::OnProgress.md)|Aufgerufen, um Status auf dem Datendownloadingprozess anzugeben.|  
|[CAsyncMonikerFile::OnStartBinding](../Topic/CAsyncMonikerFile::OnStartBinding.md)|Wenn die Bindung aufgerufen, beginnen hohes ist.|  
|[CAsyncMonikerFile::OnStopBinding](../Topic/CAsyncMonikerFile::OnStopBinding.md)|Aufgerufen, wenn asynchrone Lesevorgang beendet wird.|  
  
## Hinweise  
 Ist von [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), das wiederum von [COleStreamFile](../../mfc/reference/colestreamfile-class.md) berechnet wird, verwendet die `CAsyncMonikerFile`[IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)\-Schnittstelle, um auf jeden Datenstream, einschließlich Ladendateien asynchron von einer URL asynchron zuzugreifen.  Die Dateien können datapath Eigenschaften von ActiveX\-Steuerelementen sein.  
  
 Asynchrone Moniker werden hauptsächlich in den internetaktivierten Anwendungen und in ActiveX\-Steuerelemente, eine reagierende Benutzeroberfläche während der Dateiübertragungen bereitzustellen verwendet.  Ein Paradebeispiel hierfür ist die Verwendung von [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md), asynchrone Eigenschaften für ActiveX\-Steuerelemente bereitzustellen.  Das `CDataPathProperty`\-Objekt ruft wiederholt einen Rückruf ab, um Verfügbarkeit von neuen Daten während eines längeren Eigenschaftaustauschprozesses anzugeben.  
  
 Weitere Informationen dazu, wie asynchrone Moniker und ActiveX\-Steuerelemente in Internetanwendungen, finden Sie die folgenden Elemente verwendet:  
  
-   [Internet\-erste Schritte: Asynchrone Moniker](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Internet\-erste Schritte: ActiveX\-Steuerelemente](../../mfc/activex-controls-on-the-internet.md)  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## Anforderungen  
 **Header:** afxole.h  
  
## Siehe auch  
 [CMonikerFile Class](../../mfc/reference/cmonikerfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMonikerFile Class](../../mfc/reference/cmonikerfile-class.md)   
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)   
 [Asynchronous Versus Synchronous Monikers](http://msdn.microsoft.com/library/windows/desktop/ms687193)
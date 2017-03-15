---
title: "IErrorRecordsImpl-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IErrorRecordsImpl"
  - "ATL.IErrorRecordsImpl"
  - "IErrorRecordsImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IErrorRecordsImpl-Klasse"
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IErrorRecordsImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die OLE DB\- [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx)\-Schnittstelle, fügt Datensätzen zu hinzu und ruft Datensätze von einem Datenmember \([m\_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)\) des Typs  **CAtlArray \<**`RecordClass`**\>** ausgelöst.  
  
## Syntax  
  
```  
template <  
   class T,   
   class RecordClass = ATLERRORINFO  
>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
#### Parameter  
 `T`  
 Eine Klasse wird von `IErrorRecordsImpl` abgeleitet.  
  
 `RecordClass`  
 Eine Klasse, die ein OLE DB\-Fehlerobjekt darstellt.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[GetErrorDescriptionString](../../data/oledb/ierrorrecordsimpl-geterrordescriptionstring.md)|Ruft die Fehlerbeschreibungszeichenfolge von einem Fehlerdatensatz ab.|  
|[GetErrorGUID](../../data/oledb/ierrorrecordsimpl-geterrorguid.md)|Ruft die GUID Fehler von einem Fehlerdatensatz ab.|  
|[GetErrorHelpContext](../../data/oledb/ierrorrecordsimpl-geterrorhelpcontext.md)|Ruft die Hilfekontext\-id von einem Fehlerdatensatz ab.|  
|[GetErrorHelpFile](../../data/oledb/ierrorrecordsimpl-geterrorhelpfile.md)|Ruft den vollständigen Pfadnamen der Hilfedatei von einem Fehlerdatensatz ab.|  
|[GetErrorSource](../../data/oledb/ierrorrecordsimpl-geterrorsource.md)|Ruft den Fehlerquellcode von einem Fehlerdatensatz ab.|  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[AddErrorRecord](../../data/oledb/ierrorrecordsimpl-adderrorrecord.md)|Fügt einem Datensatz dem OLE DB\-Fehlerobjekt hinzu.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Gibt grundlegenden Informationen zum Fehler, z den Rückgabecode und die anbieterspezifische Fehlernummer zurück.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Gibt einen Zeiger auf eine Schnittstelle auf einem benutzerdefinierten Fehlerobjekts zurück.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Gibt ein [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) von Schnittstellenzeigern auf dem angegebenen Datensatz zurück.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Gibt den Fehlerparametern zurück.|  
|[GetRecordCount](../Topic/CDaoRecordset::GetRecordCount.md)|Gibt die Anzahl von Datensätzen im OLE DB\-Datensatzobjekt zurück.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)|Ein Array Fehlerdatensätze.|  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)
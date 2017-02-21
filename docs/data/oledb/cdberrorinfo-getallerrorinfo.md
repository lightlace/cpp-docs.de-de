---
title: "CDBErrorInfo::GetAllErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDBErrorInfo.GetAllErrorInfo"
  - "CDBErrorInfo::GetAllErrorInfo"
  - "ATL::CDBErrorInfo::GetAllErrorInfo"
  - "GetAllErrorInfo"
  - "CDBErrorInfo.GetAllErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAllErrorInfo-Methode"
ms.assetid: 630049fa-d296-497a-bbf6-f5d3d71d271d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CDBErrorInfo::GetAllErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt alle Fehlertypinformationen zurück, die in einem Fehlerdatensatz enthalten sind.  
  
## Syntax  
  
```  
  
      HRESULT GetAllErrorInfo(  
   ULONG ulRecordNum,  
   LCID lcid,  
   BSTR* pbstrDescription,  
   BSTR* pbstrSource = NULL,  
   GUID* pguid = NULL,  
   DWORD* pdwHelpContext = NULL,  
   BSTR* pbstrHelpFile = NULL  
) const throw( );  
```  
  
#### Parameter  
 *ulRecordNum*  
 \[in\] die Basiszahl des Datensatzes, dass Fehlerinformationen zurückgibt.  
  
 `lcid`  
 \[in\] die Gebietsschema\-ID, sodass die Fehlerinformationen zurückgegeben werden können.  
  
 `pbstrDescription`  
 \[out\] Ein Zeiger auf eine Textbeschreibung des Fehlers oder NULL, wenn das Gebietsschema nicht unterstützt wird.  Siehe Hinweise.  
  
 `pbstrSource`  
 \[out\] Ein Zeiger auf eine Zeichenfolge, die den Namen der Komponente enthält, die den Fehler verursacht hat.  
  
 `pguid`  
 \[out\] Ein Zeiger auf die GUID der Schnittstelle, die den Fehler definiert hat.  
  
 *pdwHelpContext*  
 \[out\] Ein Zeiger auf die Hilfekontext\-id für den Fehler.  
  
 *pbstrHelpFile*  
 \[out\] Ein Zeiger auf eine Zeichenfolge, die den Pfad zur Hilfedatei enthält, die den Fehler beschreibt.  
  
## Rückgabewert  
 `S_OK` bei erfolgreicher Ausführung.  Siehe [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) in *der OLE DB\-Programmierreferenz* für andere Werte.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Hinweise  
 Der Ausgabewert von `pbstrDescription` wird intern erhalten, indem IErrorInfo::GetDescription aufruft, das den Wert festgelegt wird, um in NULL, wenn das Gebietsschema nicht unterstützt wird oder wenn die beiden folgenden Bedingungen erfüllt sind:  
  
1.  der Wert von `lcid` ist Englisch NOT US und  
  
2.  der Wert von `lcid` ist NOT gleich dem Wert, der von GetUserDefaultLCID zurückgegeben wird.  
  
## Siehe auch  
 [CDBErrorInfo\-Klasse](../../data/oledb/cdberrorinfo-class.md)
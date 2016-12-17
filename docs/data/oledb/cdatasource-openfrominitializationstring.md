---
title: "CDataSource::OpenFromInitializationString"
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
  - "CDataSource.OpenFromInitializationString"
  - "OpenFromInitializationString"
  - "CDataSource::OpenFromInitializationString"
  - "ATL::CDataSource::OpenFromInitializationString"
  - "ATL.CDataSource.OpenFromInitializationString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenFromInitializationString-Methode"
ms.assetid: 5ef1f1fd-92a9-4e1c-ad80-d3601b094b8c
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::OpenFromInitializationString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Öffnet eine Datenquelle, die durch die vom Benutzer bereitgestellte Initialisierungszeichenfolge angegeben wird.  
  
## Syntax  
  
```  
  
      HRESULT OpenFromInitializationString(   
   LPCOLESTR szInitializationString,   
   bool fPromptForInfo = false    
) throw( );  
```  
  
#### Parameter  
 *SzInitializationString*  
 \[in\] die Initialisierungszeichenfolge.  
  
 *fPromptForInfo*  
 \[in\] wenn dieses Argument auf **true** festgelegt ist, legt dann `OpenFromInitializationString` die Eigenschaft **DBPROP\_INIT\_PROMPT** auf **DBPROMPT\_COMPLETEREQUIRED** festgelegt, die angibt, dass der Benutzer aufgefordert wird, wenn weitere Informationen benötigt werden.  Dies ist für Situationen, in denen die Initialisierungszeichenfolge eine Datenbank angibt, die ein Kennwort erfordert, jedoch die Zeichenfolge enthält nicht das Kennwort.  Der Benutzer wird einem Kennwort \(oder anderen\) fehlenden Informationen beim Versuch, eine Verbindung zur Datenbank herzustellen aufgefordert.  
  
 Der Standardwert ist **false**, der angibt, dass der Benutzer nicht aufgefordert wird \(von **DBPROP\_INIT\_PROMPT** von **DBPROMPT\_NOPROMPT**\).  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Diese Methode startet ein Datenquellenobjekt mithilfe der in oledb32.dll Dienstkomponenten; Diese DLL enthält die Implementierung von Dienst\-Komponentenfunktionen wie Ressourcen\-Pooling, automatischer Transaktions\-Eintragung, u. a.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataSource\-Klasse](../../data/oledb/cdatasource-class.md)
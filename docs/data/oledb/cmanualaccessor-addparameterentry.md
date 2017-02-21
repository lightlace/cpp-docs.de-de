---
title: "CManualAccessor::AddParameterEntry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CManualAccessor::AddParameterEntry"
  - "ATL.CManualAccessor.AddParameterEntry"
  - "CManualAccessor.AddParameterEntry"
  - "AddParameterEntry"
  - "ATL::CManualAccessor::AddParameterEntry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddParameterEntry-Methode"
ms.assetid: 9048b164-052b-41b1-a861-227fc529e0b5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CManualAccessor::AddParameterEntry
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt einem Parametereintrag den Parametereintragsstrukturen hinzu.  
  
## Syntax  
  
```  
  
      void AddParameterEntry(  
   DBORDINAL nOrdinal,  
   DBTYPE wType,  
   DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL,  
   DBPARAMIO eParamIO = DBPARAMIO_INPUT   
) throw ( );  
```  
  
#### Parameter  
 Siehe [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in der *OLE* DB\-Programmierreferenz.  
  
 `nOrdinal`  
 \[in\] einen Parameterwert.  
  
 `wType`  
 \[in\] Datentyp.  
  
 `nColumnSize`  
 \[in\] Spaltengröße in Bytes.  
  
 `pData`  
 \[in\] Ein Zeiger auf die Daten anderer Spalten gespeichert im Puffer.  
  
 `pLength`  
 \[in\] Ein Zeiger auf die Feldlänge, nach Bedarf.  
  
 `pStatus`  
 \[in\] Ein Zeiger auf den Spaltenstatus gebunden werden Variablen, nach Bedarf.  
  
 *eParamIO*  
 \[in\] gibt an, ob der Parameter, mit dem sich die Bindung zugeordnet ist, einer Eingabe, eine Eingabe\/Ausgabe oder Ausgabeparameter handelt.  
  
## Hinweise  
 Um diese Funktion verwenden, müssen Sie zuerst [CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CManualAccessor\-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)   
 [DBViewer\-Beispiel](../../top/visual-cpp-samples.md)
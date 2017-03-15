---
title: "ICommandImpl::CreateRowset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandImpl::CreateRowset"
  - "ICommandImpl.CreateRowset"
  - "CreateRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateRowset-Methode"
ms.assetid: a0890009-205e-4970-879f-01ed9d6a93f1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ICommandImpl::CreateRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird von [Ausführen](../../data/oledb/icommandimpl-execute.md), um ein einzelnes Rowset zu erstellen.  
  
## Syntax  
  
```  
  
      template <class   
      RowsetClass  
      >  
HRESULT CreateRowset(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj   
);  
```  
  
#### Parameter  
 `RowsetClass`  
 Ein Vorlagenklassenmember, der die Rowsetklasse des Benutzers darstellt.  generiert gewöhnlich durch den Assistenten.  
  
 `pUnkOuter`  
 \[in\] Ein Zeiger auf die **IUnknown** steuernden Schnittstelle, wenn das Rowset als Teil eines Aggregats erstellt wird; Andernfalls befindet es ungültig.  
  
 `riid`  
 \[in\] entspricht `riid` in `ICommand::Execute`.  
  
 `pParams`  
 \[in\/out\] entspricht `pParams` in `ICommand::Execute`.  
  
 `pcRowsAffected`  
 Entspricht in `pcRowsAffected` in `ICommand::Execute`.  
  
 `ppRowset`  
 \[in\/out\] entspricht `ppRowset` in `ICommand::Execute`.  
  
 `pRowsetObj`  
 \[out\] Ein Zeiger auf ein Rowsetobjekt.  In der Regel wird dieser Parameter nicht verwendet, aber er kann verwendet werden, wenn mehr Arbeiten auf das Rowset ausführen müssen, bevor sie an ein COM\-Objekt übergeben.  Die Lebensdauer von `pRowsetObj` wird von `ppRowset` gebunden.  
  
## Rückgabewert  
 Ein Standard\- `HRESULT`\-Wert.  Siehe `ICommand::Execute` für eine Liste von typischen Werten.  
  
## Hinweise  
 Um mehr als ein Rowset zu erstellen, oder eigene Bedingungen zum Erstellen verschiedener Rowsets bereitzustellen, platzieren Sie unterschiedliche Aufrufe zu `CreateRowset` aus **Ausführen**.  
  
 Siehe [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) in *der OLE DB\-Programmierreferenz.*  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [ICommandImpl\-Klasse](../../data/oledb/icommandimpl-class.md)
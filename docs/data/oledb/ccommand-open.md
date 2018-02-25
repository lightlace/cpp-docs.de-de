---
title: 'CCommand:: Open | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: 4c9b8f31-faf3-452d-9a29-3d3e5f54d6f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bf4d30382224cd1fe85d12623acdcb90b0dee1bd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ccommandopen"></a>CCommand::Open
Führt ein, und bindet optional den Befehl.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCWSTR wszCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(const CSession& session,  
   LPCSTR szCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(const CSession& session,  
   INT szCommand = NULL,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `session`  
 [in] Die Sitzung, in dem den Befehl ausgeführt werden soll.  
  
 `wszCommand`  
 [in] Der Befehl ausgeführt wird, werden als Unicode-Zeichenfolge übergeben. Kann **NULL** Verwendung `CAccessor`, in diesem Fall der Befehl aus der an übergebene Wert abgerufen wird die [DEFINE_COMMAND](../../data/oledb/define-command.md) Makro. Finden Sie unter [ICommand:: Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) in der *OLE DB Programmer's Reference* Details.  
  
 `szCommand`  
 [in] Identisch mit `wszCommand` außer dass dieser Parameter eine Befehlszeichenfolge ANSI verwendet. Der vierte diese Methode kann einen NULL-Wert handeln. Finden Sie unter "Hinweise" weiter unten in diesem Thema Informationen ein.  
  
 *pPropSet*  
 [in] Ein Zeiger auf ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) Strukturen, die Eigenschaften und Werten festgelegt werden. Finden Sie unter [Eigenschaftensätze und Eigenschaftengruppen](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in der *OLE DB Programmer's Reference* im Windows SDK.  
  
 `pRowsAffected`  
 [in/Out] Ein Zeiger auf Speicher, in dem die Anzahl der von einem Befehl betroffenen Zeilen zurückgegeben wird. Wenn  *\*pRowsAffected* ist **NULL**, keine Zeilenanzahl zurückgegeben wird. Andernfalls **öffnen** legt *`pRowsAffected` entsprechend der folgenden Bedingungen:  
  
|If|Then|  
|--------|----------|  
|Die **cParamSets** Element des `pParams` ist größer als 1|*`pRowsAffected` Stellt die Gesamtanzahl der Zeilen, die alle von der bei der Ausführung angegebenen Parametersätzen betroffen.|  
|Die Anzahl der betroffenen Zeilen ist nicht verfügbar|*`pRowsAffected` wird auf-1 festgelegt.|  
|Der Befehl nicht aktualisiert, löschen oder Einfügen von Zeilen|*`pRowsAffected` ist nicht definiert.|  
  
 `guidCommand`  
 [in] Eine GUID, die Syntax und die allgemeinen Regeln für den zu verwendenden Anbieter angibt, bei der Analyse des Befehlstexts. Finden Sie unter [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) und [ICommandText:: SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx) in der *OLE DB Programmer's Reference* Details.  
  
 `bBind`  
 [in] Gibt an, ob den Befehl automatisch zu binden, nach der gerade ausgeführt wird. Die Standardeinstellung ist **"true"**, die bewirkt, dass der Befehl automatisch gebunden werden. Festlegen von `bBind` auf **"false"** wird verhindert, dass die automatische Bindung des Befehls, sodass manuell gebunden werden kann. (Manuelle Bindung ist von besonderem Interesse für OLAP-Benutzer).  
  
 `ulPropSets`  
 [in] Die Anzahl der [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) Strukturen zu übergeben, der *DBPROPSET* Argument.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die ersten drei Formen von **öffnen** schalten Sie eine Sitzung, einen Befehl erstellen und führen Sie den Befehl, Parameter nach Bedarf binden.  
  
 Die erste Form der **öffnen** eine Zeichenfolge mit Unicode-Befehl akzeptiert und hat keinen Standardwert.  
  
 Die zweite Form der **öffnen** nimmt eine Befehlszeichenfolge ANSI und kein Standardwert (für Abwärtskompatibilität mit vorhandenen ANSI-Anwendungen bereitgestellt).  
  
 Die dritte Form des **öffnen** die Befehlszeichenfolge NULL, weil Typ aufweisen können `int` hat den Standardwert NULL. Es dient für den Aufruf von `Open(session, NULL);` oder `Open(session);` da NULL Typ `int`. Diese Version erfordert und bestätigt, die die `int` Parameter NULL sein.  
  
 Die vierte Form von **öffnen** Wenn Sie bereits einen Befehl erstellt haben und Sie ein einzelnes ausführen möchten [vorbereiten](../../data/oledb/ccommand-prepare.md) und mehrere Ausführungen.  
  
> [!NOTE]
>  **Open** Aufrufe **Execute**, die wiederum ruft `GetNextResult`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CCommand-Klasse](../../data/oledb/ccommand-class.md)
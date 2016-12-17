---
title: "CCommand::Open"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL.CCommand.Open"
  - "ATL::CCommand::Open"
  - "CCommand.Open"
  - "CCommand::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open-Methode"
ms.assetid: 4c9b8f31-faf3-452d-9a29-3d3e5f54d6f8
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt aus und bindet optional den Befehl.  
  
## Syntax  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   INT szCommand = NULL,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### Parameter  
 `session`  
 \[in\] in der die Sitzung, um den Befehl ausführen.  
  
 `wszCommand`  
 \[in\] der Befehl auszuführen, übergeben als Unicode\-Zeichenfolge.  Kann **NULL**, wenn `CAccessor` verwendet wird, wird der Befehl im Wert abgerufen wird, der zum [DEFINE\_COMMAND](../../data/oledb/define-command.md)\-Makro übergeben wird.  Siehe [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) in *der OLE DB\-Programmierreferenz* für Details.  
  
 `szCommand`  
 \[in\] nimmt `wszCommand` identisch außer dass dieser Parameter eine ANSI\-Befehlszeichenfolge.  Das vierte Formular dieser Methode kann einen NULL\-Wert akzeptiert.  Siehe "Hinweise" weiter unten in diesem Thema für Details.  
  
 *pPropSet*  
 \[in\] strukturiert Ein Zeiger auf ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) das Einbinden von festgelegt werden Eigenschaften und Werte.  Siehe [Eigenschaftensätze und Eigenschaftengruppen](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in *der OLE DB\-Programmierreferenz* in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pRowsAffected`  
 \[in\/out\] Ein Zeiger auf den Speicher, in dem die Anzahl von Zeilen, die über einen Befehl gelten, zurückgegeben wird.  Wenn es ist keine **NULL**, Zeilenanzahl zurückgegeben wird *\*pRowsAffected*.  Andernfalls legt **Öffnen** \*`pRowsAffected` entsprechend den folgenden Bedingungen fest:  
  
|If|Then|  
|--------|----------|  
|Das **cParamSets**\-Element von `pParams` ist größer als 1|\*`pRowsAffected` stellt die Gesamtzahl der Zeilen dar, die von allen Parametersätze beeinflusst werden, die bei der Ausführung angegeben werden.|  
|Die Anzahl der betroffenen Zeilen ist nicht verfügbar|\* \-`pRowsAffected` auf 1 festgelegt.|  
|Der Befehl nicht aktualisiert oder löscht, fügt darin Zeilen ein|\*`pRowsAffected` nicht definiert ist.|  
  
 `guidCommand`  
 \[in\] Eine GUID, die der Syntax und die allgemeinen Regeln angibt, den der Anbieter verwendet, wenn es den Befehlstext analysiert.  Siehe [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) und [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx) in der *OLE* DB\-Programmierreferenz für Details.  
  
 `bBind`  
 \[in\] gibt an, ob der Befehl automatisch gebunden, nach ausgeführt werden.  Der Standardwert ist **true**, der den Befehl auslöst, automatisch gebunden werden.  Einstellung `bBind` von **false** verhindert die automatische Bindung des Befehls, damit Sie manuell binden können. \(Das manuelle Bindung ist von besonderem Interesse für OLAP\-Benutzern.\)  
  
 `ulPropSets`  
 \[in\] hat die Anzahl der [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)\-Strukturen in das *pPropSet*\-Argument.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Die ersten drei Formen von **Öffnen** werden eine Sitzung, einen Befehl erstellen und führen Sie den Befehl aus und ggf. binden alle Parameter.  
  
 Das erste Format von **Öffnen** wird eine Unicode\-Befehlszeichenfolge und besitzt keinen Standardwert.  
  
 Das zweite Format von **Öffnen** wird eine ANSI\-Befehlszeichenfolge und keinen Standardwert \(bereitgestellt für Abwärtskompatibilität mit vorhandenen ANSI\-Anwendungen\).  
  
 Das dritte Format von **Öffnen** kann der Befehlszeichenfolge, um, aufgrund des Typs `int` mit einem Standardwert NULL NULL sein.  Es wird für das Aufrufen von `Open(session, NULL);` oder `Open(session);` bereitgestellt, da NULL vom Typ `int` ist.  Diese Version erfordert und erläutert, dass der Parameter `int` NULL ist.  
  
 Verwenden Sie das vierte Format von **Öffnen**, wenn Sie bereits einen Befehl erstellt und Sie einzelnen [Vorbereiten vor](../../data/oledb/ccommand-prepare.md) und mehrere Testläufe ausführen möchten.  
  
> [!NOTE]
>  **Öffnen** ruft **Ausführen** auf, das wiederum `GetNextResult` aufgerufen wird.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CCommand\-Klasse](../../data/oledb/ccommand-class.md)
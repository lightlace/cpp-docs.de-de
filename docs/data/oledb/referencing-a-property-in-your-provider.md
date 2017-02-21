---
title: "Verweisen auf eine Eigenschaft im Anbieter | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Anbieter, Eigenschaften"
  - "Referenzen, Zu Eigenschaften in Anbietern"
  - "Verweisen auf Eigenschaften in Anbietern"
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verweisen auf eine Eigenschaft im Anbieter
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Suchen Sie die Eigenschaftengruppe und Eigenschaften\-ID der gewünschten Eigenschaft.  Weitere Informationen finden Sie in der *OLE DB Programmer's Reference* unter [OLE DB Properties](https://msdn.microsoft.com/en-us/library/ms722734.aspx) \(nur auf Englisch verfügbar\).  
  
 Im folgenden Beispiel wird davon ausgegangen, dass Sie eine Eigenschaft aus dem Rowset ermitteln möchten.  Der Code zur Verwendung der Sitzung oder des Befehls ist zwar ähnlich, verwendet jedoch eine andere Schnittstelle.  
  
 Erstellen Sie ein [CDBPropSet](../../data/oledb/cdbpropset-class.md)\-Objekt, und verwenden Sie die Eigenschaftengruppe als Parameter für den Konstruktor.  Beispiel:  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 Rufen Sie [AddProperty](../../data/oledb/cdbpropset-addproperty.md) auf, und übergeben Sie die Eigenschaften\-ID und einen Wert, der der Eigenschaft zugeordnet werden soll.  Der Werttyp richtet sich nach der verwendeten Eigenschaft.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IRowsetChange, true);  
propset.AddProperty(DBPROP_UPDATABILITY,  
DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 Rufen Sie **GetProperties** mithilfe der `IRowset`\-Schnittstelle auf.  Übergeben Sie das Eigenschaftenset als Parameter.  Der fertige Code sieht wie folgt aus:  
  
```  
CAgentRowset<CMyProviderCommand>* pRowset = (CAgentRowset<CMyProviderCommand>*) pThis;  
  
CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
DBPROPIDSET set;  
set.AddPropertyID(DBPROP_BOOKMARKS);  
DBPROPSET* pPropSet = NULL;  
ULONG ulPropSet = 0;  
HRESULT hr;  
  
if (spRowsetProps)  
   hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
if (pPropSet)  
{  
   CComVariant var = pPropSet->rgProperties[0].vValue;  
   CoTaskMemFree(pPropSet->rgProperties);  
   CoTaskMemFree(pPropSet);  
  
   if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
   {  
      ...  // Use property here  
   }  
}  
```  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)
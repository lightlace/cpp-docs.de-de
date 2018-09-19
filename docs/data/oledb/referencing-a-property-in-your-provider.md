---
title: Verweisen auf eine Eigenschaft im Anbieter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f6730746cbb3da08e52b5a4d9936aa48a8484886
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052557"
---
# <a name="referencing-a-property-in-your-provider"></a>Verweisen auf eine Eigenschaft im Anbieter

Finden Sie die Eigenschaftengruppe und die Eigenschafts-ID für die gewünschte Eigenschaft an. Weitere Informationen finden Sie unter [OLE DB-Eigenschaften](/previous-versions/windows/desktop/ms722734\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.  
  
Im folgende Beispiel wird davon ausgegangen, dass Sie versuchen, eine Eigenschaft aus dem Rowset abzurufen. Der Code für die Verwendung der Sitzung oder einen Befehl ähnelt, verwendet jedoch eine andere Schnittstelle.  
  
Erstellen Sie eine [CDBPropSet](../../data/oledb/cdbpropset-class.md) -Objekt unter Verwendung der Gruppe der Eigenschaften als Parameter an den Konstruktor. Zum Beispiel:  
  
```cpp  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
Rufen Sie [AddProperty](../../data/oledb/cdbpropset-addproperty.md), übergeben sie die Eigenschafts-ID und einen Wert der Eigenschaft zugewiesen werden. Der Typ des Werts hängt von der Eigenschaft, die Sie verwenden.  
  
```cpp  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IRowsetChange, true);  

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
Verwenden der `IRowset` Schnittstelle aufrufen, `GetProperties`. Übergeben Sie die Eigenschaft, die als Parameter festgelegt. Hier ist der endgültige Code ein:  
  
```cpp  
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
  
## <a name="see-also"></a>Siehe auch  

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)
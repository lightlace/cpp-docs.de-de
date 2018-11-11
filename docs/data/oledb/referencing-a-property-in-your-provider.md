---
title: Verweisen auf eine Eigenschaft im Anbieter
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
ms.openlocfilehash: d6a750d3c2c6c409a1b7d3ce40ef13566b522cff
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265164"
---
# <a name="referencing-a-property-in-your-provider"></a>Verweisen auf eine Eigenschaft im Anbieter

Finden Sie die Eigenschaftengruppe und die Eigenschafts-ID für die gewünschte Eigenschaft an. Weitere Informationen finden Sie unter [OLE DB-Eigenschaften](/previous-versions/windows/desktop/ms722734) in die **OLE DB-Programmierreferenz**.

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
CAgentRowset<CCustomCommand>* pRowset = (CAgentRowset<CCustomCommand>*) pThis;

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
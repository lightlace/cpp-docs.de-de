---
title: Abrufen von Daten
ms.date: 10/19/2018
helpviewer_keywords:
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
ms.openlocfilehash: 441f036d1677806e81bc419ec6a45e810e63a34f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409058"
---
# <a name="fetching-data"></a>Abrufen von Daten

Nachdem Sie die Datenquelle, Sitzung und Rowset-Objekte öffnen, können Sie Daten abrufen. Je nach Art des Accessors, die Sie verwenden, müssen Sie Spalten binden.

## <a name="to-fetch-data"></a>Zum Abrufen von Daten

1. Öffnen Sie das Rowset mit der entsprechenden **öffnen** Befehl.

1. Bei Verwendung von `CManualAccessor`, binden Sie die Ausgabespalten aus, wenn Sie dies nicht bereits getan haben. Das folgende Beispiel stammt aus dem [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) Beispiel. Rufen Sie zum Binden der Spalten, `GetColumnInfo`, und erstellen Sie einen Accessor mit den Bindungen, wie im folgenden Beispiel gezeigt:

    ```cpp
    // From the DBViewer Sample CDBTreeView::OnQueryEdit
    // Get the column information
    ULONG ulColumns       = 0;
    DBCOLUMNINFO* pColumnInfo  = NULL;
    LPOLESTR pStrings      = NULL;
    if (rs.GetColumnInfo(&ulColumns, &pColumnInfo, &pStrings) != S_OK)
        ThrowMyOLEDBException(rs.m_pRowset, IID_IColumnsInfo);
    struct MYBIND* pBind = new MYBIND[ulColumns];
    rs.CreateAccessor(ulColumns, &pBind[0], sizeof(MYBIND)*ulColumns);
    for (ULONG l=0; l<ulColumns; l++)
    rs.AddBindEntry(l+1, DBTYPE_STR, sizeof(TCHAR)*40, &pBind[l].szValue, NULL, &pBind[l].dwStatus);
    rs.Bind();
    ```

1. Schreiben einer **während** Schleife zum Abrufen der Daten. Rufen Sie in der Schleife `MoveNext` fahren fort, um den Cursor und den Rückgabewert mit S_OK, testen, wie im folgenden Beispiel gezeigt:

    ```cpp
    while (rs.MoveNext() == S_OK)
    {
        // Add code to fetch data here
        // If you are not using an auto accessor, call rs.GetData()
    }
    ```

1. In der **während** Schleife können Sie die Daten gemäß Ihrer Accessortyp abrufen.

   - Bei Verwendung der [CAccessor](../../data/oledb/caccessor-class.md) -Klasse, müssen Sie einen Benutzerdatensatz, der Datenelemente enthält. Sie können Ihre Daten mit diesen Datenmember zugreifen, wie im folgenden Beispiel gezeigt:

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members directly. In this case, m_nFooID
            // is declared in a user record that derives from
            // CAccessor
            wsprintf_s("%d", rs.m_nFooID);
        }
        ```

   - Bei Verwendung der `CDynamicAccessor` oder `CDynamicParameterAccessor` -Klasse, können Sie Daten abrufen, die Zugriff auf Funktionen mit `GetValue` und `GetColumn`, wie im folgenden Beispiel gezeigt. Wenn Sie den Typ der Daten ermitteln möchten, Sie verwenden, verwenden Sie `GetType`.

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the dynamic accessor functions to retrieve your data.

            ULONG ulColumns = rs.GetColumnCount();
            for (ULONG i=0; i<ulColumns; i++)
            {
                rs.GetValue(i);
            }
        }
        ```

   - Bei Verwendung von `CManualAccessor`, müssen Sie Ihre eigenen Datenmember angeben, sie selbst binden und direkt auf diese zugegriffen, wie im folgenden Beispiel gezeigt:

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members you specified in the calls to
            // AddBindEntry.

            wsprintf_s("%s", szFoo);
        }
        ```

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)

---
title: Hinzufügen einer Schnittstelle zum Anbieter
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
ms.openlocfilehash: 5659078641439744c1f68cbb399c19b9b58bd0bb
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265138"
---
# <a name="adding-an-interface-to-your-provider"></a>Hinzufügen einer Schnittstelle zum Anbieter

Bestimmen, welches Objekt Sie die Schnittstelle zum hinzufügen möchten (Data Source, Rowset, Befehl oder Sitzung Objekte in der Regel erstellt, durch die **OLE DB-Anbieter-Assistent**). Es ist möglich, dass das Objekt, dem Sie die Schnittstelle zum hinzufügen müssen, einer ist, die Ihrem Anbieter derzeit nicht unterstützt wird. In diesem Fall führen Sie die **ATL-OLE DB-Anbieter-Assistenten** zum Erstellen des Objekts. Mit der rechten Maustaste in des Projekts im **Klassenansicht**, klicken Sie auf **hinzufügen** > **neues Element** wählen Sie im Menü **installiert**  >  **Visual C++** > **ATL**, und klicken Sie dann auf **ATL-OLE DB-Anbieter**. Sie möchten den Code für die Benutzeroberfläche in einem separaten Verzeichnis abgelegt und kopieren Sie die Dateien zu Ihrem Anbieterprojekt.

Wenn Sie eine neue Klasse zum unterstützen der Schnittstelle erstellt haben, stellen Sie das Objekt, das von dieser Klasse erben. Beispielsweise können Sie die Klasse hinzufügen `IRowsetIndexImpl` in ein Rowsetobjekt:

```cpp
template <class Creator>
class CCustomRowset :
    public CRowsetImpl< CCustomRowset<Creator>, CCustomWindowsFile, Creator>,
    public IRowsetIndexImpl< ... >
```

Hinzuzufügen Sie die Schnittstelle zu COM_MAP, in dem Objekt, das mit dem COM_INTERFACE_ENTRY-Makro. Wenn keine Zuordnung vorhanden ist, erstellen. Zum Beispiel:

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
END_COM_MAP()
```

Für das Rowsetobjekt die Kette der Zuordnung des übergeordneten Objekts, sodass das Objekt in der übergeordneten Klasse delegieren kann. Fügen Sie in diesem Beispiel der Zuordnung-Makro hinzu:

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)
END_COM_MAP()
```

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)
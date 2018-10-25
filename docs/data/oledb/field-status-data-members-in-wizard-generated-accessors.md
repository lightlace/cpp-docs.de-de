---
title: Feld-Datenmember in vom Assistenten generierten Zugriffsmethoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/24/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: def38b763094c78e7e03ad1f0197c1df49fecdaf
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079999"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>Feldstatus-Datenmember in vom Assistenten generierten Zugriffsmethoden

Bei Verwendung der **ATL-OLE DB-Consumer-Assistenten** um einen Consumer erstellen, generiert der Assistent einen Datenmember in die Benutzerdatensatz-Klasse für jedes Feld, das Sie in der spaltenzuordnung angeben. Jedes Datenelement ist vom Typ `DWORD` und enthält einen Statuswert, der dem jeweiligen Feld entspricht.

Z. B. für einen Datenmember *M_OwnerID*, generiert der Assistent einen zusätzlichen Datenmember für Feldstatus (*DwOwnerIDStatus*) und eine andere für die Feldlänge (*DwOwnerIDLength*). Es generiert außerdem eine spaltenzuordnung zu COLUMN_ENTRY_LENGTH_STATUS-Einträgen.

Dies wird im folgenden Code gezeigt:

```cpp
class CAuthorsAccessor
{
public:
   LONG m_AuID;
   TCHAR m_Author[53];
   LONG m_YearBorn;

   DBSTATUS m_dwAuIDStatus;
   DBSTATUS m_dwAuthorStatus;
   DBSTATUS m_dwYearBornStatus;

   DBLENGTH m_dwAuIDLength;
   DBLENGTH m_dwAuthorLength;
   DBLENGTH m_dwYearBornLength;

    DEFINE_COMMAND_EX(CAuthorsAccessor, L" \
    SELECT \
        AuID, \
        Author, \
        YearBorn \
        FROM dbo.Authors")

    BEGIN_COLUMN_MAP(CAuthorsAccessor)
       COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, dwAuIDLength, dwAuIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, dwAuthorLength, dwAuthorStatus)
       COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, dwYearBornLength, dwYearBornStatus)
    END_COLUMN_MAP()
...
```

> [!NOTE]
> Wenn Sie die Benutzerdatensatz-klasse ändern oder einen eigenen Consumer erstellen, müssen die Datenvariablen in der Reihenfolge vor den Status- und Längenvariablen liegen.

Sie können die Status-Werte verwenden, zu Debugzwecken. Wenn vom Code generiert die **ATL-OLE DB-Consumer-Assistenten** Kompilierungsfehler generiert z. B. DB_S_ERRORSOCCURRED oder DB_E_ERRORSOCCURRED, Sie sollten ein erster Blick auf die aktuellen Werte von der Feldstatus-Datenmember. Die betreffenden Spalten entsprechen mit Werten ungleich NULL.

Sie können auch die Status-Werte verwenden, um einen NULL-Wert für ein bestimmtes Feld festzulegen. Auf diese Weise können Sie in Fällen, in denen Sie einen Feldwert als NULL statt 0 (null) zu unterscheiden möchten. Es liegt an Ihnen zu entscheiden, ob NULL ein gültiger Wert oder ein spezieller Wert, und entscheiden, wie Sie Ihre Anwendung behandelt werden soll. OLE DB definiert DBSTATUS_S_ISNULL als die richtige Methode zur Angabe der eines generischen NULL-Werts. Wenn der Consumer Daten liest, und der Wert null ist, wird das Statusfeld auf DBSTATUS_S_ISNULL festgelegt. Wenn der Consumer einen NULL-Wert festgelegt möchte, setzt der Consumer den Statuswert auf DBSTATUS_S_ISNULL vor dem Aufruf des Anbieters an.

Öffnen Sie als Nächstes "OleDb.h", und suchen Sie nach DBSTATUSENUM. Sie können dann der numerische Wert des Status ungleich NULL für Enumerationswerte DBSTATUSENUM übereinstimmen. Ist der Enumerationsname nicht ausreichen, um Sie zu informieren, was falsch ist, finden Sie unter den **Status** Thema in der **Datenwerte binden** Teil der [OLE DB Programmer's Guide](/previous-versions/windows/desktop/ms713643). Dieses Thema enthält Tabellen mit dem Status-Werte, die beim Abrufen oder Festlegen der Daten verwendet. Informationen zu Längenwerten finden Sie unter den **Länge** Thema im gleichen Abschnitt.

## <a name="retrieving-the-length-or-status-of-a-column"></a>Abrufen der Länge oder der Status einer Spalte

Sie können die Länge einer Spalte variabler Länge oder der Status einer Spalte (z. B. DBSTATUS_S_ISNULL, zu überprüfen) abrufen:

- Verwenden Sie zum Abrufen der Länge der COLUMN_ENTRY_LENGTH-Makro ein.

- Um den Status zu erhalten, verwenden Sie die COLUMN_ENTRY_STATUS-Marko.

- Um beides zu erhalten, verwenden Sie COLUMN_ENTRY_LENGTH_STATUS wie gezeigt:

    ```cpp
    class CProducts
    {
    public:
       char      szName[40];
       long      nNameLength;
       DBSTATUS   nNameStatus;

    BEGIN_COLUMN_MAP(CProducts)
    // Bind the column to CProducts.m_ProductName.
    // nOrdinal is zero-based, so the column number of m_ProductName is 1.
       COLUMN_ENTRY_LENGTH_STATUS(1, szName, nNameLength, nNameStatus)
    END_COLUMN_MAP()
    };
    ```

- Klicken Sie dann Zugriff auf die Länge bzw. den Status wie gezeigt:

    ```cpp
    CTable<CAccessor<CProducts >> product;
    CSession session;

    product.Open(session, "Product");

    while (product.MoveNext() == S_OK)
    {
       // Check the product name isn't NULL before tracing it
       if (product.nNameStatus == DBSTATUS_S_OK)
          ATLTRACE("%s is %d characters\n", product.szName, product.nNameLength);
    }
    ```

Bei Verwendung von `CDynamicAccessor`, die Länge und den Status automatisch für Sie gebunden sind. Verwenden Sie zum Abrufen der Werte für Länge und der Status der `GetLength` und `GetStatus` Memberfunktionen.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)
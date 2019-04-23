---
title: 'Datensatzfeldaustausch: Arbeiten mit Assistenten-Code'
ms.date: 11/04/2016
helpviewer_keywords:
- DoFieldExchange method, overriding
- Unicode, with database classes
- field data members, declaring
- RFX (ODBC), wizard code
- RFX (ODBC), implementing
- field data members
- ODBC, RFX
- m_nParams data member, initializing
- m_nFields data member
- m_nParams data member
- overriding, DoFieldExchange
- m_nFields data member, initializing
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
ms.openlocfilehash: 82f0d946cac3429150250e2df5d1bfd674ec30ee
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041292"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>Datensatzfeldaustausch: Arbeiten mit Assistenten-Code

In diesem Thema wird erläutert, den Code, den MFS-Anwendungsassistenten und **Klasse hinzufügen** (siehe [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) zur Unterstützung von RFX und wie Sie möchten möglicherweise ändern, Code zu schreiben.

> [!NOTE]
>  Dieses Thema gilt für Klassen, die von `CRecordset` in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, wird die Massen-Datensatzfeldaustausch (Bulk-RFX) implementiert. Bulk RFX ähnelt RFX. Informationen zu den Unterschieden finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Bei der Erstellung einer Recordset-Klasse mit dem MFC-Anwendungs-Assistenten oder **Klasse hinzufügen**, schreibt der Assistent die folgenden RFX-bezogene Elemente basierend auf der Datenquelle, Tabelle und Auswahl von Spalten, die Sie im Assistenten vornehmen:

- Deklarationen von den Recordset-Felddatenmembern in die Recordset-Klasse

- Eine Überschreibung der `CRecordset::DoFieldExchange`

- Initialisierung des Recordset-Felddatenmember in den Konstruktor des Recordset-Klasse

##  <a name="_core_the_field_data_member_declarations"></a> Feld Datenmemberdeklarationen

Die Assistenten schreiben Sie eine Deklaration des Recordset-Klasse in eine .h-Datei, die ähnlich wie die folgende Klasse `CSections`:

```cpp
class CSections : public CRecordset
{
public:
   CSections(CDatabase* pDatabase = NULL);
   DECLARE_DYNAMIC(CSections)

// Field/Param Data
   CString   m_strCourseID;
   CString   m_strInstructorID;
   CString   m_strRoomNo;
   CString   m_strSchedule;
   CString   m_strSectionNo;

// Overrides
   // Wizard generated virtual function overrides
   protected:
   virtual CString GetDefaultConnect();  // Default connection string
   virtual CString GetDefaultSQL();      // Default SQL for Recordset
   virtual void DoFieldExchange(CFieldExchange* pFX);  // RFX support

// Implementation
#ifdef _DEBUG
   virtual void AssertValid() const;
   virtual void Dump(CDumpContext& dc) const;
#endif

};
```

Wenn Sie Parameterdatenmember oder neue Felddatenmember, die Sie selbst eine Bindung hinzufügen, fügen sie nach denjenigen vom Assistenten generierte hinzu.

Beachten Sie, die der Assistent überschreibt die `DoFieldExchange` Memberfunktion der Klasse `CRecordset`.

##  <a name="_core_the_dofieldexchange_override"></a> DoFieldExchange außer Kraft setzen

[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) ist das Herzstück von RFX. Das Framework ruft `DoFieldExchange` jederzeit Daten in der Datenquelle entweder aus der Datenquelle zum Recordset oder vom Recordset zu verschieben muss. `DoFieldExchange` unterstützt das Abrufen von Informationen zu Feld auch Datenelemente über die [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty) und [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull) Memberfunktionen.

Die folgenden `DoFieldExchange` außer Kraft setzen, ist für die `CSections` Klasse. Der Assistent fügt die Funktion in der CPP-Datei für die Recordset-Klasse.

```cpp
void CSections::DoFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   RFX_Text(pFX, "CourseID", m_strCourseID);
   RFX_Text(pFX, "InstructorID", m_strInstructorID);
   RFX_Text(pFX, "RoomNo", m_strRoomNo);
   RFX_Text(pFX, "Schedule", m_strSchedule);
   RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

Beachten Sie, dass die folgenden Funktionen der Funktion:

- In diesem Abschnitt der Funktion wird die feldzuordnung aufgerufen.

- Ein Aufruf von `CFieldExchange::SetFieldType`, über die `pFX` Zeiger. Dieser Aufruf gibt an, dass alle RFX-Funktion am Ende der aufgerufenen `DoFieldExchange` oder beim nächsten Aufruf von `SetFieldType` Ausgabespalten sind. Weitere Informationen finden Sie unter [CFieldExchange::](../../mfc/reference/cfieldexchange-class.md#setfieldtype).

- Mehrere Aufrufe der `RFX_Text` globale Funktion – eine pro Felddatenmember (alle sind `CString` Variablen im Beispiel). Diese Aufrufe geben Sie die Beziehung zwischen den Namen einer Spalte in der Datenquelle und ein Felddatenmember. Die RFX-Funktionen ist die tatsächliche Datenübertragung. Die Klassenbibliothek stellt RFX-Funktionen für die allgemeine Datentypen. Weitere Informationen über RFX-Funktionen finden Sie unter [Record Field Exchange: Verwenden der RFX-Funktionen](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).

    > [!NOTE]
    >  Die Reihenfolge der Spalten im Resultset muss die Reihenfolge der Aufrufe der RFX-Funktionen in entsprechen `DoFieldExchange`.

- Die `pFX` Zeiger auf eine [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) -Objekt, das das Framework beim Aufruf übergeben wird `DoFieldExchange`. Die `CFieldExchange` Objekt gibt an, den Vorgang, `DoFieldExchange` ausführen, die Richtung der Übertragung und anderer Kontextinformationen.

##  <a name="_core_the_recordset_constructor"></a> Recordset-Konstruktor

Der recordsetkonstruktor, den die Assistenten schreiben enthält zwei Dinge, die im Zusammenhang mit RFX:

- Eine Initialisierung für jedes felddatenelement

- Eine Initialisierung für die [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields) Datenmember, der die Anzahl der Felddatenmember enthält

Der Konstruktor für die `CSections` Recordset-Beispiel sieht wie folgt aus:

```cpp
CSections::CSections(CDatabase* pdb)
   : CRecordset(pdb)
{
   m_strCourseID = "";
   m_strInstructorID = "";
   m_strRoomNo = "";
   m_strSchedule = "";
   m_strSectionNo = "";
   m_nFields = 5;
}
```

> [!NOTE]
>  Wenn Sie alle Felddatenmember manuell hinzufügen, wie Sie dynamisch neue Spalten zu binden, müssen Sie erhöhen `m_nFields`. Klicken Sie dazu eine neue Zeile des Codes, wie z. B. anfügen:

```cpp
m_nFields += 3;
```

Dies ist der Code für die drei neue Felder hinzufügen. Wenn Sie keine Parameterdatenmember hinzufügen, müssen Sie initialisieren den [M_nParams](../../mfc/reference/crecordset-class.md#m_nparams) Datenmember, der die Anzahl der Parameter-Datenmember enthält. Platzieren der `m_nParams` Initialisierung außerhalb der Klammern.

## <a name="see-also"></a>Siehe auch

[Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)
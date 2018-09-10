---
title: 'TN043: RFX-Routinen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- RFX
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1266097f9d548630459a3fb45ed75edb811deea
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317341"
---
# <a name="tn043-rfx-routines"></a>TN043: RFX-Routinen

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Dieser Hinweis beschreibt die Datensatzfeldaustausch-Datensatzfeldaustausch (RFX)-Architektur. Außerdem wird beschrieben, wie Sie schreiben eine **RFX_** Verfahren.

## <a name="overview-of-record-field-exchange"></a>Übersicht über die Datensatzfeldaustausch

Recordset alle Funktionen werden mit C++-Code ausgeführt. Es gibt keine spezielle Ressourcen oder dem Magic-Makros. Das Herzstück des Mechanismus ist eine virtuelle Funktion, die in jeder abgeleiteten Recordset-Klasse überschrieben werden muss. Es befindet sich immer in dieser Form:

```cpp
void CMySet::DoFieldExchange(CFieldExchange* pFX)
{
    //{{AFX_FIELD_MAP(CMySet)
        <recordset exchange field type call>
        <recordset exchange function call>
    //}}AFX_FIELD_MAP
}
```

Die speziellen Format AFX Kommentare können Klassen-Assistenten, um zu suchen und bearbeiten Sie den Code in dieser Funktion. Code, der mit dem Klassen-Assistent nicht kompatibel ist, sollte außerhalb der speziellen Format Kommentare platziert werden.

Im obigen Beispiel \<Recordset_exchange_field_type_call > hat das Format:

```cpp
pFX->SetFieldType(CFieldExchange::outputColumn);
```

und \<Recordset_exchange_function_call > hat das Format:

```cpp
RFX_Custom(pFX, "Col2", m_Col2);
```

Die meisten **RFX_** Funktionen verfügen über drei Argumenten wie oben gezeigt, aber einige (z. B. `RFX_Text` und `RFX_Binary`) haben Sie zusätzliche optionale Argumente.

Mehr als eine **RFX_** enthalten sein kann, in den einzelnen `DoDataExchange` Funktion.

Finden Sie unter "afxdb.h" eine Liste mit allen dem Recordset Feld Exchange Routinen mit MFC bereitgestellt.

Recordset-Feld-Aufrufe sind eine Möglichkeit der Registrierung von Speicherorten (normalerweise die Datenmember) zum Speichern von Feld-Daten für eine `CMySet` Klasse.

## <a name="notes"></a>Hinweise

Recordset Funktionen dienen nur zur Verwendung der `CRecordset` Klassen. Sie sind nicht in der Regel von anderen MFC-Klassen verwendet werden kann.

Die Anfangswerte der Daten werden in der standardmäßigen C++-Konstruktor, in der Regel in einem Block mit festgelegt `//{{AFX_FIELD_INIT(CMylSet)` und `//}}AFX_FIELD_INIT` Kommentare.

Jede **RFX_** Funktion muss unterstützen verschiedene Vorgänge, die zwischen der Rückgabe des geänderten Status des Felds zum Archivieren des Felds als Vorbereitung für das Feld bearbeitet.

Jede Funktion, die Aufrufe `DoFieldExchange` (z. B. `SetFieldNull`, `IsFieldDirty`), ist eine eigene Initialisierung rund um den Aufruf `DoFieldExchange`.

## <a name="how-does-it-work"></a>Wie funktioniert es

Sie müssen sich nicht um Folgendes zu Datensatzfeldaustausch verwenden. Schreiben jedoch verstehen, wie dies hinter den Kulissen funktioniert. Sie können Ihre eigene Exchange-Prozedur.

Die `DoFieldExchange` Memberfunktion ist ähnlich wie die `Serialize` Memberfunktion – dient zum Abrufen oder Festlegen von Daten in und aus einem externen Formular (in diesem Groß-/Kleinschreibung Spalten aus dem Ergebnis einer ODBC-Abfrage) vom bzw. an Daten in der Klasse. Die *pFX* -Parameter ist der Kontext dafür den Datenaustausch und ähnelt der *CArchive* Parameter `CObject::Serialize`. Die *pFX* (eine `CFieldExchange` Objekt) verfügt über ein Indikator Vorgang, mit dem ähnelt, aber eine Generalisierung von der *CArchive* Richtungsflag. RFX-Funktion möglicherweise die folgenden Vorgänge unterstützt:

- `BindParam` – Anzugeben Sie, wo die ODBC-Parameterdaten abrufen sollen

- `BindFieldToColumn` – Geben Sie an, in dem ODBC abrufen/OutputColumn Daten Einzahlung müssen

- `Fixup` – Legen Sie `CString/CByteArray` Länge und NULL-Status, die bit festlegen

- `MarkForAddNew` – Mark geändert, wenn der Wert geändert wurde, da der Aufruf von AddNew

- `MarkForUpdate` – Mark geändert, wenn der Wert geändert wurde, da aufrufen bearbeiten

- `Name` – Fügen Sie die Feldnamen für Felder geändert markiert

- `NameValue` – Append "\<Spaltenname > =" für Felder geändert markiert

- `Value` – Fügen Sie "" gefolgt von Trennzeichen, z. B. ',' oder ' "

- `SetFieldDirty` : Setzen Sie Bit geändert (d. h. geänderten) Statusfeld

- `SetFieldNull` – Legen Sie die Statusbit, der angibt, der null-Wert für Feld

- `IsFieldDirty` – Rückgabewert des geänderten Status Bits

- `IsFieldNull` – Die Rückgabewert von null-Status-bit

- `IsFieldNullable` – "True" zurück, wenn das Feld NULL-Werte enthalten kann

- `StoreField` – Wert des Felds Archiv

- `LoadField` – Laden Sie die archivierten Feldwert

- `GetFieldInfoValue` – Allgemeine Informationen für ein Feld zurück

- `GetFieldInfoOrdinal` – Allgemeine Informationen für ein Feld zurück

## <a name="user-extensions"></a>Benutzer-Erweiterungen

Es gibt verschiedene Möglichkeiten zum Erweitern des Standard-RFX-Mechanismus. Sie haben folgende Möglichkeiten:

- Fügen Sie neue Datentypen hinzu. Zum Beispiel:

    ```cpp
    CBookmark
    ```

- Fügen Sie die neue Exchange-Prozeduren (RFX_) hinzu.

    ```cpp
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
        const char *szName,
        BIGINT& value);
    ```

- Haben die `DoFieldExchange` Memberfunktion bedingt enthalten, zusätzliche RFX-Funktionen aufrufen oder eine beliebige andere gültige C++-Anweisungen.

    ```cpp
    while (posExtraFields != NULL)
    {
        RFX_Text(pFX,
        m_listName.GetNext(posExtraFields),
        m_listValue.GetNext(posExtraValues));
    }
    ```

> [!NOTE]
> Dieser Code kann nicht von Datensatzfeldern von ClassWizard nicht bearbeitet werden und sollte nur außerhalb der speziellen Format Kommentare verwendet werden.

## <a name="writing-a-custom-rfx"></a>Schreiben Sie eine benutzerdefinierte RFX

Um Ihre eigene benutzerdefinierte RFX-Funktion zu schreiben, wird empfohlen, dass Sie eine vorhandene RFX-Funktion kopieren, und sie für Ihre eigenen Zwecke ändern. Auswählen der richtigen RFX kopieren kann Ihren Auftrag erheblich vereinfachen. Einige RFX-Funktionen verfügen einige eindeutige Eigenschaften, die Sie berücksichtigen sollten bei der Entscheidung, das kopiert werden.

`RFX_Long` und `RFX_Int`: Hierbei handelt es sich um die einfachste RFX-Funktionen. Der Datenwert ist nicht erforderlich für jede spezielle Interpretation, und die Größe der Daten wurde behoben.

`RFX_Single` und `RFX_Double`: wie RFX-Long RFX_Int oben, diese Funktionen sind einfach und kann die standardmäßige Implementierung umfassend nutzen. Sie sind im dbflt.cpp statt dbrfx.cpp, jedoch gespeichert, um aktivieren Sie das Laden der Laufzeit floating Point-Bibliothek, nur, wenn sie explizit Verweis sind.

`RFX_Text` und `RFX_Binary`: Diese beiden Funktionen vorab einen statischen Puffer zum Speichern von Informationen für Zeichenfolge/Binary, und müssen diese Puffer registrieren & Wert bei ODBC SQLBindCol registrieren. Aus diesem Grund habe diese beiden Funktionen speziellen Code.

`RFX_Date`: ODBC gibt die Datums-und Uhrzeitinformationen in ihre eigenen TIMESTAMP_STRUCT Datenstruktur zurück. Diese Funktion weist eine TIMESTAMP_STRUCT dynamisch als "Proxy" für das Senden und Empfangen von Daten für Datum-Zeit. Verschiedene Vorgänge müssen die Informationen für Datum und Uhrzeit zwischen dem C++ übertragen `CTime` Objekt und dem TIMESTAMP_STRUCT-Proxy. Dies erschwert diese Funktion erheblich, aber es ist ein gutes Beispiel dafür, wie einen Proxy für die Datenübertragung verwendet.

`RFX_LongBinary`: Dies ist der einzige Klassenbibliothek RFX-Funktion, die nicht spaltenbindung zum Empfangen und Senden von Daten. Diese Funktion ignoriert die Operation BindFieldToColumn stattdessen während des Vorgangs Fixup reserviert Speicher, um die eingehenden SQL_LONGVARCHAR oder SQL_LONGVARBINARY Daten enthalten, und führt einen SQLGetData-Aufruf zum Abrufen des Werts in den zugeordneten Speicher. Beim Vorbereiten zum Zurücksenden von Datenwerten mit der Datenquelle (z. B. NameValue und Wert-Vorgänge) verwendet diese Funktion ODBCs-DATA_AT_EXEC-Funktionalität. Finden Sie unter [technischen Hinweis 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) für Weitere Informationen zum Arbeiten mit SQL_LONGVARBINARY und SQL_LONGVARCHARs.

Wenn Sie Ihren eigenen schreiben **RFX_** -Funktion, Sie häufig werden mit `CFieldExchange::Default` auf einen bestimmten Vorgang zu implementieren. Sehen Sie sich die Implementierung der Standardwert für den betreffenden Vorgang. Wenn sie den Vorgang ausführt würden Sie schreiben Ihre **RFX_** Funktion, die Sie, um delegieren können die `CFieldExchange::Default`. Sehen Sie Beispiele zum Aufruf `CFieldExchange::Default` in dbrfx.cpp

Es ist wichtig, rufen Sie `IsFieldType` am Anfang die RFX-Funktion, und klicken Sie auf die Rückgabe sofort, wenn er "false" zurückgibt. Dieser Mechanismus wird Parameter Vorgänge durchgeführt werden, auf *OutputColumns*, und umgekehrt (z. B. Aufruf `BindParam` auf eine *OutputColumn*). Darüber hinaus `IsFieldType` automatisch verfolgt des gibt die Anzahl von *OutputColumns* (*M_nFields*) und Params (*M_nParams*).

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)  
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)  

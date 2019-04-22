---
title: 'Recordset: Parametrisieren eines Recordsets (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- parameterizing recordsets
- ODBC recordsets, parameterizing
- recordsets, parameterizing
- passing parameters, to queries at runtime
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
ms.openlocfilehash: df67256c54cae3e2adb054d653d3e58bb91dd631
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026161"
---
# <a name="recordset-parameterizing-a-recordset-odbc"></a>Recordset: Parametrisieren eines Recordsets (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

Manchmal empfiehlt in der Lage, wählen Sie die Datensätze zur Laufzeit mithilfe der Informationen, die Sie berechnet oder vom Benutzer abgerufen. Recordset-Parametern können Sie dieses Ziel zu erreichen.

In diesem Thema wird Folgendes erläutert:

- [Der Zweck eines parametrisierten Recordsets](#_core_parameterized_recordsets).

- [Wann und warum Sie möglicherweise ein Recordset parametrisieren möchten](#_core_when_to_use_parameters).

- [Beschreibt, wie Parameter Datenelemente im Recordset-Klasse deklariert](#_core_parameterizing_your_recordset_class).

- [Wie Sie Informationen zu den Parametern zu einem Recordset-Objekt zur Laufzeit übergeben](#_core_passing_parameter_values_at_run_time).

##  <a name="_core_parameterized_recordsets"></a> Parametrisierte Recordsets

Ein parametrisiertes Recordset können Sie die Parameterinformationen zur Laufzeit übergeben. Dies hat zwei wichtige Auswirkungen:

- Es kann eine bessere ausführungsgeschwindigkeit führen.

- Sie können eine Abfrage zu erstellen zur Laufzeit basierend auf Informationen, die zur Entwurfszeit nicht zur Verfügung, z. B. Informationen vom Benutzer erhalten oder zur Laufzeit berechnet.

Beim Aufruf `Open` zum Ausführen der Abfrage verwendet das Recordset die Parameterinformationen zum Abschließen der **SQL-SELECT** Anweisung. Sie können jedes Recordset parametrisieren.

##  <a name="_core_when_to_use_parameters"></a> Wenn Sie Parameter verwenden

Typische einsatzmöglichkeiten für Parameter sind:

- Übergeben von Argumenten an eine vordefinierte Abfrage zur Laufzeit.

   Um Parameter an eine gespeicherte Prozedur übergeben, müssen Sie eine vollständige benutzerdefinierte ODBC angeben **Aufrufen** Anweisung – mithilfe von Parameterplatzhaltern – beim Aufruf `Open`, dem Recordset Standard-SQL-Anweisung überschreiben. Weitere Informationen finden Sie unter [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) in die *Klassenbibliotheksreferenz* und [SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md) und [Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).

- Effiziente Ausführung zahlreicher Neuabfragen mit Informationen zu den verschiedenen Parametern.

   Beispielsweise können jedes Mal, wenn Ihre Endbenutzer Informationen für einen bestimmten Studenten in der Registrierungsdatenbank für Schüler und Studenten, sucht Sie Namen\noder die ID des Studenten als Parameter, der vom Benutzer angeben. Klicken Sie dann beim Aufrufen des Recordsets `Requery` Memberfunktion wird die Abfrage wählt nur diese Student Datensatz.

   Der Recordset-Filter-Zeichenfolge, die in `m_strFilter`, könnte wie folgt aussehen:

    ```cpp
    "StudentID = ?"
    ```

   Angenommen, Sie erhalten die Studenten-ID in der Variablen `strInputID`. Wenn Sie einen Parameter festlegen, um `strInputID` (z. B. die Studenten-ID 100) der Wert der Variablen gebunden ist, um die Parameterplatzhalter die "?" in der Filterzeichenfolge.

   Weisen Sie den Parameterwert wie folgt:

    ```cpp
    strInputID = "100";
    ...
    m_strParam = strInputID;
    ```

   Sie möchten nicht auf diese Weise eine Filterzeichenfolge einrichten:

    ```cpp
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted
                                       // for some drivers
    ```

   Eine Erläuterung der Verwendung von Anführungszeichen ordnungsgemäß für Filterzeichenfolgen, finden Sie unter [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

   Der Wert des Parameters unterscheidet sich jedes Mal, die das Recordset zu, für eine neue für Schüler und Studenten-ID aktualisieren

   > [!TIP]
   > Verwenden von Parametern ist effizienter als einfach einen Filter. Für eine parametrisierte Recordset, muss die Datenbank zu eine SQL verarbeiten **wählen** Anweisung nur einmal. Für ein gefiltertes Recordset ohne Parameter die **wählen** Anweisung verarbeitet werden muss jedes Mal, wenn Sie `Requery` durch einen neuen Filterwert.

Weitere Informationen zu filtern, finden Sie unter [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

##  <a name="_core_parameterizing_your_recordset_class"></a> Zum Parametrisieren von Recordset-Klasse

> [!NOTE]
> Dieser Abschnitt gilt für abgeleitete Objekte `CRecordset` in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie das gesammelte Abrufen, die Implementierung von Parametern verwenden wird ein ähnlicher Prozess. Weitere Informationen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Vor der Erstellung des Recordset-Klasse zu bestimmen, welche Parameter Sie benötigen, was ihre Datentypen sind und wie Sie das Recordset verwendet.

#### <a name="to-parameterize-a-recordset-class"></a>Parametrisieren von einem Recordset-Klasse

1. Führen Sie die [MFC-ODBC-Consumer-Assistenten](../../mfc/reference/adding-an-mfc-odbc-consumer.md) aus **Klasse hinzufügen** zum Erstellen der Klasse.

1. Geben Sie die Felddatenmember für die Spalten des Recordsets.

1. Nachdem der Assistent die Klasse in eine Datei in Ihrem Projekt schreibt, finden Sie unter der h-Datei und manuell fügen Sie eine oder mehrere Parameterdatenmember zur Klassendeklaration hinzu. Die Hinzufügung sieht in etwa wie im folgenden Beispiel, werden Teil einer Snapshot-Klasse beantworten Sie die Abfrage "die Schüler und Studenten sind in der senior-Klasse?"

    ```cpp
    class CStudentSet : public CRecordset
    {
    // Field/Param Data
        CString m_strFirstName;
        CString m_strLastName;
        CString m_strStudentID;
        CString m_strGradYear;

        CString m_strGradYrParam;
    };
    ```

   Fügen Sie nach den vom Assistenten generierte Felddatenmembern Parameterdatenmember hinzu. Standardmäßig wird das Wort "Param" an jeder benutzerdefinierte Parametername angefügt werden soll.

1. Ändern der [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) Definition der Memberfunktion in der CPP-Datei. Hinzufügen von RFX-Funktion für jedes Datenelement für Parameter, die Sie der Klasse hinzugefügt. Weitere Informationen über das Schreiben eigener RFX-Funktionen finden Sie unter [Record Field Exchange: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Geben Sie vor der RFX-Aufrufe für die Parameter mit einem einzigen Aufruf:

    ```cpp
    pFX->SetFieldType( CFieldExchange::param );
    // RFX calls for parameter data members
    ```

1. Erhöhen Sie im Konstruktor des Recordset-Klasse, die Anzahl von Parametern, `m_nParams`.

   Weitere Informationen finden Sie unter [Record Field Exchange: Arbeiten mit Assistenten-Code](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md).

1. Wenn Sie den Code, die einem Recordset-Objekt dieser Klasse erstellt schreiben, platzieren ein "?" (Fragezeichen) Symbol an jeder Stelle in Ihrer SQL-Anweisung-Zeichenfolgen, in denen ein Parameter ist, ersetzt werden.

   Zur Laufzeit "?" Platzhalter werden aufgefüllt, in der Reihenfolge, die Sie durch die Werte der Parameter zu übergeben. Der erste Parameter-Datenmember festgelegt wird, nachdem die [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) Aufruf ersetzt, die der ersten "?"in der SQL-Zeichenfolge, die zweite Parameterdatenmember ersetzt die zweite"?" und so weiter.

> [!NOTE]
> Die Reihenfolge der Parameter ist wichtig: die Reihenfolge der RFX-Aufrufe für Parameter in Ihre `DoFieldExchange` Funktion muss die Reihenfolge der Parameterplatzhalter in der SQL-Zeichenfolge entsprechen.

> [!TIP]
> Die wahrscheinlichste Zeichenfolge, die Arbeit mit ist die Zeichenfolge, die Sie angeben (sofern vorhanden) für der Klasse des [M_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) Datenmember, aber einige ODBC-Treiber können Parameter in anderen SQL-Klauseln können.

##  <a name="_core_passing_parameter_values_at_run_time"></a> Übergeben von Parameterwerten zur Laufzeit

Sie müssen die Parameterwerte angeben, vor dem Aufruf `Open` (für ein neues Recordsetobjekt) oder `Requery` (für eine vorhandene Ressourcengruppe).

#### <a name="to-pass-parameter-values-to-a-recordset-object-at-run-time"></a>Übergeben von Parameterwerten zu einem Recordset-Objekt zur Laufzeit

1. Erstellen Sie das Recordsetobjekt.

1. Eine Zeichenfolge oder Zeichenfolgen, z. B. Vorbereiten der `m_strFilter` Zeichenfolge, die die SQL-Anweisung, oder Teilen davon. Einfügen "?" Platzhalter, in denen die Parameterinformationen, sich an.

1. Jeder Parameter-Datenmember des Objekts wird einen Laufzeit-Parameterwert zuweisen.

1. Rufen Sie die `Open` Member-Funktion (oder `Requery`, für ein bereits vorhandenes Recordset).

Nehmen wir beispielsweise an, dass Sie eine Filterzeichenfolge für das Recordset mit Informationen, die zur Laufzeit abgerufene angeben möchten. Angenommen, Sie haben ein Recordset-Klasse erstellt `CStudentSet` zuvor – namens `rsStudents` – und möchten nun neu Abfragen für eine bestimmte Art von Informationen über Schüler.

```cpp
// Set up a filter string with
// parameter placeholders
rsStudents.m_strFilter = "GradYear <= ?";

// Obtain or calculate parameter values
// to pass--simply assigned here
CString strGradYear = GetCurrentAcademicYear( );

// Assign the values to parameter data members
rsStudents.m_strGradYrParam = strGradYear;

// Run the query
if( !rsStudents.Requery( ) )
    return FALSE;
```

Das Recordset enthält Datensätze, für die Schüler/Studenten, deren Datensätze erfüllt die Bedingungen, die gemäß des Filters, der von der Laufzeit-Parameter erstellt wurde. In diesem Fall enthält das Recordset Datensätze für alle senior Schüler/Studenten.

> [!NOTE]
>  Bei Bedarf können Sie den Wert eines Datenmembers Parameter festlegen, für NULL-Werte mit [SetParamNull](../../mfc/reference/crecordset-class.md#setparamnull). Entsprechend können Sie überprüfen, ob ein Parameterdatenmember Null ist, ist mit [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull).

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Recordset: Datensatzauswahl durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
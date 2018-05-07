---
title: 'Recordset: Parametrisieren eines Recordsets (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parameterizing recordsets
- ODBC recordsets, parameterizing
- recordsets, parameterizing
- passing parameters, to queries at runtime
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 275cd9d2ee7ccbd4c9972c00ae6fbb8f33166a0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-parameterizing-a-recordset-odbc"></a>Recordset: Parametrisieren eines Recordsets (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In einigen Fällen empfiehlt in der Lage, wählen Sie Einträge zur Laufzeit mithilfe der Informationen, die Sie berechnet oder von Ihren Endbenutzern abgerufen haben. Recordset-Parametern können Sie dieses Ziel zu erreichen.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Der Zweck eines parametrisierten Recordsets](#_core_parameterized_recordsets).  
  
-   [Wann und warum Sie ein Recordset parametrisieren möchten](#_core_when_to_use_parameters).  
  
-   [Parameter-Datenmember in Recordset-Klasse deklarieren](#_core_parameterizing_your_recordset_class).  
  
-   [Gewusst wie: Übergeben von Parameterinformationen zu einem Recordset-Objekt zur Laufzeit](#_core_passing_parameter_values_at_run_time).  
  
##  <a name="_core_parameterized_recordsets"></a> Parametrisierte Recordsets  
 Ein parametrisierte Recordset können Sie die Parameterinformationen zur Laufzeit übergeben. Dies hat zwei wichtige Auswirkungen:  
  
-   Es kann eine bessere ausführungsgeschwindigkeit führen.  
  
-   Sie können damit erstellen Sie eine Abfrage zur Laufzeit basierend auf Informationen, die zur Entwurfszeit nicht zur Verfügung, z. B. Informationen vom Benutzer erhalten oder zur Laufzeit berechnet.  
  
 Beim Aufruf **öffnen** zum Ausführen der Abfrage verwendet das Recordset die Parameterinformationen zum Abschließen der **SQL SELECT-Anweisung** Anweisung. Sie können jedes beliebige Recordset parametrisieren.  
  
##  <a name="_core_when_to_use_parameters"></a> Verwenden von Parametern  
 Typische Verwendungsmöglichkeiten für Parameter aufgeführt:  
  
-   Übergeben von Argumenten an eine vordefinierte Abfrage zur Laufzeit.  
  
     Um Parameter an eine gespeicherte Prozedur übergeben, müssen Sie eine vollständige benutzerdefinierte ODBC angeben **Aufrufen** Anweisung – mithilfe von Parameterplatzhaltern – beim Aufruf **öffnen**, das Recordset Standard-SQL-Anweisung überschreiben. Weitere Informationen finden Sie unter [CRecordset](../../mfc/reference/crecordset-class.md#open) in der *Klassenbibliotheksreferenz* und [SQL: Anpassen eines Recordsets SQL-Anweisung (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md) und [ Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).  

  
-   Effiziente Ausführung zahlreicher Neuabfragen mit verschiedenen Parameterinformationen.  
  
     Beispielsweise können jedes Mal, wenn Ihre Endbenutzer Informationen für einen bestimmten Studenten in die Datenbank Student Registration sucht Sie Namen\noder die ID des Studenten als Parameter, der vom Benutzer angeben. Klicken Sie dann beim Aufrufen des Recordsets **Requery** Memberfunktion, die Abfrage wählt nur diese Student Datensatz.  
  
     Das Recordset-Filter-Zeichenfolge, die in **M_strFilter**, könnte wie folgt aussehen:  
  
    ```  
    "StudentID = ?"  
    ```  
  
     Angenommen, Sie erhalten die Studenten-ID in der Variablen `strInputID`. Wenn Sie einen Parameter festlegen, auf `strInputID` (z. B. die Studenten-ID 100) der Wert der Variablen an die Parameterplatzhalter dargestellte gebunden ist das "?" in der Filterzeichenfolge.  
  
     Weisen Sie den Parameterwert wie folgt:  
  
    ```  
    strInputID = "100";  
    ...  
    m_strParam = strInputID;  
    ```  
  
     Sie möchten nicht auf diese Weise eine Filterzeichenfolge einzurichten:  
  
    ```  
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted  
                                       // for some drivers  
    ```  
  
     Eine Erläuterung dazu, wie Sie Filterzeichenfolgen ordnungsgemäß, finden Sie unter [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
     Der Wert des Parameters ist jedes Mal anders das Recordset zu, auf eine neue Student-ID. aktualisieren  
  
    > [!TIP]
    >  Verwenden eines Parameters ist effizienter als ein einfacher Filter. Für einen parametrisierten Recordset Verarbeiten der Datenbank muss eine SQL **wählen** Anweisung nur einmal. Für ein gefiltertes Recordset ohne Parameter die **wählen** Anweisung verarbeitet werden muss jedes Mal, wenn Sie **Requery** durch einen neuen Filterwert.  
  
 Weitere Informationen zu Filtern finden Sie unter [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
##  <a name="_core_parameterizing_your_recordset_class"></a> Parametrisieren von Recordset-Klasse  
  
> [!NOTE]
>  Dieser Abschnitt gilt für Objekte, die von abgeleiteten `CRecordset` in denen der gesammelte Abrufen von Zeilen nicht implementiert wurde. Bei Verwendung von gesammelte Abrufen von Zeilen, die Implementierung von Parametern ist ein ähnlichen Prozess. Weitere Informationen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Vor der Erstellung des Recordset-Klasse zu ermitteln, welche Parameter Sie benötigen, was ihre Datentypen sind und wie Sie das Recordset verwendet.  
  
#### <a name="to-parameterize-a-recordset-class"></a>Parametrisieren von einem Recordset-Klasse  
  
1.  Führen Sie die [MFC-ODBC-Consumer-Assistent](../../mfc/reference/adding-an-mfc-odbc-consumer.md) aus **Klasse hinzufügen** zum Erstellen der Klasse.  
  
2.  Geben Sie die Felddatenmember für die Spalten des Recordsets.  
  
3.  Nachdem der Assistent die Klasse in eine Datei in Ihrem Projekt schreibt, wechseln Sie zu der .h-Datei, und fügen Sie eine oder mehrere Parameterdatenmember manuell hinzu, der Klassendeklaration. Zusätzlich sieht etwa wie im folgenden Beispiel, die Teil einer Snapshot-Klasse zur Beantwortung der Abfrage "die Studenten sind in der Klasse senior?"  
  
    ```  
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
  
     Fügen Sie Ihrer Parameterdatenmember nach den vom Assistenten generierten Felddatenmembern hinzu. Normalerweise wird das Wort "Param" an jedem benutzerdefinierten Parameternamen angefügt werden soll.  
  
4.  Ändern der [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) Memberfunktionsdefinition in der CPP-Datei. Hinzufügen eines Funktionsaufrufs RFX für jedes Datenelement für Parameter, die Sie der Klasse hinzugefügt. Informationen über das Schreiben von RFX-Funktionen finden Sie unter [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Geben Sie vor der RFX-Aufrufe für die Parameter mit einem einzigen Aufruf:  
  
    ```  
    pFX->SetFieldType( CFieldExchange::param );  
    // RFX calls for parameter data members  
    ```  
  
5.  Erhöhen Sie im Konstruktor der Recordset-Klasse, die Anzahl von Parametern, `m_nParams`.  
  
     Informationen finden Sie unter [Datensatzfeldaustausch: Arbeiten mit Assistenten-Code](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md).  
  
6.  Wenn Sie den Code, die einem Recordset-Objekt dieser Klasse erstellt schreiben, platzieren ein "?" (Fragezeichen) Symbol an jeder Stelle in Ihre SQL-Anweisung in Zeichenfolgen, in denen ein Parameter ist, ersetzt werden.  
  
     Zur Laufzeit "?" Platzhalter werden aufgefüllt, in der Reihenfolge, die Sie durch die Werte der Parameter zu übergeben. Nach der ersten Parameter-Datenmember festgelegt die [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) Aufruf ersetzt das erste "?"in der SQL-Zeichenfolge, die zweite Parameterdatenmember ersetzt das zweite"?", und so weiter.  
  
> [!NOTE]
>  Die Reihenfolge der Parameter ist wichtig: die Reihenfolge der RFX-Aufrufe für Parameter in Ihre `DoFieldExchange` Funktion muss die Reihenfolge der Parameterplatzhalter in der SQL-Zeichenfolge entsprechen.  
  
> [!TIP]

>  Die wahrscheinlichste Zeichenfolge zur Bearbeitung ist die Zeichenfolge, die Sie angeben (sofern vorhanden) für der Klasse [M_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) Datenmember, aber einige ODBC-Treiber können Parameter in anderen SQL-Klauseln.  
  
##  <a name="_core_passing_parameter_values_at_run_time"></a> Übergeben von Parameterwerten zur Laufzeit  
 Sie müssen die Parameterwerte angeben, vor dem Aufruf **öffnen** (für ein neues Recordset-Objekt) oder **Requery** (für ein bereits vorhandenes).  
  
#### <a name="to-pass-parameter-values-to-a-recordset-object-at-run-time"></a>Übergeben von Parameterwerten zu einem Recordset-Objekt zur Laufzeit  
  
1.  Erstellen Sie das Recordsetobjekt.  
  
2.  Eine Zeichenfolge oder Zeichenfolgen, z. B. Vorbereiten der **M_strFilter** Zeichenfolge, die die SQL-Anweisung oder Teile davon. Put "?" Platzhalter die Parameterinformationen steht zu wechseln.  
  
3.  Jeder Parameter-Datenmember des Objekts einen Laufzeit-Parameterwert zuweisen.  
  
4.  Rufen Sie die **öffnen** Memberfunktion (oder **Requery**, für ein bereits vorhandenes Recordset).  
  
 Nehmen Sie z. B. an, dass eine Filterzeichenfolge für das Recordset mit Informationen, die zur Laufzeit abgerufen werden sollen. Angenommen, Sie haben ein Recordset der Klasse erstellt `CStudentSet` zuvor – aufgerufen `rsStudents` – und möchten nun neu Abfragen für eine bestimmte Art von Informationen.  
  
```  
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
  
 Das Recordset enthält Datensätze für diese Studenten, deren Datensätze erfüllt die Bedingungen, die durch den Filter, der aus Laufzeitparametern konstruiert wurde angegeben. In diesem Fall enthält das Recordset Datensätze für alle senior Studenten.  
  
> [!NOTE]
>  Bei Bedarf können Sie den Wert eines Datenelements Parameter festlegen, auf Null, mit [SetParamNull](../../mfc/reference/crecordset-class.md#setparamnull). Entsprechend können Sie überprüfen, ob ein Parameterdatenmember Null ist, mit [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull).  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [Recordset: Wie Recordsets Datensätze auswählen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
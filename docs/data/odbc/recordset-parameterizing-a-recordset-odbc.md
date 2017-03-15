---
title: "Recordset: Parametrisieren eines Recordsets (ODBC) | Microsoft Docs"
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
  - "ODBC-Recordsets, Parametrisieren"
  - "Parametrisieren von Recordsets"
  - "Übergeben von Parametern, Für Abfragen zur Laufzeit"
  - "Recordsets, Parametrisieren"
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Recordset: Parametrisieren eines Recordsets (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In manchen Fällen ist es erforderlich, Datensätze zur Laufzeit auswählen zu können. Die Auswahl wird aufgrund von Informationen vorgenommen, die Sie berechnet oder vom Endbenutzer angefordert haben.  Für diesen Zweck sind Recordsetparameter vorgesehen.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Gründe für den Einsatz eines parametrisierten Recordsets](#_core_parameterized_recordsets).  
  
-   [Wann und wieso Sie ein Recordset parametrisieren sollten](#_core_when_to_use_parameters).  
  
-   [Wie Sie Parameterdatenmember in der Recordset\-Klasse deklarieren](#_core_parameterizing_your_recordset_class).  
  
-   [Wie Sie zur Laufzeit Parameterinformationen an ein Recordset\-Objekt übergeben](#_core_passing_parameter_values_at_run_time).  
  
##  <a name="_core_parameterized_recordsets"></a> Parametrisierte Recordsets  
 Mit einem parametrisierten Recordset können Sie Parameterinformationen zur Laufzeit übergeben.  Dies hat zwei positive Auswirkungen:  
  
-   Die Ausführungsgeschwindigkeit kann sich unter Umständen erhöhen.  
  
-   Sie können zur Laufzeit eine Abfrage erstellen, die auf Informationen basiert, die Ihnen in der Entwurfszeit noch nicht zur Verfügung standen. Dies können z. B. Informationen sein, die vom Benutzer eingegeben oder zur Laufzeit berechnet werden.  
  
 Wenn Sie die Abfrage mit einem Aufruf von **Open** ausführen, vervollständigt das Recordset die zugehörige **SQL SELECT**\-Anweisung mit den Parameterinformationen.  Sie können jedes beliebige Recordset parametrisieren.  
  
##  <a name="_core_when_to_use_parameters"></a> Wann Sie Parameter verwenden sollten  
 Typische Einsatzgebiete für Parameter sind:  
  
-   Übergeben von Laufzeitargumenten an eine vordefinierte Abfrage.  
  
     Um Parameter an eine gespeicherte Prozedur zu übergeben, müssen Sie beim Aufruf von **Open** eine vollständige, benutzerdefinierte ODBC\-**CALL**\-Anweisung mit Parameterplatzhaltern übergeben und so die Standard\-SQL\-Anweisung des Recordsets überschreiben.  Weitere Informationen finden Sie unter [CRecordset::Open](../Topic/CRecordset::Open.md) in der *Class Library Reference* sowie in den Themen [SQL: Anpassen der SQL\-Anweisung eines Recordsets \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md) und [Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).  
  
-   Effiziente Ausführung zahlreicher Neuabfragen mit verschiedenen Parameterinformationen.  
  
     Jedes Mal, wenn der Endbenutzer Informationen über einen bestimmten Studenten in der Studentendatenbank sucht, können Sie den Namen oder die ID des Studenten als Parameter übergeben, den Sie vom Benutzer erhalten haben.  Wenn Sie dann die **Requery**\-Memberfunktion des Recordsets aufrufen, wählt die Abfrage nur den Datensatz dieses Studenten aus.  
  
     Die in **m\_strFilter** gespeicherte Filterzeichenfolge des Recordsets könnte dann folgendermaßen aussehen:  
  
    ```  
    "StudentID = ?"  
    ```  
  
     Nehmen wir an, Sie erhalten die Studenten\-ID aus der Variablen `strInputID`.  Wenn Sie einem Parameter `strInputID` zuweisen \(z. B. die Studenten\-ID 100\), wird der Wert der Variablen an den Parameterplatzhalter gebunden, der in der Filterzeichenfolge durch das Fragezeichen repräsentiert wird.  
  
     Weisen Sie den Parameterwert folgendermaßen zu:  
  
    ```  
    strInputID = "100";  
    ...  
    m_strParam = strInputID;  
    ```  
  
     Es wird nicht empfohlen, eine Filterzeichenfolge auf die folgende Weise einzurichten:  
  
    ```  
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted  
                                       // for some drivers  
    ```  
  
     Eine Anleitung, wie Sie Filterzeichenfolgen richtig in Begrenzungszeichen einschließen, finden Sie unter [Recordset: Filtern von Datensätzen \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
     Der Parameter hat bei jeder Neuabfrage des Recordsets nach einer neuen Studenten\-ID einen anderen Wert.  
  
    > [!TIP]
    >  Ein Parameter ist effizienter als ein einfacher Filter.  Für ein parametrisiertes Recordset muss die Datenbank nur ein einziges Mal eine SQL\-**SELECT**\-Anweisung ausführen.  Für ein gefiltertes Recordset ohne Parameter muss die **SELECT**\-Anweisung dagegen jedes Mal ausgeführt werden, wenn Sie durch Aufruf von **Requery** eine Neuabfrage mit einem anderen Filterwert durchführen.  
  
 Weitere Informationen über Filter finden Sie unter [Recordset: Filtern von Datensätzen \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
##  <a name="_core_parameterizing_your_recordset_class"></a> Parametrisieren der Recordset\-Klasse  
  
> [!NOTE]
>  Dieser Abschnitt bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Falls Sie das gesammelte Abrufen von Zeilen einsetzen, ist der Prozess zur Implementierung von Parametern sehr ähnlich.  Weitere Informationen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Bevor Sie die Recordset\-Klasse erstellen können, müssen Sie entscheiden, welche Parameter Sie benötigen, welchen Datentyp diese haben und in welcher Weise sie vom Recordset verwendet werden.  
  
#### So parametrisieren Sie eine Recordset\-Klasse  
  
1.  Führen Sie den [MFC\-ODBC\-Consumer\-Assistenten](../../mfc/reference/adding-an-mfc-odbc-consumer.md) unter **Klasse hinzufügen** aus, um die Klasse zu erstellen.  
  
2.  Geben Sie die Felddatenmember für die Spalten des Recordsets an.  
  
3.  Nachdem der Assistent die Klasse in eine Datei des Projekts geschrieben hat, öffnen Sie die H\-Datei und fügen von Hand in die Klassendeklaration einen oder mehrere Parameterdatenmember ein.  Die hinzugefügten Teile könnten etwa so wie im folgenden Beispiel aussehen. Dieser Codeausschnitt zeigt eine Momentaufnahme\-Klasse, die die Abfrage "Welche Studenten sind in der Abschlussklasse?" beantworten soll.  
  
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
  
     Fügen Sie Parameterdatenmember nach den durch den Assistenten erstellten Felddatenmembern hinzu.  Sie sollten der Konvention folgen und an den Namen jedes benutzerdefinierten Parameternamens das Wort "Param" anhängen.  
  
4.  Ändern Sie in der CPP\-Datei die Definition der [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)\-Memberfunktion.  Fügen Sie für jeden Parameterdatenmember, den Sie der Klasse hinzugefügt haben, den Aufruf einer RFX\-Funktion ein.  Weitere Informationen über das Schreiben eigener RFX\-Funktionen finden Sie unter [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  Stellen Sie den RFX\-Aufrufen für die Parameter folgenden Aufruf voran:  
  
    ```  
    pFX->SetFieldType( CFieldExchange::param );  
    // RFX calls for parameter data members  
    ```  
  
5.  Erhöhen Sie im Konstruktor der Recordset\-Klasse den Parameterzähler `m_nParams`.  
  
     Weitere Informationen finden Sie unter [Datensatzfeldaustausch: Arbeiten mit Assistenten\-Code](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md).  
  
6.  Wenn Sie den Code schreiben, mit dem ein Recordset\-Objekt dieser Klasse erstellt wird, fügen Sie überall dort in den Zeichenfolgen der SQL\-Anweisung, wo ein Parameter ersetzt werden muss, ein Fragezeichen \("?"\) ein.  
  
     Zur Laufzeit werden die "?"\-Platzhalter durch die von Ihnen übergebenen Parameterwerte ersetzt.  Der erste nach dem Aufruf von [SetFieldType](../Topic/CFieldExchange::SetFieldType.md) gesetzte Parameterdatenmember ersetzt das erste "?" in der SQL\-Zeichenfolge, der zweite Parameterdatenmember ersetzt das zweite "?" usw.  
  
> [!NOTE]
>  Stellen Sie sicher, dass die Reihenfolge der RFX\-Aufrufe für Parameter in der `DoFieldExchange`\-Funktion der Reihenfolge der Platzhalter für Parameter in der SQL\-Zeichenfolge entspricht.  
  
> [!TIP]
>  Am häufigsten werden Sie mit der Zeichenfolge arbeiten, die Sie für den [m\_strFilter](../Topic/CRecordset::m_strFilter.md)\-Datenmember der Klasse angeben. Einige ODBC\-Treiber unterstützen jedoch möglicherweise Parameter in weiteren SQL\-Klauseln.  
  
##  <a name="_core_passing_parameter_values_at_run_time"></a> Übergeben von Parameterwerten zur Laufzeit  
 Sie müssen Parameterwerte angeben, bevor Sie **Open** \(für ein neues Recordset\-Objekt\) oder **Requery** \(für ein bereits vorhandenes Recordset\-Objekt\) aufrufen.  
  
#### So übergeben Sie zur Laufzeit Parameterwerte an ein Recordset\-Objekt  
  
1.  Konstruieren Sie das Recordset\-Objekt.  
  
2.  Bereiten Sie eine oder mehrere Zeichenfolgen vor \(z. B. die Zeichenfolge **m\_strFilter**\), die die SQL\-Anweisung oder Teile davon enthalten.  Setzen Sie "?"\-Platzhalter an die Stellen, in die Parameterinformationen eingetragen werden sollen.  
  
3.  Weisen Sie jedem Parameterdatenmember des Objekts einen Laufzeitparameterwert zu.  
  
4.  Rufen Sie die Memberfunktion **Open** auf \(oder **Requery** für ein bereits vorhandenes Recordset\).  
  
 Sie können z. B. eine Filterzeichenfolge für das Recordset definieren, die Informationen verwendet, die zur Laufzeit ermittelt werden.  Nehmen wir z. B. an, Sie haben unter dem Namen `rsStudents` ein Recordset der `CStudentSet`\-Klasse erstellt und möchten dieses Recordset jetzt nach bestimmten Informationen neu abfragen:  
  
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
  
 Das Recordset enthält die Datensätze aller Studenten, deren Datensätze den im Filter festgelegten Bedingungen entsprechen, wobei der Filter aus Laufzeitparametern erstellt wurde.  In diesem Beispiel enthält das Recordset die Datensätze aller Studenten im Abschlussjahr.  
  
> [!NOTE]
>  Bei Bedarf können Sie mit [SetParamNull](../Topic/CRecordset::SetParamNull.md) für den Wert eines Parameterdatenmembers NULL festlegen.  Entsprechend können Sie mit [IsFieldNull](../Topic/CRecordset::IsFieldNull.md) überprüfen, ob ein Parameterdatenmember NULL ist.  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [Recordset: Datensatzauswahl durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)